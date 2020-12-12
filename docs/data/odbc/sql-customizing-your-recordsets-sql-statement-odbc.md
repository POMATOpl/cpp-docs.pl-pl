---
description: 'Dowiedz się więcej na temat: SQL: dostosowywanie instrukcji SQL zestawu rekordów (ODBC)'
title: 'SQL: dostosowywanie instrukcji SQL zestawu rekordów (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
ms.openlocfilehash: 73765ed66dacbc017cca6236ae5a90388390fa45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278691"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: dostosowywanie instrukcji SQL zestawu rekordów (ODBC)

W tym temacie objaśniono:

- Jak struktura konstruuje instrukcję SQL

- Jak zastąpić instrukcję SQL

> [!NOTE]
> Te informacje dotyczą klas MFC ODBC. Jeśli pracujesz z klasami MFC DAO, zapoznaj się z tematem "porównanie usługi Microsoft Jet Database Engine SQL i ANSI SQL" w pomocy DAO.

## <a name="sql-statement-construction"></a>Konstrukcja instrukcji SQL

Zestawy rekordów opierają się przede wszystkim na instrukcji **SELECT** języka SQL. W przypadku deklarowania klasy za pomocą kreatora program zapisuje zastępujący wersję `GetDefaultSQL` funkcji członkowskiej, która wygląda podobnie do tego (dla klasy zestawu rekordów o nazwie `CAuthors` ).

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

Domyślnie to zastąpienie zwraca nazwę tabeli określoną za pomocą kreatora. W przykładzie nazwa tabeli to "autorów". Gdy później wywołasz `Open` funkcję członkowską zestawu rekordów, `Open` konstruuje końcową instrukcję **SELECT** w formularzu:

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

gdzie `table-name` jest uzyskiwany przez wywołanie `GetDefaultSQL` i `rfx-field-list` jest uzyskiwane z wywołań funkcji RFX w `DoFieldExchange` . Jest to możliwe dla instrukcji **SELECT** , chyba że zastąpisz ją w wersji zastępujący w czasie wykonywania, chociaż można także zmodyfikować instrukcję domyślną z parametrami lub filtrem.

> [!NOTE]
> Jeśli określisz nazwę kolumny, która zawiera (lub może zawierać) spacje, należy ująć ją w nawiasy kwadratowe. Na przykład nazwa "First Name" powinna mieć wartość "[First Name]".

Aby zastąpić domyślną instrukcję **SELECT** , należy przekazać ciąg zawierający kompletną instrukcję **SELECT** podczas wywoływania `Open` . Zamiast konstruować własny ciąg domyślny, zestaw rekordów używa dostarczonego ciągu. Jeśli instrukcja zastępująca zawiera klauzulę **WHERE** , nie należy określać filtru, `m_strFilter` ponieważ następnie można zastosować dwie instrukcje filtru. Podobnie, jeśli instrukcja zastępująca zawiera klauzulę **order by** , nie należy określać sortowania w `m_strSort` taki sposób, że nie będziesz mieć dwóch instrukcji Sort.

> [!NOTE]
> Jeśli używasz ciągów literałów w filtrach (lub innych częściach instrukcji SQL), może być konieczne wyrażenie "Quote" (ujęte w określonych ogranicznikach) takie ciągi z prefiksem literału i znakiem sufiksu literału (lub znaków).

Można również napotkać specjalne wymagania dotyczące składni dla operacji, takich jak sprzężenia zewnętrzne, w zależności od systemu DBMS. Użyj funkcji ODBC, aby uzyskać te informacje ze sterownika dla systemu DBMS. Na przykład, wywołaj `::SQLGetTypeInfo` dla określonego typu danych, na przykład `SQL_VARCHAR` ,, aby zażądać LITERAL_PREFIX i LITERAL_SUFFIX znaków. Jeśli piszesz kod niezależny od bazy danych, zobacz [dodatek C: Gramatyka SQL](/sql/odbc/reference/appendixes/appendix-c-sql-grammar) w [Kompendium ODBC programisty](/sql/odbc/reference/odbc-programmer-s-reference) , aby uzyskać szczegółowe informacje o składni.

Obiekt zestawu rekordów konstruuje instrukcję SQL, która używa do wybierania rekordów, chyba że zostanie przekazana niestandardowa instrukcja SQL. Sposób, w jaki jest to wykonywane, zależy głównie od wartości przekazywanej  w parametrze lpszSQL `Open` funkcji członkowskiej.

Ogólna forma instrukcji **SELECT** języka SQL:

```
SELECT [ALL | DISTINCT] column-list FROM table-list
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]
```

Jednym ze sposobów dodawania słowa kluczowego **DISTINCT** do instrukcji SQL zestawu rekordów jest osadzenie słowa kluczowego w pierwszym WYWOŁANIU funkcji RFX w `DoFieldExchange` . Na przykład:

```
...
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);
...
```

> [!NOTE]
> Tej techniki należy używać tylko z zestawem rekordów otwartym jako tylko do odczytu.

## <a name="overriding-the-sql-statement"></a>Zastępowanie instrukcji SQL

W poniższej tabeli przedstawiono możliwości parametru *lpszSQL* `Open` . Przypadki w tabeli wyjaśniono poniżej tabeli.

**Parametr lpszSQL i otrzymany ciąg SQL**

|Sprawa|Co przekazujesz w lpszSQL|Wynikająca instrukcja SELECT|
|----------|------------------------------|------------------------------------|
|1|NULL|**Wybierz** *RFX-Field-list* **z** *tabeli-Name*<br /><br /> `CRecordset::Open` wywołuje metodę `GetDefaultSQL` pobrania nazwy tabeli. Wynikowy ciąg jest jednym z przypadków od 2 do 5, w zależności od `GetDefaultSQL` zwracanych wartości.|
|2|Nazwa tabeli|**Wybierz** *RFX-Field-list* **z** *tabeli-Name*<br /><br /> Lista pól jest pobierana z instrukcji RFX w `DoFieldExchange` . Jeśli `m_strFilter` i `m_strSort` nie są puste, program dodaje klauzule **WHERE** i/lub **order by** .|
|r.3 \*|Kompletna instrukcja **SELECT** , ale bez klauzuli **WHERE** lub **order by**|Zgodnie z oczekiwaniami. Jeśli `m_strFilter` i `m_strSort` nie są puste, program dodaje klauzule **WHERE** i/lub **order by** .|
|czwart \*|Kompletna instrukcja **SELECT** z klauzulą **WHERE** i/lub **order by**|Zgodnie z oczekiwaniami. `m_strFilter` i/lub `m_strSort` muszą pozostać puste lub dwie instrukcje Filter i/lub Sort są generowane.|
|5000 \*|Wywołanie procedury składowanej|Zgodnie z oczekiwaniami.|

\*`m_nFields`musi być mniejsza lub równa liczbie kolumn określonych w instrukcji **SELECT** . Typ danych każdej kolumny określonej w instrukcji **SELECT** musi być taki sam jak typ danych odpowiadającej RFX kolumny wyjściowej.

### <a name="case-1---lpszsql--null"></a>Przypadek 1 lpszSQL = NULL

Wybór zestawu rekordów zależy od tego, co `GetDefaultSQL` zwraca po `CRecordset::Open` jego wywołania. W przypadku przypadków od 2 do 5 opisano możliwe ciągi.

### <a name="case-2---lpszsql--a-table-name"></a>Przypadek 2 lpszSQL = nazwa tabeli

Zestaw rekordów używa wymiany pól rekordów (RFX) w celu skompilowania listy kolumn na podstawie nazw kolumn dostarczonych w wywołaniach funkcji RFX w przesłonięciu klasy zestawu rekordów `DoFieldExchange` . Jeśli użyto Kreatora do zadeklarowania klasy zestawu rekordów, ten przypadek ma taki sam wynik jak w przypadku 1 (pod warunkiem, że podano tę samą nazwę tabeli, która została określona w Kreatorze). Jeśli nie używasz Kreatora do pisania klasy, przypadek 2 jest najprostszym sposobem konstruowania instrukcji SQL.

Poniższy przykład tworzy instrukcję SQL, która wybiera rekordy z aplikacji bazy danych MFC. Gdy struktura wywołuje `GetDefaultSQL` funkcję członkowską, funkcja zwraca nazwę tabeli, `SECTION` .

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

Aby uzyskać nazwy kolumn instrukcji **SELECT** języka SQL, struktura wywołuje `DoFieldExchange` funkcję członkowską.

```cpp
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)
{
    pFX->SetFieldType(CFieldExchange::outputColumn);
    RFX_Text(pFX, "CourseID", m_strCourseID);
    RFX_Text(pFX, "InstructorID", m_strInstructorID);
    RFX_Text(pFX, "RoomNo", m_strRoomNo);
    RFX_Text(pFX, "Schedule", m_strSchedule);
    RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

Po zakończeniu instrukcja SQL będzie wyglądać następująco:

```sql
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo
    FROM SECTION
```

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Przypadek 3 lpszSQL = instrukcja SELECT/FROM

Należy ręcznie określić listę kolumn, zamiast polegać na RFX. Można to zrobić w następujący sposób:

- Chcesz określić słowo kluczowe **DISTINCT** po **zaznaczeniu**.

   Lista kolumn powinna być zgodna z nazwami kolumn i typami w tej samej kolejności, w jakiej są wymienione w `DoFieldExchange` .

- Istnieje powód, aby ręcznie pobrać wartości kolumn przy użyciu funkcji ODBC `::SQLGetData` zamiast polegać na RFX, aby powiązać i pobrać kolumny.

   Możesz na przykład uwzględnić nowe kolumny klienta aplikacji dodanej do tabel bazy danych po rozesłaniu aplikacji. Należy dodać te dodatkowe składowe danych pól, które nie były znane w czasie zadeklarowanym w klasie za pomocą kreatora.

   Lista kolumn powinna być zgodna z nazwami kolumn i typami w tej samej kolejności, w jakiej są wyświetlane w `DoFieldExchange` , a następnie według nazw kolumn powiązanych ręcznie. Aby uzyskać więcej informacji, zobacz [zestaw rekordów: dynamiczne wiązanie kolumn danych (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

- Chcesz dołączyć do tabel, określając wiele tabel w klauzuli **from** .

   Aby uzyskać informacje i przykład, zobacz [zestaw rekordów: wykonywanie sprzężenia (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>Przypadek 4 lpszSQL = SELECT/FROM oraz WHERE i/lub ORDER BY

Należy określić wszystko: lista kolumn (oparta na wywołaniach RFX w programie `DoFieldExchange` ), lista tabel oraz zawartość klauzuli **order by** i/  or. Jeśli określisz klauzule **WHERE** i/lub **order by** w ten sposób, nie używaj `m_strFilter` i/lub `m_strSort` .

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>Przypadek 5 lpszSQL = wywołanie procedury składowanej

Jeśli konieczne jest wywołanie wstępnie zdefiniowanego zapytania (na przykład procedury składowanej w Microsoft SQL Server Database), należy napisać instrukcję **call** w ciągu przekazywanym do *lpszSQL*. Kreatory nie obsługują deklarowania klasy zestawu rekordów do wywoływania wstępnie zdefiniowanego zapytania. Nie wszystkie wstępnie zdefiniowane zapytania zwracają rekordy.

Jeśli wstępnie zdefiniowane zapytanie nie zwraca rekordów, można użyć `CDatabase` funkcji elementu członkowskiego `ExecuteSQL` bezpośrednio. Dla wstępnie zdefiniowanego zapytania, które zwraca rekordy, należy również ręcznie napisać wywołania RFX w `DoFieldExchange` dla każdej kolumny, która zwraca procedurę. Wywołania RFX muszą być w tej samej kolejności i zwracać te same typy, co wstępnie zdefiniowane zapytanie. Aby uzyskać więcej informacji, zobacz [zestaw rekordów: deklarowanie klasy dla wstępnie zdefiniowanego zapytania (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md).

## <a name="see-also"></a>Zobacz też

[SQL: typy danych SQL i C++ (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL: wykonywanie bezpośrednich wywołań SQL (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

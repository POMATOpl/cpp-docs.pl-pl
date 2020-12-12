---
description: Dowiedz się więcej o strukturze CDaoQueryDefInfo —
title: CDaoQueryDefInfo — Struktura
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDefInfo
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
ms.openlocfilehash: 46b9b49d91d3d005d941eb585663c205fe30b2da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271814"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo — Struktura

`CDaoQueryDefInfo`Struktura zawiera informacje o obiekcie querydef zdefiniowanym dla obiektów dostępu do danych (DAO).

## <a name="syntax"></a>Składnia

```
struct CDaoQueryDefInfo
{
    CString m_strName;               // Primary
    short m_nType;   // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    BOOL m_bUpdatable;               // Secondary
    BOOL m_bReturnsRecords;          // Secondary
    CString m_strSQL;                // All
    CString m_strConnect;            // All
    short m_nODBCTimeout;            // All
};
```

#### <a name="parameters"></a>Parametry

*m_strName*<br/>
Unikatowa nazwa obiektu querydef. Aby uzyskać więcej informacji, zobacz temat "Nazwa właściwości" w pomocy DAO. Wywołaj metodę [CDaoQueryDef:: GetName](../../mfc/reference/cdaoquerydef-class.md#getname) , aby bezpośrednio pobrać tę właściwość.

*m_nType*<br/>
Wartość wskazująca typ operacyjny obiektu querydef. Może to być jedna z następujących wartości:

- `dbQSelect` SELECT — zapytanie wybiera rekordy.

- `dbQAction` Akcja — zapytanie przenosi lub zmienia dane, ale nie zwraca rekordów.

- `dbQCrosstab` Krzyżowe — zapytanie zwraca dane w formacie przypominającym arkusz kalkulacyjny.

- `dbQDelete` Usuń — zapytanie usuwa zestaw określonych wierszy.

- `dbQUpdate` Update — zapytanie zmienia zestaw rekordów.

- `dbQAppend` Append — zapytanie dodaje nowe rekordy na końcu tabeli lub zapytania.

- `dbQMakeTable` Utwórz tabelę — zapytanie tworzy nową tabelę na podstawie zestawu rekordów.

- `dbQDDL` Definicja danych — zapytanie wpływa na strukturę tabel lub ich części.

- `dbQSQLPassThrough` Przekazywanie — instrukcja SQL jest przekazywany bezpośrednio do zaplecza bazy danych bez przetwarzania pośredniego.

- `dbQSetOperation` Union — zapytanie tworzy obiekt zestawu rekordów typu migawka zawierający dane ze wszystkich określonych rekordów w co najmniej dwóch tabelach z usuniętymi powielonymi rekordami. Aby uwzględnić duplikaty, Dodaj słowo kluczowe **All** w instrukcji SQL obiektu querydef.

- `dbQSPTBulk` Używany z programem w `dbQSQLPassThrough` celu określenia zapytania, które nie zwraca rekordów.

> [!NOTE]
> Aby utworzyć kwerendę przekazującą SQL, nie ustawiasz `dbQSQLPassThrough` stałej. Ta wartość jest ustawiana automatycznie przez aparat bazy danych Microsoft Jet podczas tworzenia obiektu querydef i ustawiania właściwości Connect.

Aby uzyskać więcej informacji, zobacz temat "Type Property" w pomocy DAO.

*m_dateCreated*<br/>
Data i godzina utworzenia querydef. Aby bezpośrednio pobrać datę utworzenia, należy wywołać funkcję członkowską [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) `CDaoTableDef` obiektu skojarzonego z tabelą. Aby uzyskać więcej informacji, zobacz poniższe komentarze. Zapoznaj się również z tematem "DateCreated, LastUpdated Properties" w pomocy DAO.

*m_dateLastUpdated*<br/>
Data i godzina ostatniej zmiany wprowadzonej do obiektu querydef. Aby bezpośrednio pobrać datę ostatniej aktualizacji tabeli, wywołaj funkcję członkowską [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) obiektu querydef. Aby uzyskać więcej informacji, zobacz poniższe komentarze. I zapoznaj się z tematem "DateCreated, LastUpdated Properties" w pomocy DAO.

*m_bUpdatable*<br/>
Wskazuje, czy można wprowadzać zmiany do obiektu querydef. Jeśli ta właściwość ma wartość TRUE, querydef jest aktualizowalny; w przeciwnym razie nie jest. Aktualizowalne oznacza, że można zmienić definicję zapytania obiektu querydef. Właściwość aktualizowalna obiektu querydef ma ustawioną wartość TRUE, jeśli można zaktualizować definicję zapytania, nawet jeśli wynikowy zestaw rekordów nie jest aktualizowalny. Aby bezpośrednio pobrać tę właściwość, wywołaj funkcję członkowską [aktualizującą](../../mfc/reference/cdaoquerydef-class.md#canupdate) querydef. Aby uzyskać więcej informacji, zobacz temat "Aktualizowalna właściwość" w pomocy DAO.

*m_bReturnsRecords*<br/>
Wskazuje, czy kwerenda przekazująca SQL do zewnętrznej bazy danych zwraca rekordy. Jeśli ta właściwość ma wartość TRUE, zapytanie zwraca rekordy. Aby bezpośrednio pobrać tę właściwość, wywołaj [CDaoQueryDef:: GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords). Nie wszystkie zapytania przekazujące SQL do zewnętrznych baz danych zwracają rekordy. Na przykład, instrukcja SQL **Update** aktualizuje rekordy bez zwracania rekordów, natomiast instrukcja **SELECT** języka SQL zwraca rekordy. Aby uzyskać więcej informacji, zobacz temat "Właściwość ReturnsRecords" w pomocy DAO.

*m_strSQL*<br/>
Instrukcja SQL, która definiuje zapytanie wykonywane przez obiekt querydef. Właściwość SQL zawiera instrukcję SQL, która określa, jak rekordy są wybierane, grupowane i uporządkowane podczas wykonywania zapytania. Można użyć zapytania, aby wybrać rekordy do uwzględnienia w obiekcie zestawu rekordów typu dynamiczny lub Snapshot-Type. Można także definiować zapytania zbiorcze, aby modyfikować dane bez zwracania rekordów. Wartość tej właściwości można pobrać bezpośrednio, wywołując funkcję elementu członkowskiego [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) obiektu querydef.

*m_strConnect*<br/>
Zawiera informacje o źródle bazy danych używanej w zapytaniu przekazującym. Te informacje mają postać ciągu połączenia. Aby uzyskać więcej informacji na temat łączenia ciągów i informacje o tym, jak bezpośrednio pobrać wartość tej właściwości, zobacz funkcja członkowska [CDaoDatabase:: GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) .

*m_nODBCTimeout*<br/>
Liczba sekund oczekiwania przez aparat bazy danych Microsoft Jet przed wystąpieniem błędu limitu czasu, gdy zapytanie zostanie uruchomione w bazie danych ODBC. W przypadku korzystania z bazy danych ODBC, takiej jak Microsoft SQL Server, mogą występować opóźnienia spowodowane ruchem sieciowym lub intensywnym użyciem serwera ODBC. Zamiast czekać w nieskończoność, można określić, jak długo aparat programu Microsoft Jet czeka przed wygenerowaniem błędu. Domyślna wartość limitu czasu to 60 sekund. Wartość tej właściwości można pobrać bezpośrednio, wywołując funkcję elementu członkowskiego [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) obiektu querydef. Aby uzyskać więcej informacji, zobacz temat "Właściwość ODBCTimeout" w pomocy DAO.

## <a name="remarks"></a>Uwagi

Querydef jest obiektem klasy [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Odwołania do elementów podstawowych, pomocniczych i wszystkie powyżej wskazują, jak informacje są zwracane przez funkcję składową [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) w klasie `CDaoDatabase` .

Informacje pobierane przez funkcję członkowską [CDaoDatabase:: GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) są przechowywane w `CDaoQueryDefInfo` strukturze. Wywołanie `GetQueryDefInfo` obiektu bazy danych, w którym kolekcjabinding obiektu querydef jest przechowywana. `CDaoQueryDefInfo` definiuje również `Dump` funkcję członkowską w kompilacjach debugowania. Możesz użyć, `Dump` aby zrzucić zawartość `CDaoQueryDefInfo` obiektu. Klasa `CDaoDatabase` udostępnia również funkcje członkowskie do bezpośredniego dostępu do wszystkich właściwości zwracanych w `CDaoQueryDefInfo` obiekcie, dlatego prawdopodobnie rzadko trzeba będzie wywołać `GetQueryDefInfo` .

Po dołączeniu nowego pola lub obiektu parametru do kolekcji pól lub parametrów obiektu querydef wyjątek jest zgłaszany, jeśli bazowa baza danych nie obsługuje typu danych określonego dla nowego obiektu.

Ustawienia daty i godziny są wyprowadzane z komputera, na którym interfejs querydef został utworzony lub ostatnio zaktualizowany. W środowisku wielodostępnym użytkownicy powinni uzyskać te ustawienia bezpośrednio z serwera plików za pomocą polecenia **net time** , aby uniknąć rozbieżności w ustawieniach właściwości DateCreated i LastUpdated.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Klasa CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)<br/>
[Klasa CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)

---
description: Dowiedz się więcej o strukturze CDaoIndexInfo —
title: CDaoIndexInfo — Struktura
ms.date: 06/25/2018
f1_keywords:
- CDaoIndexInfo
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
ms.openlocfilehash: 2e09846789dc91e4d0df67665f3e975b557c07c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250767"
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo — Struktura

`CDaoIndexInfo`Struktura zawiera informacje o obiekcie indeksu zdefiniowanym dla obiektów dostępu do danych (DAO).

## <a name="syntax"></a>Składnia

```cpp
struct CDaoIndexInfo {
    CDaoIndexInfo();                    // Constructor
    CString m_strName;                  // Primary
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary
    short m_nFields;                    // Primary
    BOOL m_bPrimary;                    // Secondary
    BOOL m_bUnique;                     // Secondary
    BOOL m_bClustered;                  // Secondary
    BOOL m_bIgnoreNulls;                // Secondary
    BOOL m_bRequired;                   // Secondary
    BOOL m_bForeign;                    // Secondary
    long m_lDistinctCount;              // All

    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

### <a name="parameters"></a>Parametry

*m_strName*<br/>
Unikatowa nazwa obiektu pola. Aby uzyskać szczegółowe informacje, zobacz temat "Nazwa właściwości" w pomocy DAO.

*m_pFieldInfos*<br/>
Wskaźnik do tablicy obiektów [CDaoIndexFieldInfo —](../../mfc/reference/cdaoindexfieldinfo-structure.md) wskazujący, które pola tabledef lub zestawu rekordów są polami klucza w indeksie. Każdy obiekt identyfikuje jedno pole w indeksie. Domyślną kolejnością indeksu jest rosnąco. Obiekt indeksu może mieć jedno lub więcej pól reprezentujących klucze indeksu dla każdego rekordu. Mogą to być rosnące, malejące lub kombinacje.

*m_nFields*<br/>
Liczba pól przechowywanych w `m_pFieldInfos` .

*m_bPrimary*<br/>
Jeśli właściwość podstawowa ma wartość TRUE, obiekt index reprezentuje indeks podstawowy. Indeks podstawowy składa się z co najmniej jednego pola, które jednoznacznie identyfikują wszystkie rekordy w tabeli we wstępnie zdefiniowanej kolejności. Ponieważ pole index musi być unikatowe, właściwość UNIQUE obiektu index jest również ustawiona na wartość TRUE w obiekcie DAO. Jeśli podstawowy indeks składa się z więcej niż jednego pola, każde pole może zawierać zduplikowane wartości, ale każda kombinacja wartości ze wszystkich pól indeksowanych musi być unikatowa. Indeks podstawowy składa się z klucza tabeli i zwykle zawiera te same pola co klucz podstawowy.

Po ustawieniu klucza podstawowego dla tabeli klucz podstawowy jest automatycznie definiowany jako podstawowy indeks tabeli. Aby uzyskać więcej informacji, zobacz temat "Właściwość podstawowa" i "unikatowa Właściwość" w pomocy DAO.

> [!NOTE]
> Może istnieć co najwyżej jeden podstawowy indeks tabeli.

*m_bUnique*<br/>
Wskazuje, czy obiekt indeksu reprezentuje unikatowy indeks dla tabeli. Jeśli ta właściwość ma wartość TRUE, obiekt index reprezentuje indeks, który jest unikatowy. Unikatowy indeks składa się z co najmniej jednego pola, które logicznie Rozmieść wszystkie rekordy w tabeli w unikatowej, wstępnie zdefiniowanej kolejności. Jeśli indeks składa się z jednego pola, wartości w tym polu muszą być unikatowe dla całej tabeli. Jeśli indeks składa się z więcej niż jednego pola, każde pole może zawierać zduplikowane wartości, ale każda kombinacja wartości ze wszystkich pól indeksowanych musi być unikatowa.

Jeśli właściwość UNIQUE i Primary obiektu index ma wartość TRUE, indeks jest unikatowy i podstawowy: jednoznacznie identyfikuje wszystkie rekordy w tabeli we wstępnie zdefiniowanej kolejności logicznej. Jeśli właściwość podstawowa ma wartość FAŁSZ, indeks jest indeksem pomocniczym. Indeksy pomocnicze (Key i nonkey) logicznie układają rekordy we wstępnie zdefiniowanej kolejności bez obsługi jako identyfikatora dla rekordów w tabeli.

Aby uzyskać więcej informacji, zobacz temat "Właściwość podstawowa" i "unikatowa Właściwość" w pomocy DAO.

*m_bClustered*<br/>
Wskazuje, czy obiekt indeksu reprezentuje indeks klastrowany dla tabeli. Jeśli ta właściwość ma wartość TRUE, obiekt index reprezentuje indeks klastrowany. w przeciwnym razie nie. Klastrowany indeks składa się z jednego lub więcej pól nonkey, które razem Rozmieść wszystkie rekordy w tabeli w wstępnie zdefiniowanej kolejności. W przypadku indeksu klastrowanego dane w tabeli są dosłownie przechowywane w kolejności określonej przez indeks klastrowany. Klastrowany indeks zapewnia wydajny dostęp do rekordów w tabeli. Aby uzyskać więcej informacji, zobacz temat "Właściwość klastrowana" w pomocy DAO.

> [!NOTE]
> Właściwość klastrowane jest ignorowana dla baz danych korzystających z aparatu bazy danych Microsoft Jet, ponieważ aparat bazy danych Jet nie obsługuje indeksów klastrowanych.

*m_bIgnoreNulls*<br/>
Wskazuje, czy istnieją wpisy indeksu dla rekordów, które mają wartości null w ich polach indeksu. Jeśli ta właściwość ma wartość TRUE, pola z wartościami null nie mają wpisu indeksu. Aby wyszukiwać rekordy przy użyciu pola szybciej, można zdefiniować indeks dla tego pola. Jeśli zezwolisz na wpisy o wartości null w indeksowanym polu i oczekujesz, że wiele wpisów ma mieć wartość null, można ustawić właściwość IgnoreNulls dla obiektu index na wartość TRUE, aby zmniejszyć ilość miejsca do magazynowania używanego przez indeks. Ustawienie właściwości IgnoreNulls i wymagane ustawienie właściwości razem określają, czy rekord z wartością indeksu null ma wpis indeksu, jak pokazano w poniższej tabeli.

|IgnoreNulls|Wymagane|Wartość null w polu indeksu|
|-----------------|--------------|-------------------------|
|Prawda|Fałsz|Dozwolona wartość null; nie dodano wpisu indeksu.|
|Fałsz|Fałsz|Dozwolona wartość null; dodano wpis indeksu.|
|Prawda lub FAŁSZ|Prawda|Wartość null jest niedozwolona; nie dodano wpisu indeksu.|

Aby uzyskać więcej informacji, zobacz temat "Właściwość IgnoreNulls" w pomocy DAO.

*m_bRequired*<br/>
Wskazuje, czy obiekt indeksu DAO wymaga wartości innej niż null. Jeśli ta właściwość ma wartość TRUE, obiekt indeksu nie zezwala na wartość null. Aby uzyskać więcej informacji, zobacz temat "Właściwość wymagana" w pomocy DAO.

> [!TIP]
> Gdy można ustawić tę właściwość dla obiektu indeksu DAO lub obiektu pola (zawartego w obiekcie tabledef, Recordset lub querydef), należy ustawić go dla obiektu Field. Ważność ustawienia właściwości dla obiektu Field jest sprawdzana przed obiektem indeksu.

*m_bForeign*<br/>
Wskazuje, czy obiekt indeksu reprezentuje klucz obcy w tabeli. Jeśli ta właściwość ma wartość TRUE, indeks reprezentuje klucz obcy w tabeli. Klucz obcy składa się z co najmniej jednego pola w tabeli obcej, która jednoznacznie identyfikuje wiersz w tabeli podstawowej. Aparat bazy danych Microsoft Jet tworzy obiekt indeksu dla tabeli obcej i ustawia właściwość obcą podczas tworzenia relacji, która wymusza integralność referencyjną. Aby uzyskać więcej informacji, zobacz temat "Właściwość obca" w pomocy DAO.

*m_lDistinctCount*<br/>
Wskazuje liczbę unikatowych wartości dla obiektu indeksu, które są zawarte w skojarzonej tabeli. Sprawdź Właściwość DistinctCount, aby określić liczbę unikatowych wartości lub kluczy w indeksie. Każdy klucz jest liczony tylko raz, mimo że może istnieć wiele wystąpień tej wartości, jeśli indeks zezwala na zduplikowane wartości. Te informacje są przydatne w aplikacjach, które próbują zoptymalizować dostęp do danych, oceniając informacje o indeksie. Liczba unikatowych wartości jest również znana jako Kardynalność obiektu indeksu. Właściwość DistinctCount nie zawsze odzwierciedla rzeczywistą liczbę kluczy w konkretnym czasie. Na przykład zmiana spowodowana wycofaniem transakcji nie zostanie natychmiast odzwierciedlona we właściwości DistinctCount. Aby uzyskać więcej informacji, zobacz temat "Właściwość DistinctCount" w pomocy DAO.

## <a name="remarks"></a>Uwagi

Odwołania do elementów podstawowych, pomocniczych i wszystkie powyżej wskazują, jak informacje są zwracane przez `GetIndexInfo` funkcję członkowską w klasach [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) i [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).

Obiekty indeksu nie są reprezentowane przez klasę MFC. Zamiast tego obiekty DAO powiązane z obiektami MFC klasy [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) lub [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) zawierają kolekcję obiektów indeksu o nazwie kolekcja indeksów. Te klasy dostarczają funkcje członkowskie, aby uzyskać dostęp do poszczególnych elementów informacji o indeksie, lub można uzyskać do nich dostęp jednocześnie przy użyciu `CDaoIndexInfo` obiektu, wywołując `GetIndexInfo` funkcję członkowską obiektu zawierającego.

`CDaoIndexInfo` ma Konstruktor i destruktor w celu prawidłowego przydzielenia i cofnięcia przydziału informacji o polu indeksu w `m_pFieldInfos` .

Informacje pobierane przez `GetIndexInfo` funkcję członkowską obiektu tabledef są przechowywane w `CDaoIndexInfo` strukturze. Wywołaj `GetIndexInfo` funkcję członkowską zawierającego obiekt tabledef, w której kolekcje indeksów jest przechowywany obiekt indeksu. `CDaoIndexInfo` definiuje również `Dump` funkcję członkowską w kompilacjach debugowania. Możesz użyć, `Dump` aby zrzucić zawartość `CDaoIndexInfo` obiektu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)

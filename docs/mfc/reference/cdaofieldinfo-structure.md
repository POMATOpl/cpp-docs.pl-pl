---
description: Dowiedz się więcej o strukturze CDaoFieldInfo —
title: CDaoFieldInfo — Struktura
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: 8cb297e767fed023ff7b6c2fe7efe5dd41a1621a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250871"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo — Struktura

`CDaoFieldInfo`Struktura zawiera informacje o obiekcie Field zdefiniowanym dla obiektów dostępu do danych (DAO).

Obiekty DAO są obsługiwane przez pakiet Office 2013. Element DAO 3,6 jest wersją ostateczną i jest uznawany za przestarzały.

## <a name="syntax"></a>Składnia

```
struct CDaoFieldInfo
{
    CString m_strName;           // Primary
    short m_nType;               // Primary
    long m_lSize;                // Primary
    long m_lAttributes;          // Primary
    short m_nOrdinalPosition;    // Secondary
    BOOL m_bRequired;            // Secondary
    BOOL m_bAllowZeroLength;     // Secondary
    long m_lCollatingOrder;      // Secondary
    CString m_strForeignName;    // Secondary
    CString m_strSourceField;    // Secondary
    CString m_strSourceTable;    // Secondary
    CString m_strValidationRule; // All
    CString m_strValidationText; // All
    CString m_strDefaultValue;   // All
};
```

#### <a name="parameters"></a>Parametry

*m_strName*<br/>
Unikatowa nazwa obiektu pola. Aby uzyskać szczegółowe informacje, zobacz temat "Nazwa właściwości" w pomocy DAO.

*m_nType*<br/>
Wartość, która wskazuje typ danych pola. Aby uzyskać szczegółowe informacje, zobacz temat "Type Property" w pomocy DAO. Wartość tej właściwości może być jedną z następujących:

- `dbBoolean` Tak/nie, tak samo jak PRAWDA/FAŁSZ

- `dbByte` Bajc

- `dbInteger` Wybierak

- `dbLong` Długo

- `dbCurrency` Walutowy Zobacz MFC Class [COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle` Wiersz

- `dbDouble` Double

- `dbDate` Data/godzina; Zobacz MFC Class [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText` Opis Zobacz MFC Class [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary` Long Binary (obiekt OLE); Możesz chcieć użyć klasy MFC [CByteArray](../../mfc/reference/cbytearray-class.md) zamiast klasy `CLongBinary` , co jest bardziej `CByteArray` czytelne i łatwiejsze w użyciu.

- `dbMemo` Dana Zobacz MFC — Klasa `CString`

- `dbGUID` Unikatowy identyfikator globalny/uniwersalny unikatowy identyfikator używany z zdalnymi wywołaniami procedur. Aby uzyskać więcej informacji, zobacz temat "Type Property" w pomocy DAO.

> [!NOTE]
> Nie używaj typów danych ciągu dla danych binarnych. Powoduje to, że dane są przekazywane przez warstwę translacji Unicode/ANSI, co zwiększa obciążenie i prawdopodobnie nieoczekiwane tłumaczenie.

*m_lSize*<br/>
Wartość wskazująca maksymalny rozmiar (w bajtach) obiektu pola DAO, który zawiera tekst lub stały rozmiar obiektu Field, który zawiera wartości tekstowe lub liczbowe. Aby uzyskać szczegółowe informacje, zobacz temat "size Property" w pomocy DAO. Rozmiary mogą być jedną z następujących wartości:

|Typ|Rozmiar (w bajtach)|Opis|
|----------|--------------------|-----------------|
|`dbBoolean`|1 bajt|Tak/nie (wartość taka sama jak true/false)|
|`dbByte`|1|Byte|
|`dbInteger`|2|Liczba całkowita|
|`dbLong`|4|Długo|
|`dbCurrency`|8|Waluta ([COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Pojedyncze|
|`dbDouble`|8|Double|
|`dbDate`|8|Data/godzina ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Tekst ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long Binary (obiekt OLE; [CByteArray](../../mfc/reference/cbytearray-class.md); Użyj zamiast `CLongBinary` )|
|`dbMemo`|0|Memo ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|Unikatowy identyfikator globalny/uniwersalny unikatowy identyfikator używany z zdalnymi wywołaniami procedur.|

*m_lAttributes*<br/>
Określa charakterystykę obiektu pola zawartego w obiekcie tabledef, recordset, querydef lub index. Zwracana wartość może być sumą tych stałych, utworzonych za pomocą operatora bitowego lub (**&#124;**) C++:

- `dbFixedField` Rozmiar pola jest stały (domyślnie dla pól liczbowych).

- `dbVariableField` Rozmiar pola to zmienna (tylko pola tekstowe).

- `dbAutoIncrField` Wartość pola dla nowych rekordów jest automatycznie zwiększana do unikatowej długiej liczby całkowitej, której nie można zmienić. Obsługiwane tylko w przypadku tabel bazy danych Microsoft Jet.

- `dbUpdatableField` Wartość pola można zmienić.

- `dbDescending` Pole jest sortowane w kolejności malejącej (Z-A lub 100-0) (dotyczy tylko obiektu Field w kolekcji Fields obiektu index; w MFC obiekty indeksów są same zawarte w obiektach tabledef). Jeśli ta stała zostanie pominięta, pole jest sortowane w kolejności rosnącej (A-Z lub 0-100) (wartość domyślna).

Podczas sprawdzania ustawienia tej właściwości można użyć operatora koniunkcji bitowej C++ ( **&** ) w celu przetestowania określonego atrybutu. Podczas ustawiania wielu atrybutów można połączyć je, łącząc odpowiednie stałe z operatorem bitowym lub (**&#124;**). Aby uzyskać szczegółowe informacje, zobacz temat "Właściwość Attributes" w pomocy DAO.

*m_nOrdinalPosition*<br/>
Wartość określająca kolejność liczbową, w której pole reprezentowane przez obiekt pola DAO ma być wyświetlane względem innych pól. Tę właściwość można ustawić za pomocą [CDaoTableDef:: \ Field](../../mfc/reference/cdaotabledef-class.md#createfield). Aby uzyskać szczegółowe informacje, zobacz temat "Właściwość OrdinalPosition" w pomocy DAO.

*m_bRequired*<br/>
Wskazuje, czy obiekt DAO Field wymaga wartości innej niż null. Jeśli ta właściwość ma wartość TRUE, pole nie zezwala na wartość null. Jeśli jest to wymagane, pole może zawierać wartości null, a także wartości, które spełniają warunki określone przez ustawienia właściwości AllowZeroLength i ValidationRule. Aby uzyskać szczegółowe informacje, zapoznaj się z tematem "Właściwość wymagana" w pomocy DAO. Tę właściwość można ustawić dla elementu tabledef z [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_bAllowZeroLength*<br/>
Wskazuje, czy pusty ciąg ("") jest prawidłową wartością obiektu DAO typu text lub MEMO. Jeśli ta właściwość ma wartość TRUE, pusty ciąg jest prawidłową wartością. Możesz ustawić tę właściwość na wartość FALSE, aby upewnić się, że nie można użyć pustego ciągu do ustawienia wartości pola. Aby uzyskać szczegółowe informacje, zobacz temat "Właściwość AllowZeroLength" w pomocy DAO. Tę właściwość można ustawić dla elementu tabledef z [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_lCollatingOrder*<br/>
Określa sekwencję sortowania w tekście dla porównania ciągów lub sortowania. Aby uzyskać szczegółowe informacje, zobacz temat "Dostosowywanie ustawień rejestru systemu Windows na potrzeby dostępu do danych" w pomocy DAO. Aby uzyskać listę możliwych zwracanych wartości, zobacz `m_lCollatingOrder` element członkowski struktury [CDaoDatabaseInfo —](../../mfc/reference/cdaodatabaseinfo-structure.md) . Tę właściwość można ustawić dla elementu tabledef z [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strForeignName*<br/>
Wartość, która w relacji określa nazwę obiektu DAO Field w tabeli obcej, która odnosi się do pola w tabeli podstawowej. Aby uzyskać szczegółowe informacje, zobacz temat "Właściwość Obcyname" w pomocy DAO.

*m_strSourceField*<br/>
Wskazuje nazwę pola, które jest oryginalnym źródłem danych dla obiektu DAO Field zawartego w obiekcie tabledef, Recordset lub querydef. Ta właściwość wskazuje oryginalną nazwę pola skojarzoną z obiektem pola. Na przykład można użyć tej właściwości, aby określić oryginalne źródło danych w polu zapytania, którego nazwa nie jest powiązana z nazwą pola w tabeli źródłowej. Aby uzyskać szczegółowe informacje, zobacz temat "SourceField, właściwości źródła" w pomocy DAO. Tę właściwość można ustawić dla elementu tabledef z [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strSourceTable*<br/>
Określa nazwę tabeli, która jest pierwotnym źródłem danych dla obiektu DAO Field zawartego w obiekcie tabledef, Recordset lub querydef. Ta właściwość wskazuje oryginalną nazwę tabeli skojarzoną z obiektem Field. Na przykład można użyć tej właściwości, aby określić oryginalne źródło danych w polu zapytania, którego nazwa nie jest powiązana z nazwą pola w tabeli źródłowej. Aby uzyskać szczegółowe informacje, zobacz temat "SourceField, właściwości źródła" w pomocy DAO. Tę właściwość można ustawić dla elementu tabledef z [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strValidationRule*<br/>
Wartość, która sprawdza poprawność danych w polu w miarę ich zmiany lub dodania do tabeli. Aby uzyskać szczegółowe informacje, zobacz temat "Właściwość ValidationRule" w pomocy DAO. Tę właściwość można ustawić dla elementu tabledef z [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#createfield).

Aby uzyskać informacje dotyczące TableDefs, zobacz `m_strValidationRule` element członkowski struktury [CDaoTableDefInfo —](../../mfc/reference/cdaotabledefinfo-structure.md) .

*m_strValidationText*<br/>
Wartość określająca tekst komunikatu wyświetlanego przez aplikację, jeśli wartość obiektu pola DAO nie spełnia reguły walidacji określonej przez ustawienie właściwości ValidationRule. Aby uzyskać szczegółowe informacje, zobacz temat "Właściwość ValidationText" w pomocy DAO. Tę właściwość można ustawić dla elementu tabledef z [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strDefaultValue*<br/>
Wartość domyślna obiektu DAO. Po utworzeniu nowego rekordu ustawienie właściwości DefaultValue jest automatycznie wprowadzane jako wartość pola. Aby uzyskać szczegółowe informacje, zobacz temat "właściwość DefaultValue" w pomocy DAO. Tę właściwość można ustawić dla elementu tabledef z [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#createfield).

## <a name="remarks"></a>Uwagi

Odwołania do podstawowych, pomocniczych i wszystkie powyżej wskazują, jak informacje są zwracane przez `GetFieldInfo` funkcję elementu członkowskiego w klasach [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)i [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).

Obiekty Field nie są reprezentowane przez klasę MFC. Zamiast tego obiekty DAO powiązane z obiektami MFC następujących klas zawierają kolekcje obiektów Field: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)i [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Te klasy dostarczają funkcje członkowskie, aby uzyskać dostęp do niektórych poszczególnych elementów informacji o polach, lub możesz uzyskać do nich dostęp jednocześnie przy użyciu `CDaoFieldInfo` obiektu, wywołując `GetFieldInfo` funkcję członkowską obiektu zawierającego.

Oprócz użycia do badania właściwości obiektu, można również użyć `CDaoFieldInfo` do konstruowania parametru wejściowego do tworzenia nowych pól w tabledef. Prostsze opcje są dostępne dla tego zadania, ale jeśli potrzebujesz bardziej precyzyjnej kontroli, możesz użyć wersji [CDaoTableDef:: Onfield](../../mfc/reference/cdaotabledef-class.md#createfield) , która przyjmuje `CDaoFieldInfo` parametr.

Informacje pobierane przez `GetFieldInfo` funkcję członkowską (klasy zawierającej pole) są przechowywane w `CDaoFieldInfo` strukturze. Wywołaj `GetFieldInfo` funkcję członkowską zawierającego obiekt, w której Kolekcja pól jest przechowywana. `CDaoFieldInfo` definiuje również `Dump` funkcję członkowską w kompilacjach debugowania. Możesz użyć, `Dump` aby zrzucić zawartość `CDaoFieldInfo` obiektu.

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdao. h

## <a name="see-also"></a>Zobacz też

[Struktury, style, wywołania zwrotne i mapy komunikatów](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef:: GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset:: GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef:: GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)

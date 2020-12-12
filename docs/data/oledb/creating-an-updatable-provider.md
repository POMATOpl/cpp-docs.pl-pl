---
description: 'Dowiedz się więcej na temat: Tworzenie aktualizowalnego dostawcy'
title: Tworzenie aktualizowalnego dostawcy
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 948b50f5e49ca8288e5fcf1ada75ae07d4a8b39f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305419"
---
# <a name="creating-an-updatable-provider"></a>Tworzenie aktualizowalnego dostawcy

Visual C++ obsługuje aktualizowalnych dostawców lub dostawców, którzy mogą aktualizować (zapisywać w) magazyn danych. W tym temacie omówiono sposób tworzenia aktualizowalnych dostawców przy użyciu szablonów OLE DB.

W tym temacie założono, że rozpoczynasz pracę od dostawcy. Istnieją dwa kroki umożliwiające utworzenie aktualizowalnego dostawcy. Najpierw należy zdecydować, w jaki sposób dostawca wprowadzi zmiany do magazynu danych; w odróżnieniu od tego, czy zmiany mają zostać wykonane natychmiast, czy odroczone do momentu wystawienia polecenia aktualizacji. Sekcja "[Tworzenie dostawców aktualizowalnych](#vchowmakingprovidersupdatable)" zawiera opis zmian i ustawień, które należy wykonać w kodzie dostawcy.

Następnie musisz upewnić się, że dostawca zawiera wszystkie funkcje do obsługi wszystkich elementów, których może żądać klient. Jeśli odbiorca chce zaktualizować magazyn danych, dostawca musi zawierać kod, który utrzymuje dane w magazynie danych. Na przykład można użyć biblioteki C Run-Time lub MFC do wykonania takich operacji na źródle danych. Sekcja "[Zapisywanie do źródła danych](#vchowwritingtothedatasource)" zawiera opis sposobu zapisywania do źródła danych, działania z wartościami domyślnymi oraz ustawiania flag kolumn.

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) jest przykładem aktualizowalnego dostawcy. UpdatePV jest taka sama jak MyProv, ale z aktualizowalną obsługą.

## <a name="making-providers-updatable"></a><a name="vchowmakingprovidersupdatable"></a> Tworzenie aktualizowalnych dostawców

Klucz służący do aktualizowania dostawcy zawiera informacje o operacjach, które mają być wykonywane przez dostawcę w magazynie danych, oraz o tym, w jaki sposób dostawca ma wykonywać te operacje. Istotny problem polega na tym, czy aktualizacje magazynu danych mają zostać wykonane natychmiastowo, czy odroczone (wsadowe) do momentu wygenerowania polecenia aktualizacji.

Najpierw należy zdecydować, czy dziedziczyć z `IRowsetChangeImpl` lub `IRowsetUpdateImpl` w klasie zestawu wierszy. W zależności od tego, który z tych ustawień zostanie wdrożony, wpłynie to na funkcjonalność trzech metod: `SetData` , `InsertRows` , i `DeleteRows` .

- W przypadku dziedziczenia z [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), wywołanie tych trzech metod natychmiast zmienia magazyn danych.

- W przypadku dziedziczenia z [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)metody odkładają zmiany do magazynu danych do momentu wywołania `Update` , `GetOriginalData` , lub `Undo` . Jeśli aktualizacja obejmuje kilka zmian, są one wykonywane w trybie wsadowym (należy zauważyć, że zmiany wsadowe mogą zwiększyć znaczne obciążenie pamięci).

Zwróć uwagę, że `IRowsetUpdateImpl` pochodzi od `IRowsetChangeImpl` . W ten sposób `IRowsetUpdateImpl` oferuje możliwość zmiany możliwości i możliwości przetwarzania wsadowego.

### <a name="to-support-updatability-in-your-provider"></a>Aby obsłużyć możliwość aktualizacji w dostawcy

1. W klasie zestawu wierszy Dziedzicz z `IRowsetChangeImpl` lub `IRowsetUpdateImpl` . Te klasy zapewniają odpowiednie interfejsy umożliwiające zmianę magazynu danych:

   **Dodawanie IRowsetChange**

   Dodaj `IRowsetChangeImpl` do łańcucha dziedziczenia przy użyciu tego formularza:

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   Dodaj również `COM_INTERFACE_ENTRY(IRowsetChange)` do `BEGIN_COM_MAP` sekcji w klasie zestawu wierszy.

   **Dodawanie IRowsetUpdate**

   Dodaj `IRowsetUpdate` do łańcucha dziedziczenia przy użyciu tego formularza:

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > Wiersz należy usunąć `IRowsetChangeImpl` z łańcucha dziedziczenia. Ten jeden wyjątek do dyrektywy wymienionej wcześniej musi zawierać kod dla `IRowsetChangeImpl` .

1. Dodaj następujący obiekt do mapy COM ( `BEGIN_COM_MAP ... END_COM_MAP` ):

   |  W przypadku zaimplementowania   |           Dodaj do mapy COM             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | W przypadku zaimplementowania | Dodaj do mapy zestawu właściwości |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. W poleceniu Dodaj następujące elementy do mapy zestawu właściwości ( `BEGIN_PROPSET_MAP ... END_PROPSET_MAP` ):

   |  W przypadku zaimplementowania   |                                             Dodaj do mapy zestawu właściwości                                              |
   |---------------------|------------------------------------------------------------------------------------------------------------------|
   | `IRowsetChangeImpl` |                            `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`                             |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. Na mapie zestawu właściwości należy również uwzględnić wszystkie poniższe ustawienia, które znajdują się poniżej:

    ```cpp
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)

    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)
    ```

   Wartości używane w tych wywołaniach makr można znaleźć, wyszukując w ATLDB. h identyfikatory właściwości i wartości (jeśli ATLDB. h różni się od dokumentacji online, ATLDB. h zastępuje dokumentację).

   > [!NOTE]
   > Wiele z `VARIANT_FALSE` ustawień i `VARIANT_TRUE` jest wymaganych przez szablony OLE DB. Specyfikacja OLE DB mówi, że mogą one mieć Odczyt/zapis, ale szablony OLE DB mogą obsługiwać tylko jedną wartość.

   **W przypadku zaimplementowania IRowsetChangeImpl**

   W przypadku zaimplementowania programu `IRowsetChangeImpl` należy ustawić następujące właściwości dostawcy. Te właściwości są używane przede wszystkim do żądania interfejsów przez `ICommandProperties::SetProperties` .

   - `DBPROP_IRowsetChange`: Ustawianie tych zestawów automatycznie `DBPROP_IRowsetChange` .

   - `DBPROP_UPDATABILITY`: Maska bitów określająca obsługiwane metody w `IRowsetChange` : `SetData` , `DeleteRows` , lub `InsertRow` .

   - `DBPROP_CHANGEINSERTEDROWS`: Konsument może wywołać `IRowsetChange::DeleteRows` lub `SetData` dla nowo wstawionych wierszy.

   - `DBPROP_IMMOBILEROWS`: Zestaw wierszy nie zmieni kolejności wstawionych lub zaktualizowanych wierszy.

   **W przypadku zaimplementowania IRowsetUpdateImpl**

   W przypadku zaimplementowania programu `IRowsetUpdateImpl` należy ustawić następujące właściwości dostawcy, oprócz ustawienia wszystkich właściwości `IRowsetChangeImpl` wymienionych wcześniej:

   - `DBPROP_IRowsetUpdate`.

   - `DBPROP_OWNINSERT`: Musi być READ_ONLY i VARIANT_TRUE.

   - `DBPROP_OWNUPDATEDELETE`: Musi być READ_ONLY i VARIANT_TRUE.

   - `DBPROP_OTHERINSERT`: Musi być READ_ONLY i VARIANT_TRUE.

   - `DBPROP_OTHERUPDATEDELETE`: Musi być READ_ONLY i VARIANT_TRUE.

   - `DBPROP_REMOVEDELETED`: Musi być READ_ONLY i VARIANT_TRUE.

   - `DBPROP_MAXPENDINGROWS`.

   > [!NOTE]
   > Jeśli obsługujesz powiadomienia, możesz również mieć inne właściwości. Zapoznaj się z sekcją na `IRowsetNotifyCP` tej liście.

## <a name="writing-to-the-data-source"></a><a name="vchowwritingtothedatasource"></a> Zapisywanie w źródle danych

Aby odczytać ze źródła danych, wywołaj `Execute` funkcję. Aby zapisać w źródle danych, wywołaj `FlushData` funkcję. (W ogólnym sensie opróżnianie oznacza zapisanie wprowadzonych zmian w tabeli lub indeksie na dysku).

```cpp
FlushData(HROW, HACCESSOR);
```

Argumenty uchwytów wiersza (HROW) i dojście metody dostępu (HACCESSOR) umożliwiają określenie regionu do zapisu. Zwykle można napisać pojedyncze pole danych jednocześnie.

`FlushData`Metoda zapisuje dane w formacie, w którym były pierwotnie przechowywane. Jeśli ta funkcja nie zostanie zastąpiona, dostawca będzie działać prawidłowo, ale zmiany nie zostaną opróżnione do magazynu danych.

### <a name="when-to-flush"></a>Kiedy należy opróżniać

Szablony dostawcy wywołują FlushData za każdym razem, gdy dane muszą zostać zapisane w magazynie danych. zwykle (ale nie zawsze) występuje w wyniku wywołań następujących funkcji:

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows` (jeśli istnieją nowe dane do wstawienia w wierszu)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>Jak to działa

Konsument wykonuje wywołanie, które wymaga opróżniania (na przykład aktualizacji), a to wywołanie jest przesyłane do dostawcy, który zawsze wykonuje następujące czynności:

- Wywołuje `SetDBStatus` się, gdy masz powiązana wartość stanu.

- Sprawdza flagi kolumn.

- Wywołania `IsUpdateAllowed` .

Te trzy kroki pomagają zapewnić bezpieczeństwo. Następnie jest wywoływany dostawca `FlushData` .

### <a name="how-to-implement-flushdata"></a>Jak zaimplementować FlushData

Aby zaimplementować `FlushData` , należy wziąć pod uwagę kilka problemów:

Upewnij się, że magazyn danych może obsłużyć zmiany.

Obsługa wartości NULL.

### <a name="handling-default-values"></a>Obsługa wartości domyślnych.

Aby zaimplementować własną `FlushData` metodę, musisz:

- Przejdź do klasy zestawu wierszy.

- W klasie zestawu wierszy należy umieścić deklarację:

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- Podaj implementację programu `FlushData` .

Dobrą implementacją jest `FlushData` przechowywanie tylko wierszy i kolumn, które są faktycznie aktualizowane. Możesz użyć parametrów HROW i HACCESSOR, aby określić bieżący wiersz i kolumnę przechowywane do optymalizacji.

Zazwyczaj największe wyzwanie działa z własnym natywnym magazynem danych. Jeśli to możliwe, spróbuj wykonać następujące polecenie:

- Zachowaj metodę zapisu w magazynie danych, jak to możliwe.

- Obsługuj wartości NULL (opcjonalne, ale zalecane).

- Obsługuj wartości domyślne (opcjonalne, ale zalecane).

Najlepszym zadaniem do wykonania jest posiadanie wartości NULL i domyślnych wartości w magazynie danych. Jest to najlepsze rozwiązanie, jeśli można ekstrapolację tych danych. Jeśli nie, zaleca się, aby nie zezwalać na wartości NULL i domyślne.

Poniższy przykład pokazuje, jak `FlushData` jest zaimplementowany w `RUpdateRowset` klasie w `UpdatePV` przykładzie (zobacz Rowset. h w przykładowym kodzie):

```cpp
///////////////////////////////////////////////////////////////////////////
// class RUpdateRowset (in rowset.h)
...
HRESULT FlushData(HROW, HACCESSOR)
{
    ATLTRACE2(atlTraceDBProvider, 0, "RUpdateRowset::FlushData\n");

    USES_CONVERSION;
    enum {
        sizeOfString = 256,
        sizeOfFileName = MAX_PATH
    };
    FILE*    pFile = NULL;
    TCHAR    szString[sizeOfString];
    TCHAR    szFile[sizeOfFileName];
    errcode  err = 0;

    ObjectLock lock(this);

    // From a filename, passed in as a command text,
    // scan the file placing data in the data array.
    if (m_strCommandText == (BSTR)NULL)
    {
        ATLTRACE( "RRowsetUpdate::FlushData -- "
                  "No filename specified\n");
        return E_FAIL;
    }

    // Open the file
    _tcscpy_s(szFile, sizeOfFileName, OLE2T(m_strCommandText));
    if ((szFile[0] == _T('\0')) ||
        ((err = _tfopen_s(&pFile, &szFile[0], _T("w"))) != 0))
    {
        ATLTRACE("RUpdateRowset::FlushData -- Could not open file\n");
        return DB_E_NOTABLE;
    }

    // Iterate through the row data and store it.
    for (long l=0; l<m_rgRowData.GetSize(); l++)
    {
        CAgentMan am = m_rgRowData[l];

        _putw((int)am.dwFixed, pFile);

        if (_tcscmp(&am.szCommand[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szCommand2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);
    }

    if (fflush(pFile) == EOF || fclose(pFile) == EOF)
    {
        ATLTRACE("RRowsetUpdate::FlushData -- "
                 "Couldn't flush or close file\n");
    }

    return S_OK;
}
```

### <a name="handling-changes"></a>Obsługa zmian

Aby Twój dostawca obsługiwał zmiany, najpierw musisz upewnić się, że magazyn danych (na przykład plik tekstowy lub plik wideo) zawiera funkcje, które umożliwiają wprowadzanie zmian na tym komputerze. Jeśli tak nie jest, należy utworzyć ten kod niezależnie od projektu dostawcy.

### <a name="handling-null-data"></a>Obsługa danych o wartości NULL

Istnieje możliwość, że użytkownik końcowy wyśle dane o wartości NULL. Gdy zapisujesz wartości NULL do pól w źródle danych, mogą występować potencjalne problemy. Wyobraź sobie, że aplikacja do tworzenia zamówień akceptuje wartości dla miasta i kodu pocztowego; może akceptować jedną lub obie wartości, ale nie nie, ponieważ w takim przypadku dostarczenie może być niemożliwe. W związku z tym należy ograniczyć niektóre kombinacje wartości NULL w polach, które mają sens dla aplikacji.

Jako deweloper dostawcy musisz wziąć pod uwagę, jak będą przechowywane te dane, w jaki sposób odczytywać te dane z magazynu danych i jak określać użytkownika. W tym celu należy rozważyć zmianę stanu danych zestawu wierszy w źródle danych (na przykład DataStatus = NULL). Użytkownik wybiera wartość zwracaną, gdy konsument uzyskuje dostęp do pola zawierającego wartość NULL.

Przyjrzyj się kodowi z przykładu UpdatePV; ilustruje sposób, w jaki dostawca może obsłużyć dane o wartości NULL. W UpdatePV Dostawca przechowuje dane o wartości NULL, pisząc ciąg "NULL" w magazynie danych. Gdy odczytuje dane o wartości NULL z magazynu danych, zobaczy ten ciąg, a następnie opróżnia bufor, tworząc ciąg o wartości NULL. Ma również przesłonięcie, `IRowsetImpl::GetDBStatus` w którym zwraca DBSTATUS_S_ISNULL, jeśli ta wartość danych jest pusta.

### <a name="marking-nullable-columns"></a>Oznaczanie kolumn dopuszczających wartości null

W przypadku implementacji również zestawów wierszy schematu (zobacz `IDBSchemaRowsetImpl` ) implementacja powinna być określona w zestawie wierszy DBSCHEMA_COLUMNS (zwykle oznaczony w dostawcy przez CxxxSchemaColSchemaRowset), że kolumna dopuszcza wartość null.

Należy również określić, że wszystkie kolumny wartości null zawierają wartość DBCOLUMNFLAGS_ISNULLABLE w używanej wersji programu `GetColumnInfo` .

W implementacji szablonów OLE DB, jeśli nie można oznaczyć kolumn jako nullable, dostawca zakłada, że muszą zawierać wartość i nie zezwoli konsumentowi na wysyłanie wartości null.

Poniższy przykład pokazuje, jak `CommonGetColInfo` Funkcja jest zaimplementowana w CUpdateCommand (zobacz UpProvRS. cpp) w UpdatePV. Zwróć uwagę, jak kolumny mają ten DBCOLUMNFLAGS_ISNULLABLE w przypadku kolumn dopuszczających wartości null.

```cpp
/////////////////////////////////////////////////////////////////////////////
// CUpdateCommand (in UpProvRS.cpp)

ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols, bool bBookmark)
{
    static ATLCOLUMNINFO _rgColumns[6];
    ULONG ulCols = 0;

    if (bBookmark)
    {
        ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,
                            sizeof(DWORD), DBTYPE_BYTES,
                            0, 0, GUID_NULL, CAgentMan, dwBookmark,
                            DBCOLUMNFLAGS_ISBOOKMARK)
        ulCols++;
    }

    // Next set the other columns up.
    // Add a fixed length entry for OLE DB conformance testing purposes
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Fixed"), 1, 4, DBTYPE_UI4,
                        10, 255, GUID_NULL, CAgentMan, dwFixed,
                        DBCOLUMNFLAGS_WRITE |
                        DBCOLUMNFLAGS_ISFIXEDLENGTH)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command"), 2, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text"), 3, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command2"), 4, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text2"), 5, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    if (pcCols != NULL)
    {
        *pcCols = ulCols;
    }

    return _rgColumns;
}
```

### <a name="default-values"></a>Wartości domyślne

Podobnie jak w przypadku danych o wartości NULL, użytkownik jest odpowiedzialny za wprowadzanie zmian wartości domyślnych.

Wartość domyślna `FlushData` i `Execute` ma zwrócić S_OK. W związku z tym, jeśli ta funkcja nie zostanie zastąpiona, zmiany pojawią się po pomyślnym (S_OK zostaną zwrócone), ale nie zostaną przesłane do magazynu danych.

W `UpdatePV` przykładzie (w Rowset. h) `SetDBStatus` Metoda obsługuje wartości domyślne w następujący sposób:

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* pdbStatus, CSimpleRow* pRow,
                            ATLCOLUMNINFO* pColInfo)
{
    ATLASSERT(pRow != NULL && pColInfo != NULL && pdbStatus != NULL);

    void* pData = NULL;
    char* pDefaultData = NULL;
    DWORD* pFixedData = NULL;

    switch (*pdbStatus)
    {
        case DBSTATUS_S_DEFAULT:
            pData = (void*)&m_rgRowData[pRow->m_iRowset];
            if (pColInfo->wType == DBTYPE_STR)
            {
                pDefaultData = (char*)pData + pColInfo->cbOffset;
                strcpy_s(pDefaultData, "Default");
            }
            else
            {
                pFixedData = (DWORD*)((BYTE*)pData +
                                          pColInfo->cbOffset);
                *pFixedData = 0;
                return S_OK;
            }
            break;
        case DBSTATUS_S_ISNULL:
        default:
            break;
    }
    return S_OK;
}
```

### <a name="column-flags"></a>Flagi kolumn

Jeśli w kolumnach są obsługiwane wartości domyślne, należy ustawić je za pomocą metadanych w \<provider class\> klasie SchemaRowset. Ustaw `m_bColumnHasDefault = VARIANT_TRUE` .

Istnieje również odpowiedzialność za ustawienie flag kolumn, które są określone za pomocą typu wyliczeniowego DBCOLUMNFLAGS. Flagi kolumn opisują właściwości kolumn.

Na przykład w `CUpdateSessionColSchemaRowset` klasie w `UpdatePV` (w sesji. h) pierwsza kolumna jest skonfigurowana w następujący sposób:

```cpp
// Set up column 1
trData[0].m_ulOrdinalPosition = 1;
trData[0].m_bIsNullable = VARIANT_FALSE;
trData[0].m_bColumnHasDefault = VARIANT_TRUE;
trData[0].m_nDataType = DBTYPE_UI4;
trData[0].m_nNumericPrecision = 10;
trData[0].m_ulColumnFlags = DBCOLUMNFLAGS_WRITE |
                            DBCOLUMNFLAGS_ISFIXEDLENGTH;
lstrcpyW(trData[0].m_szColumnDefault, OLESTR("0"));
m_rgRowData.Add(trData[0]);
```

Ten kod określa między innymi, że kolumna obsługuje wartość domyślną 0, którą można zapisywalne i że wszystkie dane w kolumnie mają tę samą długość. Jeśli chcesz, aby dane w kolumnie miały długość zmiennej, nie ustawisz tej flagi.

## <a name="see-also"></a>Zobacz też

[Tworzenie dostawcy OLE DB](creating-an-ole-db-provider.md)

---
description: 'Dowiedz się więcej o: odczytywanie ciągów do dostawcy OLE DB'
title: Wczytywanie ciągów do dostawcy OLE DB
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
ms.openlocfilehash: 5df8812d5589dd457684bf5e36a8a49f798f99aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286634"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>Wczytywanie ciągów do dostawcy OLE DB

`CCustomRowset::Execute`Funkcja otwiera plik i odczytuje ciągi. Odbiorca przekazuje nazwę pliku do dostawcy przez wywołanie [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)). Dostawca otrzymuje nazwę pliku i zapisuje ją w zmiennej składowej `m_strCommandText` . `Execute` odczytuje nazwę pliku z `m_strCommandText` . Jeśli nazwa pliku jest nieprawidłowa lub plik jest niedostępny, `Execute` zwraca błąd. W przeciwnym razie otwiera plik i wywołuje, `fgets` Aby pobrać ciągi. Dla każdego zestawu ciągów, które odczytuje, `Execute` tworzy wystąpienie rekordu użytkownika (zmodyfikowane `CCustomWindowsFile` przy [przechowywaniu ciągów w dostawcy OLE DB](../../data/oledb/storing-strings-in-the-ole-db-provider.md)) i umieszcza je w tablicy.

Jeśli nie można otworzyć pliku, `Execute` należy zwrócić DB_E_NOTABLE. Jeśli zwróci E_FAIL zamiast tego, dostawca nie będzie mógł współpracować z wieloma użytkownikami i nie przekaże OLE DB [testów zgodności](../../data/oledb/testing-your-provider.md).

## <a name="example"></a>Przykład

```cpp
/////////////////////////////////////////////////////////////////////////
// CustomRS.h
class CCustomRowset : public CRowsetImpl< CCustomRowset, CCustomWindowsFile, CCustomCommand>
{
public:
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
    {
        enum {
            sizeOfBuffer = 256,
            sizeOfFile = MAX_PATH
        };
        USES_CONVERSION;
        FILE* pFile = NULL;
        TCHAR szString[sizeOfBuffer];
        TCHAR szFile[sizeOfFile];
        size_t nLength;

        ObjectLock lock(this);

        // From a filename, passed in as a command text, scan the file
        // placing data in the data array.
        if (!m_strCommandText)
        {
            ATLTRACE("No filename specified");
            return E_FAIL;
        }

        // Open the file
        _tcscpy_s(szFile, sizeOfFile, m_strCommandText);
        if (szFile[0] == _T('\0') ||
            (fopen_s(&pFile, (char*)&szFile[0], "r") == 0))
        {
            ATLTRACE("Could not open file");
            return DB_E_NOTABLE;
        }

        // Scan and parse the file.
        // The file should contain two strings per record
        LONG cFiles = 0;
        while (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
        {
            nLength = strnlen((char*)szString, sizeOfBuffer);
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF
            CCustomWindowsFile am;
            _tcscpy_s(am.szCommand, am.iSize, szString);
            _tcscpy_s(am.szCommand2, am.iSize, szString);

            if (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
            {
                nLength = strnlen((char*)szString, sizeOfBuffer);
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF
                _tcscpy_s(am.szText, am.iSize, szString);
                _tcscpy_s(am.szText2, am.iSize, szString);
            }

            am.dwBookmark = ++cFiles;
            if (!m_rgRowData.Add(am))
            {
                ATLTRACE("Couldn't add data to array");
                fclose(pFile);
                return E_FAIL;
            }
        }

        if (pcRowsAffected != NULL)
            *pcRowsAffected = cFiles;
        return S_OK;
    }
};
```

Po wykonaniu tej czynności dostawca powinien być gotowy do skompilowania i uruchomienia. Do przetestowania dostawcy potrzebny jest klient z pasującymi funkcjami. [Zaimplementowanie prostego konsumenta](../../data/oledb/implementing-a-simple-consumer.md) pokazuje, jak utworzyć takiego konsumenta testowego. Uruchom konsumenta testowego u dostawcy i sprawdź, czy konsument testowy pobiera odpowiednie ciągi od dostawcy.

Po pomyślnym przetestowaniu dostawcy warto zwiększyć jego funkcjonalność, implementując dodatkowe interfejsy. Przykład jest przedstawiony w temacie [ulepszanie prostego dostawcy Read-Only](../../data/oledb/enhancing-the-simple-read-only-provider.md).

## <a name="see-also"></a>Zobacz też

[Implementowanie prostego dostawcy Read-Only](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>

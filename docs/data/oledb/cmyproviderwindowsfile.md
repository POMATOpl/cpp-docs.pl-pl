---
description: 'Dowiedz się więcej na temat: CCustomWindowsFile'
title: CCustomWindowsFile
ms.date: 10/22/2018
f1_keywords:
- cmyproviderwindowsfile
- ccustomwindowsfile
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
- CCustomWindowsFile class
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
ms.openlocfilehash: c0df2840b68a350f9d65102fdf0a962681edefd9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170402"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

Kreator tworzy klasę, która ma jeden wiersz danych. w tym przypadku jest on wywoływany `CCustomWindowsFile` . Poniższy kod dla programu `CCustomWindowsFile` jest generowany przez kreatora i zawiera listę wszystkich plików w katalogu przy użyciu `WIN32_FIND_DATA` struktury. `CCustomWindowsFile` dziedziczy ze `WIN32_FIND_DATA` struktury:

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

class CCustomWindowsFile:
   public WIN32_FIND_DATA
{
public:
BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()
};
```

`CCustomWindowsFile` jest nazywana [klasą rekordów użytkownika](../../data/oledb/user-record.md) , ponieważ ma również mapę opisującą kolumny w zestawie wierszy dostawcy. Mapa kolumn dostawcy zawiera jeden wpis dla każdego pola w zestawie wierszy przy użyciu makr PROVIDER_COLUMN_ENTRY. Makra określają nazwę kolumny, porządkową i przesunięcie do wpisu struktury. Wpisy kolumny dostawcy w powyższym kodzie zawierają przesunięcia do `WIN32_FIND_DATA` struktury. W przypadku wywołania przez klienta `IRowset::GetData` dane są przesyłane w jednym ciągłym buforze. Zamiast wykonywać operacje arytmetyczne wskaźnika, Mapa umożliwia określenie elementu członkowskiego danych.

`CCustomRowset`Klasa zawiera również `Execute` metodę. `Execute` jest to, co faktycznie odczytuje dane ze źródła natywnego. Poniższy kod przedstawia metodę wygenerowaną przez kreatora `Execute` . Funkcja używa Win32 `FindFirstFile` i `FindNextFile` interfejsów API do pobierania informacji o plikach w katalogu i umieszcza je w wystąpieniach `CCustomWindowsFile` klasy.

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
{
   USES_CONVERSION;
   BOOL bFound = FALSE;
   HANDLE hFile;
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :
       OLE2T(m_strCommandText);
   CCustomWindowsFile wf;
   hFile = FindFirstFile(szDir, &wf);
   if (hFile == INVALID_HANDLE_VALUE)
      return DB_E_ERRORSINCOMMAND;
   LONG cFiles = 1;
   BOOL bMoreFiles = TRUE;
   while (bMoreFiles)
   {
      if (!m_rgRowData.Add(wf))
         return E_OUTOFMEMORY;
      bMoreFiles = FindNextFile(hFile, &wf);
      cFiles++;
   }
   FindClose(hFile);
   if (pcRowsAffected != NULL)
      *pcRowsAffected = cFiles;
   return S_OK;
}
```

Katalog do przeszukania jest pokazywany przez program `m_strCommandText` ; zawiera on tekst reprezentowany przez `ICommandText` interfejs w obiekcie Command. Jeśli katalog nie zostanie określony, zostanie użyty bieżący katalog.

Metoda tworzy jeden wpis dla każdego pliku (odpowiadającego wierszowi) i umieszcza go w `m_rgRowData` elemencie członkowskim danych. `CRowsetImpl`Klasa definiuje `m_rgRowData` element członkowski danych. Dane w tej tablicy są wyświetlane w całej tabeli i są używane w szablonach.

## <a name="see-also"></a>Zobacz też

[Pliki Wizard-Generated dostawcy](../../data/oledb/provider-wizard-generated-files.md)<br/>

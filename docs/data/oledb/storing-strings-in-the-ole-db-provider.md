---
description: 'Dowiedz się więcej o: Przechowywanie ciągów w dostawcy OLE DB'
title: Przechowywanie ciągów w dostawcy OLE DB
ms.date: 05/09/2019
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
ms.openlocfilehash: d5a0fc7160f09d1a8b385b83481cc6fa9009f582
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316703"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Przechowywanie ciągów w dostawcy OLE DB

> [!NOTE]
> Kreator dostawcy OLE DB ATL nie jest dostępny w programie Visual Studio 2019 i nowszych.

W *niestandardowym* RS. h **kreator dostawcy ATL OLE DB** tworzy domyślny rekord użytkownika o nazwie `CWindowsFile` . Aby obsłużyć dwa ciągi, zmodyfikuj, `CWindowsFile` jak pokazano w poniższym kodzie:

```cpp
////////////////////////////////////////////////////////////////////////
class CCustomWindowsFile:
   public WIN32_FIND_DATA
{
public:
DWORD dwBookmark;
static const int iSize = 256;    // Add this
TCHAR szCommand[iSize];          // Add this
TCHAR szText[iSize];             // Add this
TCHAR szCommand2[iSize];         // Add this
TCHAR szText2[iSize];            // Add this

BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)

   PROVIDER_COLUMN_ENTRY_STR("Command", 6, szCommand)    // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text", 7, szText)          // Add this
   PROVIDER_COLUMN_ENTRY_STR("Command2", 8, szCommand2)  // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text2", 9, szText2)        // Add this
END_PROVIDER_COLUMN_MAP()

   bool operator==(const CCustomWindowsFile& am) // This is optional
   {
      return (lstrcmpi(cFileName, am.cFileName) == 0);
   }
};
```

Elementy członkowskie danych `szCommand` i `szText` reprezentują dwa ciągi z `szCommand2` i `szText2` z dodatkowymi kolumnami w razie konieczności. Element członkowski danych `dwBookmark` nie jest potrzebny dla tego prostego dostawcy tylko do odczytu, ale jest używany później do dodawania `IRowsetLocate` interfejsu; zobacz [ulepszanie prostego dostawcy tylko do odczytu](../../data/oledb/enhancing-the-simple-read-only-provider.md). `==`Operator porównuje wystąpienia (implementowanie tego operatora jest opcjonalne).

Gdy to zrobisz, możesz dodać funkcję [odczytywania ciągów do dostawcy OLE DB](../../data/oledb/reading-strings-into-the-ole-db-provider.md).

## <a name="see-also"></a>Zobacz też

[Implementowanie prostego dostawcy Read-Only](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>

---
description: 'Dowiedz się więcej o: rekord użytkownika'
title: Rekord użytkownika
ms.date: 05/09/2019
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
ms.openlocfilehash: f858660800391eff45cb88115f8fb09afa26a77f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272503"
---
# <a name="user-record"></a>Rekord użytkownika

> [!NOTE]
> Kreator dostawcy OLE DB ATL nie jest dostępny w programie Visual Studio 2019 i nowszych.

Rekord użytkownika zawiera kod i strukturę danych, które reprezentują dane kolumn dla zestawu wierszy. Rekord użytkownika można utworzyć w czasie kompilacji lub w czasie wykonywania. Podczas tworzenia dostawcy za pomocą **kreatora ATL OLE DB Provider** Kreator tworzy domyślny rekord użytkownika, który będzie wyglądać następująco (przy założeniu, że określono nazwę dostawcy [short name] *w przypadku elementu webprovider)*:

```cpp
class CWindowsFile:
   public WIN32_FIND_DATA
{
public:
  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()
  
};
```

Szablony dostawcy OLE DB obsługują wszystkie OLE DB specyficzne dla interakcji z klientem programu. Aby uzyskać dane kolumny potrzebne do odpowiedzi, dostawca wywołuje `GetColumnInfo` funkcję, którą należy umieścić w rekordzie użytkownika. Można jawnie przesłonić `GetColumnInfo` rekord użytkownika, na przykład przez zadeklarowanie go w pliku h, jak pokazano poniżej:

```cpp
template <class T>
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)
```

Jest to równe:

```cpp
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)
```

Następnie Zaimplementuj `GetColumnInfo` w pliku. cpp rekordu użytkownika.

Makra PROVIDER_COLUMN_MAP ułatwiają tworzenie `GetColumnInfo` funkcji:

- BEGIN_PROVIDER_COLUMN_MAP definiuje prototyp funkcji i tablicę statyczną `ATLCOLUMNINFO` struktur.

- PROVIDER_COLUMN_ENTRY definiuje i inicjuje pojedynczy `ATLCOLUMNINFO` .

- END_PROVIDER_COLUMN_MAP zamyka tablicę i funkcję. Umieszcza również liczbę elementów tablicy w parametrze *pcCols* .

Gdy rekord użytkownika jest tworzony w czasie wykonywania, program `GetColumnInfo` używa parametru *pThis* , aby otrzymać wskaźnik do zestawu wierszy lub polecenia. Polecenia i zestawy wierszy muszą obsługiwać `IColumnsInfo` interfejs, dlatego można pobrać informacje o kolumnie z tego wskaźnika.

`CommandClass` i `RowsetClass` są poleceniem i zestawem wierszy, który używa rekordu użytkownika.

Aby zapoznać się z bardziej szczegółowym przykładem sposobu przesłonięcia `GetColumnInfo` rekordu użytkownika, zobacz [dynamiczne Określanie kolumn zwracanych do konsumenta](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Zobacz też

[Architektura szablonu dostawcy OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>

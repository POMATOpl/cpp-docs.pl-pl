---
title: FILE_TYPE_CODE Wyliczenie
description: Zestaw SDK usługi Build Insights w wersji C++ FILE_TYPE_CODE odwołanie.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ddd625829e94786c0daddf0e78b914e225b2ecfb
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921026"
---
# <a name="file_type_code-enum"></a>FILE_TYPE_CODE Wyliczenie

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`FILE_TYPE_CODE`Wyliczenie opisuje typ pliku.

## <a name="members"></a>Elementy członkowskie

| Nazwa | Wartość | Opis |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x00000000) | Typ pliku niewymieniony w tym wyliczeniu. |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | Plik obiektu ( \* . obj). |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | Plik wykonywalny ( \* exe) lub dll ( \* . dll). |
| `FILE_TYPE_CODE_LIB` | 3 (0x00000003) | Plik biblioteki statycznej (*. lib). |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x00000004) | Biblioteka importu (*. lib) |
| `FILE_TYPE_CODE_EXP` | 5 (0x00000005) | Plik eksportu (*. EXP). |

## <a name="remarks"></a>Uwagi

::: moniker-end

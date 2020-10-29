---
title: Struktura FILE_DATA
description: Informacje o strukturze FILE_DATA zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a03c2c47be82fac2ee036a632e4df775f6c4f5f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923597"
---
# <a name="file_data-structure"></a>Struktura FILE_DATA

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`FILE_DATA`Struktura opisuje dane wejściowe lub wyjściowe.

## <a name="syntax"></a>Składnia

```cpp
typedef struct FILE_DATA_TAG
{
    const wchar_t*      Path;
    int                 TypeCode;

} FILE_DATA;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `Path` | Ścieżka bezwzględna pliku |
| `TypeCode` | Kod opisujący typ pliku. Aby uzyskać więcej informacji, zobacz [FILE_TYPE_CODE](file-type-code-enum.md). |

::: moniker-end

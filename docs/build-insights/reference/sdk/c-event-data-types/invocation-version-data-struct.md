---
title: Struktura INVOCATION_VERSION_DATA
description: Informacje o strukturze INVOCATION_VERSION_DATA zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ebed659ade4610b50ae06f2a32851522073a58d8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923557"
---
# <a name="invocation_version_data-structure"></a>Struktura INVOCATION_VERSION_DATA

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`INVOCATION_VERSION_DATA`Struktura opisuje numer wersji jako grupę wartości całkowitych.

## <a name="syntax"></a>Składnia

```cpp
typedef struct INVOCATION_VERSION_DATA_TAG
{
    unsigned short VersionMajor;
    unsigned short VersionMinor;
    unsigned short BuildNumberMajor;
    unsigned short BuildNumberMinor;

} INVOCATION_VERSION_DATA;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `VersionMajor` | Numer główny wersji. |
| `VersionMinor` | Numer pomocniczy wersji. |
| `BuildNumberMajor` | Numer główny kompilacji. |
| `BuildNumberMinor` | Numer pomocniczy kompilacji. |

::: moniker-end

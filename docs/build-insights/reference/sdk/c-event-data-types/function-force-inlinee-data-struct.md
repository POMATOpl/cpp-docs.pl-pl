---
title: Struktura FUNCTION_FORCE_INLINEE_DATA
description: Informacje o strukturze FUNCTION_FORCE_INLINEE_DATA zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_FORCE_INLINEE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e9de87bdc4e5a1a3e25483f8ba1766609c7d7622
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923573"
---
# <a name="function_force_inlinee_data-structure"></a>Struktura FUNCTION_FORCE_INLINEE_DATA

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`FUNCTION_FORCE_INLINEE_DATA`Struktura opisuje funkcję wymuszoną.

## <a name="syntax"></a>Składnia

```cpp
typedef struct FUNCTION_FORCE_INLINEE_DATA_TAG
{
    const char*         Name;
    unsigned short      Size;

} FUNCTION_FORCE_INLINEE_DATA;
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `Name` | Nazwa funkcji zakodowana w formacie UTF-8. |
| `Size` | Rozmiar funkcji, jako szereg instrukcji pośrednich. |

::: moniker-end

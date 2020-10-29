---
title: OnBeginEndPassFunc typedef
description: Odwołanie do zestawu SDK usługi Build Insights OnBeginEndPassFunc.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnBeginEndPassFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2a97ae792392e5cc0dc83bab00a92d05609a4815
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922487"
---
# <a name="onbeginendpassfunc-typedef"></a>OnBeginEndPassFunc typedef

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`OnBeginEndPassFunc`Element typedef jest jednym z podpisów funkcji używanych w strukturach [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) i [RELOG_CALLBACKS](relog-callbacks-struct.md) .

## <a name="syntax"></a>Składnia

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnBeginEndPassFunc)(
    void*                           callbackContext);
```

## <a name="members"></a>Elementy członkowskie

| Nazwa | Opis |
|--|--|
| `callbackContext` |  |

::: moniker-end

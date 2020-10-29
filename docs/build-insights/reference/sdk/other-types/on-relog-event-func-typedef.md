---
title: OnRelogEventFunc typedef
description: Odwołanie do zestawu SDK usługi Build Insights OnRelogEventFunc.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnRelogEventFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ed639ab59b900f97d29dc69240e45b2f52f2f3b3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919751"
---
# <a name="onrelogeventfunc-typedef"></a>OnRelogEventFunc typedef

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`OnRelogEventFunc`Element typedef jest jednym z podpisów funkcji używanych w strukturze [RELOG_CALLBACKS](relog-callbacks-struct.md) .

## <a name="syntax"></a>Składnia

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnRelogEventFunc)(
    const EVENT_COLLECTION_DATA*    eventStack,
    const void*                     relogSession,
    void*                           callbackContext);
```

### <a name="parameters"></a>Parametry

*eventStack*\
Stos zdarzeń dla bieżącego zdarzenia. Aby uzyskać więcej informacji na stosach zdarzeń, zobacz [zdarzenia](../event-table.md).

*relogSession*\
Wskaźnik sesji rejestrowania do użycia podczas wywoływania [InjectEvent](../functions/inject-event.md).

*callbackContext*\
Wartość kontekstu ustawiona dla tego wywołania zwrotnego w [RELOG_DESCRIPTOR](analysis-descriptor-struct.md).

### <a name="return-value"></a>Wartość zwracana

Wartość [CALLBACK_CODE](callback-code-enum.md) , która kontroluje, co powinno się stać dalej.

::: moniker-end

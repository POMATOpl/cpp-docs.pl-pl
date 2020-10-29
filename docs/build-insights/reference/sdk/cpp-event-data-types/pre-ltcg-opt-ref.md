---
title: Klasa PreLTCGOptRef
description: Odwołanie do klasy PreLTCGOptRef zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- PreLTCGOptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6786e317f0221126ec6e15c50f3fad58c5982266
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923014"
---
# <a name="preltcgoptref-class"></a>Klasa PreLTCGOptRef

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`PreLTCGOptRef`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) .

## <a name="syntax"></a>Składnia

```cpp
class PreLTCGOptRef : public Activity
{
public:
    PreLTCGOptRef(const RawEvent& event);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [działania](activity.md) `PreLTCGOptRef` Klasa zawiera następujących członków:

### <a name="constructors"></a>Konstruktory

[PreLTCGOptRef](#pre-ltcg-opt-ref)

## <a name="preltcgoptref"></a><a name="pre-ltcg-opt-ref"></a> PreLTCGOptRef

```cpp
PreLTCGOptRef(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) .

::: moniker-end

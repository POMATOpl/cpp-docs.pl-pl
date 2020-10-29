---
title: Thread — Klasa
description: Odwołanie do klasy wątku zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Thread
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a483536281aaa87a169a40473fe3f0c4ad10bc96
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922941"
---
# <a name="thread-class"></a>Thread — Klasa

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`Thread`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go do dopasowania zdarzenia [wątku](../event-table.md#thread) .

## <a name="syntax"></a>Składnia

```cpp
class Thread : public Activity
{
public:
    Thread(const RawEvent& event);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [działania](activity.md) `Thread` Klasa zawiera następujących członków:

### <a name="constructors"></a>Konstruktory

[Nici](#thread)

## <a name="thread"></a><a name="thread"></a> Nici

```cpp
Thread(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [wątku](../event-table.md#thread) .

::: moniker-end

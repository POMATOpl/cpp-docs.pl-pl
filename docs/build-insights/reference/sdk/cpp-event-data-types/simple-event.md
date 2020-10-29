---
title: Klasa SimpleEvent
description: Odwołanie do klasy SimpleEvent zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dc09a279157482089adedc660395feaa98376dae
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923001"
---
# <a name="simpleevent-class"></a>Klasa SimpleEvent

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`SimpleEvent`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj jej do dopasowania dowolnego prostego zdarzenia. Zapoznaj się z [tabelą zdarzeń](../event-table.md) , aby wyświetlić wszystkie zdarzenia, które mogą być dopasowane przez `SimpleEvent` klasę.

## <a name="syntax"></a>Składnia

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [zdarzenia](event.md) `SimpleEvent` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[SimpleEvent](#simple-event)

## <a name="simpleevent"></a><a name="simple-event"></a> SimpleEvent

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Każde proste zdarzenie.

::: moniker-end

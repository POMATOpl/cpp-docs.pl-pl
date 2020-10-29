---
title: Klasa FrontEndFileGroup
description: Odwołanie do klasy FrontEndFileGroup zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFileGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 902b394f645030fed4eeb79bae79535e6d246a1f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923229"
---
# <a name="frontendfilegroup-class"></a>Klasa FrontEndFileGroup

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`FrontEndFileGroup`Klasa jest używana z funkcjami [MatchEventStack](../functions/match-event-stack.md) i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować grupy zdarzeń [FRONT_END_FILE](../event-table.md#front-end-file) .

## <a name="syntax"></a>Składnia

```cpp
class FrontEndFileGroup : public EventGroup<FrontEndFile>
{
public:
    FrontEndFileGroup(std::deque<FrontEndFile>&& group);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [eventObject \<FrontEndFile\> ](event-group.md) `FrontEndFileGroup` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[FrontEndFileGroup](#front-end-file-group)

## <a name="frontendfilegroup"></a><a name="front-end-file-group"></a> FrontEndFileGroup

```cpp
FrontEndFileGroup(std::deque<FrontEndFile>&& group);
```

### <a name="parameters"></a>Parametry

*Group*\
Grupa zdarzeń [FRONT_END_FILE](../event-table.md#front-end-file) .

::: moniker-end

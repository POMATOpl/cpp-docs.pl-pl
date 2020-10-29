---
title: Klasa konsolidatora
description: Odwołanie do klasy konsolidatora zestawu SDK usługi kompilacja dla języka C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8a818cf7524405d4e2f29a1987e93b77371607cc
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923117"
---
# <a name="linkergroup-class"></a>Klasa konsolidatora

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`LinkerGroup`Klasa jest używana z funkcjami [MatchEventStack](../functions/match-event-stack.md) i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować grupy zdarzeń [konsolidatora](../event-table.md#linker) .

## <a name="syntax"></a>Składnia

```cpp
class LinkerGroup : public EventGroup<Linker>
{
public:
    LinkerGroup(std::deque<Linker>&& group);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [eventObject \<Linker\> ](event-group.md) `LinkerGroup` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[LinkerGroup](#linker-group)

## <a name="linkergroup"></a><a name="linker-group"></a> Konsolidator

```cpp
LinkerGroup(std::deque<Linker>&& group);
```

### <a name="parameters"></a>Parametry

*Group*\
Grupa zdarzeń [konsolidatora](../event-table.md#linker) .

::: moniker-end

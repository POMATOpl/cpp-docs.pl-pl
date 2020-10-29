---
title: Klasa wywołania
description: Odwołanie do klasy wywołania zestawu SDK usługi kompilacja dla języka C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InvocationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a8d4786a228ab25551ee36ce22637d44dc07307
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920635"
---
# <a name="invocationgroup-class"></a>Klasa wywołania

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`InvocationGroup`Klasa jest używana z funkcjami [MatchEventStack](../functions/match-event-stack.md) i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go do dopasowania grup zawierających mieszanie zdarzeń [kompilatora](../event-table.md#compiler) i [konsolidatora](../event-table.md#linker) .

## <a name="syntax"></a>Składnia

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [eventObject \<Invocation\> ](event-group.md) `InvocationGroup` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[InvocationGroup](#invocation-group)

## <a name="invocationgroup"></a><a name="invocation-group"></a> Wywołanie

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>Parametry

*Group*\
Grupa zawierająca kombinację zdarzeń [kompilatora](../event-table.md#compiler) i [konsolidatora](../event-table.md#linker) .

::: moniker-end

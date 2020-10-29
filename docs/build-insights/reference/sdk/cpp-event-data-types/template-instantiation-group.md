---
title: Klasa TemplateInstantiationGroup
description: Odwołanie do klasy TemplateInstantiationGroup zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bacd48fbf15bfbbd768b527f42587425fb0932e6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922973"
---
# <a name="templateinstantiationgroup-class"></a>Klasa TemplateInstantiationGroup

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`TemplateInstantiationGroup`Klasa jest używana z funkcjami [MatchEventStack](../functions/match-event-stack.md) i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować grupy zdarzeń [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) .

## <a name="syntax"></a>Składnia

```cpp
class TemplateInstantiationGroup : public EventGroup<TemplateInstantiation>
{
public:
    TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [eventObject \<TemplateInstantiation\> ](event-group.md) `TemplateInstantiationGroup` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[TemplateInstantiationGroup](#template-instantiation-group)

## <a name="templateinstantiationgroup"></a><a name="template-instantiation-group"></a> TemplateInstantiationGroup

```cpp
TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
```

### <a name="parameters"></a>Parametry

*Group*\
Grupa zdarzeń [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) .

::: moniker-end

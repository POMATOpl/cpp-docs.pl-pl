---
title: Function — Klasa
description: Odwołanie do klasy funkcji zestawu SDK w usłudze C++ build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Function
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 874477b9ca31095bfcf4ba3c7a6fd220dc073415
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920648"
---
# <a name="function-class"></a>Function — Klasa

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`Function`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj jej do dopasowania zdarzenia [funkcji](../event-table.md#function) .

## <a name="syntax"></a>Składnia

```cpp
class Function : public Activity
{
public:
    Function(const RawEvent& event);

    const char* Name() const;
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [działania](activity.md) `Function` Klasa zawiera następujących członków:

### <a name="constructors"></a>Konstruktory

[Funkcja](#function)

### <a name="functions"></a>Funkcje

[Nazwa](#name)

## <a name="function"></a><a name="function"></a> Funkcyjn

```cpp
Function(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [funkcji](../event-table.md#function) .

## <a name="name"></a><a name="name"></a> Nazwij

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Wartość zwracana

Nazwa funkcji zakodowana w formacie UTF-8.

::: moniker-end

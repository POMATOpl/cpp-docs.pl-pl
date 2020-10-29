---
title: Klasa Pass1
description: Odwołanie do klasy Pass1 zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass1
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 99ada8a2db5ac464113d9805797d4b4555367e77
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923041"
---
# <a name="pass1-class"></a>Klasa Pass1

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`Pass1`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go do dopasowania zdarzenia [PASS1](../event-table.md#pass1) .

## <a name="syntax"></a>Składnia

```cpp
class Pass1 : public LinkerPass
{
public:
    Pass1(const RawEvent& event);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy bazowej [LinkerPass](linker-pass.md) `Pass1` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[Pass1](#pass1)

## <a name="pass1"></a><a name="pass1"></a> Pass1

```cpp
Pass1(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [PASS1](../event-table.md#pass1) .

::: moniker-end

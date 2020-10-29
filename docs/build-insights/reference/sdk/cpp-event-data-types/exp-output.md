---
title: Klasa ExpOutput
description: Odwołanie do klasy ExpOutput zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExpOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f0e467466c344be0c6c796dd7cc168e6ff49d4c9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923287"
---
# <a name="expoutput-class"></a>Klasa ExpOutput

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`ExpOutput`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [EXP_OUTPUT](../event-table.md#exp-output) .

## <a name="syntax"></a>Składnia

```cpp
class ExpOutput : public FileOutput
{
public:
    ExpOutput(const RawEvent& event);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy bazowej [FileOutput](file-output.md) `ExpOutput` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[ExpOutput](#exp-output)

## <a name="expoutput"></a><a name="exp-output"></a> ExpOutput

```cpp
ExpOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [EXP_OUTPUT](../event-table.md#exp-output) .

::: moniker-end

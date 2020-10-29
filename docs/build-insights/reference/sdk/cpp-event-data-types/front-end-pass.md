---
title: Klasa FrontEndPass
description: Odwołanie do klasy FrontEndPass zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c2959b1b80163819287b1907c9d25ca75aa5bbc2
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923208"
---
# <a name="frontendpass-class"></a>Klasa FrontEndPass

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`FrontEndPass`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [FRONT_END_PASS](../event-table.md#front-end-pass) .

## <a name="syntax"></a>Składnia

```cpp
class FrontEndPass : public CompilerPass
{
public:
    FrontEndPass(const RawEvent& event);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy bazowej [CompilerPass](compiler-pass.md) `FrontEndPass` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[FrontEndPass](#front-end-pass)

## <a name="frontendpass"></a><a name="front-end-pass"></a> FrontEndPass

```cpp
FrontEndPass(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [FRONT_END_PASS](../event-table.md#front-end-pass) .

::: moniker-end

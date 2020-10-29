---
title: Konsolidator — Klasa
description: Odwołanie do klasy konsolidatora zestawu SDK usługi kompilacja dla języka C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Linker
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: cf5544d725c12db8962d888944d4a281387207fa
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923093"
---
# <a name="linker-class"></a>Konsolidator — Klasa

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`Linker`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [konsolidatora](../event-table.md#linker) .

## <a name="syntax"></a>Składnia

```cpp
class Linker : public Invocation
{
public:
    Linker(const RawEvent& event);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy podstawowej [wywołania](invocation.md) `Linker` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[Konsolidator](#linker)

## <a name="linker"></a><a name="linker"></a> Konsolidatora

```cpp
Linker(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [konsolidatora](../event-table.md#linker) .

::: moniker-end

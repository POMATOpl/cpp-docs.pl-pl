---
title: Klasa ImpLibOutput
description: Odwołanie do klasy ImpLibOutput zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ImpLibOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 01adb0041a3d212acf1bb846ced9019600016cda
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923178"
---
# <a name="impliboutput-class"></a>Klasa ImpLibOutput

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`ImpLibOutput`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output) .

## <a name="syntax"></a>Składnia

```cpp
class ImpLibOutput : public FileOutput
{
public:
    ImpLibOutput(const RawEvent& event);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy bazowej [FileOutput](file-output.md) `ImpLibOutput` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[ImpLibOutput](#imp-lib-output)

## <a name="impliboutput"></a><a name="imp-lib-output"></a> ImpLibOutput

```cpp
ImpLibOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output) .

::: moniker-end

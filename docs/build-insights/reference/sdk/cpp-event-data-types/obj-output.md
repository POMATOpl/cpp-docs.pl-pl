---
title: Klasa ObjOutput
description: Odwołanie do klasy ObjOutput zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ObjOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5c88ed6f1faa307d90a73104d3183adc8e50c542
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923059"
---
# <a name="objoutput-class"></a>Klasa ObjOutput

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`ObjOutput`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować zdarzenie [OBJ_OUTPUT](../event-table.md#obj-output) .

## <a name="syntax"></a>Składnia

```cpp
class ObjOutput : public FileOutput
{
public:
    ObjOutput(const RawEvent& event);
};
```

## <a name="members"></a>Elementy członkowskie

Wraz z dziedziczonymi elementami członkowskimi z klasy bazowej [FileOutput](file-output.md) `ObjOutput` Klasa zawiera następujące elementy członkowskie:

### <a name="constructors"></a>Konstruktory

[ObjOutput](#obj-output)

## <a name="objoutput"></a><a name="obj-output"></a> ObjOutput

```cpp
ObjOutput(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Zdarzenie [OBJ_OUTPUT](../event-table.md#obj-output) .

::: moniker-end

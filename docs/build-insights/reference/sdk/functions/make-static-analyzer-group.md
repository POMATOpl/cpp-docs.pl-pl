---
title: MakeStaticAnalyzerGroup
description: Dokumentacja funkcji MakeStaticAnalyzerGroup zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d7ddb8652400438c38882b1d27e635e8f1e8db51
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920245"
---
# <a name="makestaticanalyzergroup"></a>MakeStaticAnalyzerGroup

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`MakeStaticAnalyzerGroup`Funkcja służy do tworzenia statycznej grupy analizatorów, która może być przenoszona do funkcji, takich jak [`Analyze`](analyze.md) lub [`Relog`](relog.md) . Członkowie grupy analizatora odbierają zdarzenia jeden od lewej do prawej, dopóki wszystkie zdarzenia w śladach nie zostaną przeanalizowane.

## <a name="syntax"></a>Składnia

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>Parametry

*TAnalyzerPtrs*\
Ten parametr jest zawsze wywnioskowany.

*Analizatory*\
Pakiet parametrów [`IAnalyzer`](../other-types/ianalyzer-class.md) wskaźników uwzględnionych w grupie analizatorów statycznych. Te wskaźniki mogą być surowe, `std::unique_ptr` lub `std::shared_ptr` .

### <a name="return-value"></a>Wartość zwracana

Statyczna Grupa analizatorów. Użyj **`auto`** słowa kluczowego, aby przechwycić wartość zwracaną.

## <a name="remarks"></a>Uwagi

W przeciwieństwie do grup analizatorów dynamicznych, członkowie grupy analizatorów statycznych muszą być znani w czasie kompilacji. Ponadto statyczna Grupa analizatora zawiera [`IAnalyzer`](../other-types/ianalyzer-class.md) wskaźniki, które nie mają zachowań polimorficznych. W przypadku używania statycznej grupy analizatorów do analizowania śledzenia zdarzeń dla systemu Windows (ETW), wywołania `IAnalyzer` interfejsu zawsze są rozpoznawane do obiektu bezpośrednio wskazywanego przez członka grupy analizatora. Ta utrata elastyczności zapewnia szybszy czas przetwarzania zdarzeń. Jeśli członkowie grupy analizatorów nie mogą być znani w czasie kompilacji lub jeśli wymagane jest zachowanie polimorficzne `IAnalyzer` wskaźników, rozważ użycie dynamicznej grupy analizatorów. Aby użyć dynamicznej grupy analizatora, zamiast tego wywołaj metodę [`MakeDynamicAnalyzerGroup`](make-static-analyzer-group.md) .

::: moniker-end

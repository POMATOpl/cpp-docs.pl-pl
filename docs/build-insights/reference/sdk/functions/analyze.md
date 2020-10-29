---
title: Analiza
description: Odwołanie do funkcji analizy zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5e593b690231adf6f04161f9c3ff6aef3217f9ef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920323"
---
# <a name="analyze"></a>Analiza

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`Analyze`Funkcja służy do analizowania śladu śledzenia zdarzeń systemu Windows (ETW) uzyskanego z MSVC podczas śledzenia kompilacji C++. Zdarzenia w śledzeniu ETW są przekazywane sekwencyjnie do grupy analizatorów dostarczonej przez wywołującego. Ta funkcja obsługuje analizy wieloetapowe umożliwiające przekazywanie strumienia zdarzeń do grupy analizatorów wiele razy w wierszu.

## <a name="syntax"></a>Składnia

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const char*                                   inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const wchar_t*                                inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>Parametry

*TAnalyzerGroupMembers*\
Ten parametr jest zawsze wywnioskowany.

*inputLogFile*\
Wejściowy ślad ETW, z którego mają być odczytywane zdarzenia.

*numberOfPasses*\
Liczba przebiegów analizy do uruchomienia na danych wejściowych śledzenia. Śledzenie jest przekazywane przez podaną grupę analizatora raz na przebieg analizy.

*Analizator*\
Grupa analizatorów użyta do analizy. Wywołaj [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) , aby utworzyć grupę analizatorów. Aby użyć dynamicznej grupy analizatora uzyskanej z [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md), należy najpierw hermetyzować ją wewnątrz statycznej grupy analizatorów, przekazując jej adres do `MakeStaticAnalyzerGroup` .

### <a name="return-value"></a>Wartość zwracana

Kod wyniku z wyliczenia [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end

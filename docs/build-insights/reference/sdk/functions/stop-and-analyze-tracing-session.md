---
title: StopAndAnalyzeTracingSession
description: Dokumentacja funkcji StopAndAnalyzeTracingSession zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 81a8ce43ecedfa51874508193637969411ae52d6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922712"
---
# <a name="stopandanalyzetracingsession"></a>StopAndAnalyzeTracingSession

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndAnalyzeTracingSession`Funkcja przerywa trwającą sesję śledzenia i zapisuje wynikowy ślad w pliku tymczasowym. Sesja analizy jest następnie natychmiast uruchamiana przy użyciu pliku tymczasowego jako dane wejściowe. Pliki wykonywalne wywołujące tę funkcję muszą mieć uprawnienia administratora.

## <a name="syntax"></a>Składnia

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const char*                                   sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const wchar_t*                                sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>Parametry

*sessionName*\
Nazwa sesji śledzenia, która ma zostać zatrzymana. Użyj tej samej nazwy sesji, która została przeniesiona do [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md)lub [StartTracingSessionW](start-tracing-session-w.md).

*numberOfAnalysisPasses*\
Liczba przebiegów analizy do uruchomienia w śladzie. Śledzenie jest przekazywane przez podaną grupę analizatora raz na przebieg analizy.

*Statystyki*\
Wskaźnik do obiektu [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopAndAnalyzeTracingSession` zapisuje statystyki kolekcji śledzenia w tym obiekcie przed zwróceniem.

*Analizator*\
Grupa analizatorów użyta do analizy. Wywołaj [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) , aby utworzyć grupę analizatorów. Jeśli chcesz użyć dynamicznej grupy analizatora uzyskanej z [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md), najpierw Hermetyzuj ją wewnątrz statycznej grupy analizatorów, przekazując jej adres do `MakeStaticAnalyzerGroup` .

### <a name="return-value"></a>Wartość zwracana

Kod wyniku z wyliczenia [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end

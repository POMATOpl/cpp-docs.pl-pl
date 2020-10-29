---
title: StopAndRelogTracingSession
description: Dokumentacja funkcji StopAndRelogTracingSession zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d36dee1b16ca467d16b22587abe3ef34ee6ccb29
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919959"
---
# <a name="stopandrelogtracingsession"></a>StopAndRelogTracingSession

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndRelogTracingSession`Funkcja przerywa trwającą sesję śledzenia i zapisuje wynikowy ślad w pliku tymczasowym. Sesja ponownej rejestracji jest natychmiast uruchamiana przy użyciu pliku tymczasowego jako dane wejściowe. Ostatni zarejestrowany rejestr utworzony przez sesję rejestrowania jest zapisywany w pliku określonym przez obiekt wywołujący. Pliki wykonywalne wywołujące tę funkcję muszą mieć uprawnienia administratora.

## <a name="syntax"></a>Składnia

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const char*                                   sessionName,
    const char*                                   outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const wchar_t*                                sessionName,
    const wchar_t*                                outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>Parametry

*sessionName*\
Nazwa sesji śledzenia, która ma zostać zatrzymana. Użyj tej samej nazwy sesji, która została przeniesiona do [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md)lub [StartTracingSessionW](start-tracing-session-w.md).

*outputLogFile*\
Plik, w którym ma zostać zapisany zarejestrowany ponownie ślad utworzony przez sesję ponownego rejestrowania.

*Statystyki*\
Wskaźnik do obiektu [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopAndRelogTracingSession` zapisuje statystyki kolekcji śledzenia w tym obiekcie przed zwróceniem.

*numberOfAnalysisPasses*\
Liczba przebiegów analizy do uruchomienia w śladzie. Śledzenie jest przekazywane przez podaną grupę analizatora raz na przebieg analizy.

*systemEventsRetentionFlags*\
[RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md) maski bitowej, która określa, które systemowe zdarzenia ETW zachować w rejestrowanym śladzie.

*Analizator*\
Grupa analizatorów używana dla fazy analizy sesji rejestrowania. Wywołaj [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) , aby utworzyć grupę analizatorów. Jeśli chcesz użyć dynamicznej grupy analizatora uzyskanej z [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md), najpierw Hermetyzuj ją wewnątrz statycznej grupy analizatorów, przekazując jej adres do `MakeStaticAnalyzerGroup` .

*rejestratora*\
Grupa ponownego rejestrowania, która rejestruje zdarzenia do pliku śledzenia określonego w *outputLogFile* . Wywołaj [MakeStaticReloggerGroup](make-static-relogger-group.md) , aby utworzyć grupę modułu rejestrującego. Jeśli chcesz użyć dynamicznej grupy ponownego rejestrowania uzyskanej z [MakeDynamicReloggerGroup](make-dynamic-relogger-group.md), najpierw Hermetyzuj ją wewnątrz statycznej grupy rejestrowania, przechodząc do adresu `MakeStaticReloggerGroup` .

### <a name="return-value"></a>Wartość zwracana

Kod wyniku z wyliczenia [RESULT_CODE](../other-types/result-code-enum.md) .

### <a name="remarks"></a>Uwagi

Śledzenie danych wejściowych jest przesyłane przez grupę analizatora *numberOfAnalysisPasses* razy. Nie ma podobnej opcji do rejestrowania przebiegów. Śledzenie jest przekazywane trough grupę rejestratorów tylko raz, po ukończeniu wszystkich przebiegów analizy.

Rejestrowanie zdarzeń systemowych, takich jak przykłady procesora CPU z klasy rerejestratora, nie jest obsługiwane. Użyj parametru *systemEventsRetentionFlags* , aby określić, które zdarzenia systemowe mają być przechowywane w wyniku śledzenia danych wyjściowych.

::: moniker-end

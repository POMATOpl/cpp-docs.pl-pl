---
title: StopTracingSessionA
description: Dokumentacja funkcji StopTracingSessionA zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 211538c1756d41b91dab6d43f33f4b4a41ceb70c
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922652"
---
# <a name="stoptracingsessiona"></a>StopTracingSessionA

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`StopTracingSessionA`Funkcja przerywa trwającą sesję śledzenia i tworzy Nieprzetworzony plik śledzenia. Nieprzetworzone pliki śledzenia można przesłać do funkcji [Analizuj](analyze.md), [AnalzeA](analyze-a.md)i [AnalyzeW](analyze-w.md) , aby rozpocząć sesję analizy. Nieprzetworzone pliki śledzenia można także przesłać do funkcji [relog](relog.md), [RelogA](relog-a.md)i [RelogW](relog-w.md) w celu rozpoczęcia ponownego rejestrowania sesji. Wywołanie plików wykonywalnych `StopTracingSessionA` musi mieć uprawnienia administratora.

## <a name="syntax"></a>Składnia

```cpp
enum RESULT_CODE StopTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>Parametry

*sessionName*\
Nazwa sesji śledzenia, która ma zostać zatrzymana. Użyj tej samej nazwy sesji, która została przeniesiona do [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md)lub [StartTracingSessionW](start-tracing-session-w.md).

*outputLogFile*\
Ścieżka do końcowego pliku dziennika wyjściowego, w którym ma zostać zapisany nieprzetworzony wynik śledzenia.

*Statystyki*\
Wskaźnik do obiektu [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopTracingSessionA` zapisuje statystyki kolekcji śledzenia w tym obiekcie przed zwróceniem.

### <a name="return-value"></a>Wartość zwracana

Kod wyniku z wyliczenia [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end

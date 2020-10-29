---
title: StopAndAnalyzeTracingSessionA
description: Dokumentacja funkcji StopAndAnalyzeTracingSessionA zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fa5adfca2c5e4d3d4bd17abae4e78c2ac6464773
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922727"
---
# <a name="stopandanalyzetracingsessiona"></a>StopAndAnalyzeTracingSessionA

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndAnalyzeTracingSessionA`Funkcja przerywa trwającą sesję śledzenia i zapisuje wynikowy ślad w pliku tymczasowym. Sesja analizy jest następnie natychmiast uruchamiana przy użyciu pliku tymczasowego jako dane wejściowe. Pliki wykonywalne wywołujące tę funkcję muszą mieć uprawnienia administratora.

## <a name="syntax"></a>Składnia

```cpp
enum RESULT_CODE StopAndAnalyzeTracingSessionA(
    const char*                 sessionName,
    TRACING_SESSION_STATISTICS* statistics,
    const ANALYSIS_DESCRIPTOR*  analysisDescriptor);
```

### <a name="parameters"></a>Parametry

*sessionName*\
Nazwa sesji śledzenia, która ma zostać zatrzymana. Użyj tej samej nazwy sesji, która została przeniesiona do [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md)lub [StartTracingSessionW](start-tracing-session-w.md).

*Statystyki*\
Wskaźnik do obiektu [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopAndAnalyzeTracingSessionA` zapisuje statystyki kolekcji śledzenia w tym obiekcie przed zwróceniem.

*analysisDescriptor*\
Wskaźnik do obiektu [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) . Ten obiekt służy do konfigurowania sesji analizy, która jest uruchamiana przez program `StopAndAnalyzeTracingSessionA` .

### <a name="return-value"></a>Wartość zwracana

Kod wyniku z wyliczenia [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end

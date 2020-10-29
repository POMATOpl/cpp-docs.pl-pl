---
title: StopAndRelogTracingSessionW
description: Dokumentacja funkcji StopAndRelogTracingSessionW zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9c39607b9d088be18fb24238428512be09d78c53
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922683"
---
# <a name="stopandrelogtracingsessionw"></a>StopAndRelogTracingSessionW

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndRelogTracingSessionW`Funkcja przerywa trwającą sesję śledzenia i zapisuje wynikowy ślad w pliku tymczasowym. Sesja ponownej rejestracji jest natychmiast uruchamiana przy użyciu pliku tymczasowego jako dane wejściowe. Ostatni zarejestrowany rejestr utworzony przez sesję rejestrowania jest zapisywany w pliku określonym przez obiekt wywołujący. Pliki wykonywalne wywołujące tę funkcję muszą mieć uprawnienia administratora.

## <a name="syntax"></a>Składnia

```cpp
enum RESULT_CODE StopAndRelogTracingSessionW(
    const wchar_t*              sessionName,
    const wchar_t*              outputLogFile,
    TRACING_SESSION_STATISTICS* statistics,
    const RELOG_DESCRIPTOR*     relogDescriptor);
```

### <a name="parameters"></a>Parametry

*sessionName*\
Nazwa sesji śledzenia, która ma zostać zatrzymana. Użyj tej samej nazwy sesji, która została przeniesiona do [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md)lub [StartTracingSessionW](start-tracing-session-w.md).

*outputLogFile*\
Plik, w którym ma zostać zapisany zarejestrowany ponownie ślad utworzony przez sesję ponownego rejestrowania.

*Statystyki*\
Wskaźnik do obiektu [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) . `StopAndRelogTracingSessionW` zapisuje statystyki kolekcji śledzenia w tym obiekcie przed zwróceniem.

*analysisDescriptor*\
Wskaźnik do obiektu [RELOG_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) . Użyj tego obiektu, aby skonfigurować sesję ponownego rejestrowania uruchomioną przez program `StopAndRelogTracingSessionW` .

### <a name="return-value"></a>Wartość zwracana

Kod wyniku z wyliczenia [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end

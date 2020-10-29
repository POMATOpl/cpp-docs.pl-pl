---
title: StartTracingSessionW
description: Dokumentacja funkcji StartTracingSessionW zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StartTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d89bd6d040f9786539c9be08b9da0813d3bb2c82
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922741"
---
# <a name="starttracingsessionw"></a>StartTracingSessionW

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`StartTracingSessionW`Funkcja uruchamia sesję śledzenia. Pliki wykonywalne wywołujące tę funkcję muszą mieć uprawnienia administratora.

## <a name="syntax"></a>Składnia

```cpp
enum RESULT_CODE StartTracingSessionW(
    const wchar_t*                 sessionName,
    const TRACING_SESSION_OPTIONS* options);
```

### <a name="parameters"></a>Parametry

*sessionName*\
Nazwa sesji śledzenia do uruchomienia. Użyj tej samej nazwy podczas wywoływania [StopTracingSessionW](stop-tracing-session-w.md)lub dowolnej innej funkcji zatrzymania śledzenia.

*Opcje*\
Wskaźnik do obiektu [TRACING_SESSION_OPTIONS](../other-types/tracing-session-options-struct.md) . Użyj tego obiektu, aby wybrać zdarzenia, które mają być zbierane przez sesję śledzenia.

### <a name="return-value"></a>Wartość zwracana

Kod wyniku z wyliczenia [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end

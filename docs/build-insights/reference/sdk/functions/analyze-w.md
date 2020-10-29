---
title: AnalyzeW
description: Dokumentacja funkcji AnalyzeW zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a75668e0fc9d356315f5f0b3156a909187415521
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922858"
---
# <a name="analyzew"></a>AnalyzeW

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`AnalyzeW`Funkcja służy do analizowania zdarzeń MSVC odczytanych ze śledzenia zdarzeń wejściowych systemu Windows (ETW).

## <a name="syntax"></a>Składnia

```cpp
enum RESULT_CODE AnalyzeW(
    const wchar_t*             inputLogFile,
    const ANALYSIS_DESCRIPTOR* analysisDescriptor);
```

### <a name="parameters"></a>Parametry

*inputLogFile*\
Wejściowy ślad ETW, z którego mają być odczytywane zdarzenia.

*analysisDescriptor*\
Wskaźnik do obiektu [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) . Ten obiekt służy do konfigurowania analizy.

### <a name="return-value"></a>Wartość zwracana

Kod wyniku z wyliczenia [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end

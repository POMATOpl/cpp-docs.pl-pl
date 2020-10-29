---
title: RelogA
description: Dokumentacja funkcji RelogA zestawu SDK usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4e4882bca2241c520d4cb6ba0a8eb9c32704eaef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922809"
---
# <a name="reloga"></a>RelogA

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`RelogA`Funkcja służy do odczytywania zdarzeń MSVC z śladu śledzenia zdarzeń systemu Windows (ETW) i zapisywania ich w nowym, zmodyfikowanym śledzeniu ETW.

## <a name="syntax"></a>Składnia

```cpp
enum RESULT_CODE RelogA(
    const char*             inputLogFile,
    const char*             outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>Parametry

*inputLogFile*\
Wejściowy ślad ETW, z którego mają być odczytywane zdarzenia.

*outputLogFile*\
Plik, w którym mają zostać zapisane nowe zdarzenia.

*relogDescriptor*\
Wskaźnik do obiektu [RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md) . Ten obiekt służy do konfigurowania sesji ponownego rejestrowania.

### <a name="return-value"></a>Wartość zwracana

Kod wyniku z wyliczenia [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end

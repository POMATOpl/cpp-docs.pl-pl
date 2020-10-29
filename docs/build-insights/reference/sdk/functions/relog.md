---
title: Relog
description: Odwołanie do funkcji rejestrowania w usłudze C++ build Insights SDK.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Relog
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 628f60042a10cf80c0b077d28387ed75466e925b
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922747"
---
# <a name="relog"></a>Relog

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`Relog`Funkcja służy do odczytywania zdarzeń MSVC z śladu śledzenia zdarzeń systemu Windows (ETW) i zapisywania ich w nowym, zmodyfikowanym śledzeniu ETW.

## <a name="syntax"></a>Składnia

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const char*                                   inputLogFile,
    const char*                                   outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const wchar_t*                                inputLogFile,
    const wchar_t*                                outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>Parametry

*TAnalyzerGroupMembers*\
Ten parametr jest zawsze wywnioskowany.

*TReloggerGroupMembers*\
Ten parametr jest zawsze wywnioskowany.

*inputLogFile*\
Wejściowy ślad ETW, z którego mają być odczytywane zdarzenia.

*outputLogFile*\
Plik, w którym mają zostać zapisane nowe zdarzenia.

*numberOfAnalysisPasses*\
Liczba przebiegów analizy do uruchomienia na danych wejściowych śledzenia. Śledzenie jest przekazywane przez podaną grupę analizatora raz na przebieg analizy.

*systemEventsRetentionFlags*\
Maska bitów określająca, które systemowe zdarzenia ETW należy zachować w rejestrowanym śladzie. Aby uzyskać więcej informacji, zobacz [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md).

*Analizator*\
Grupa analizatorów używana dla fazy analizy sesji rejestrowania. Wywołaj [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) , aby utworzyć grupę analizatorów. Aby użyć dynamicznej grupy analizatora uzyskanej z [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md), należy najpierw hermetyzować ją wewnątrz statycznej grupy analizatorów, przekazując jej adres do `MakeStaticAnalyzerGroup` .

*rejestratora*\
Grupa ponownego rejestrowania, która rejestruje zdarzenia do pliku śledzenia określonego w *outputLogFile* . Wywołaj [MakeStaticReloggerGroup](make-static-relogger-group.md) , aby utworzyć grupę modułu rejestrującego. Aby użyć dynamicznej grupy ponownego rejestrowania uzyskanej z [MakeDynamicReloggerGroup](make-dynamic-relogger-group.md), należy najpierw hermetyzować ją wewnątrz statycznej grupy rejestrowania przez przekazanie jej adresu do `MakeStaticReloggerGroup` .

### <a name="return-value"></a>Wartość zwracana

Kod wyniku z wyliczenia [RESULT_CODE](../other-types/result-code-enum.md) .

### <a name="remark"></a>Dyskusji

Śledzenie danych wejściowych jest przesyłane przez grupę analizatora *numberOfAnalysisPasses* razy. Nie ma podobnej opcji do rejestrowania przebiegów. Śledzenie jest przekazywane trough grupę rejestratorów tylko raz, po ukończeniu wszystkich przebiegów analizy.

Rejestrowanie zdarzeń systemowych, takich jak przykłady procesora CPU z klasy rerejestratora, nie jest obsługiwane. Użyj parametru *systemEventsRetentionFlags* , aby określić, które zdarzenia systemowe mają być przechowywane w wyniku śledzenia danych wyjściowych.

::: moniker-end

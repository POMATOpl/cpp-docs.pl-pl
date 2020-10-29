---
title: Klasa IAnalyzer
description: Odwołanie do klasy IAnalyzer zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2514dd305a186d1153e9f9d1711bb774ea70cdf9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919816"
---
# <a name="ianalyzer-class"></a>Klasa IAnalyzer

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`IAnalyzer`Klasa udostępnia interfejs do analizowania śladu śledzenia zdarzeń dla systemu Windows (ETW). Jest on używany z funkcjami [MakeDynamicAnalyzerGroup](../functions/make-dynamic-analyzer-group.md), [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md), [MakeStaticAnalyzerGroup](../functions/make-dynamic-analyzer-group.md)i [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md) . Użyj `IAnalyzer` jako klasy bazowej do utworzenia własnego analizatora, który może być częścią analizatora lub grupy rejestratora.

## <a name="syntax"></a>Składnia

```cpp
class IAnalyzer : public IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
    virtual AnalysisControl OnStopActivity(const EventStack& eventStack)
    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
    virtual AnalysisControl OnBeginAnalysis();
    virtual AnalysisControl OnEndAnalysis();
    virtual AnalysisControl OnBeginAnalysisPass();
    virtual AnalysisControl OnEndAnalysisPass();

    AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnBeginRelogging() final;
    AnalysisControl OnEndRelogging() final;
    AnalysisControl OnBeginReloggingPass() final;
    AnalysisControl OnEndReloggingPass() final;

    virtual ~IAnalyzer();
};
```

## <a name="remarks"></a>Uwagi

Klasy, które pochodzą z `IAnalyzer` mogą być używane jako analizatory i rerejestratory. Gdy jest używany jako rerejestratory, funkcje specyficzne dla ponownego rejestrowania przekierują się do ich odpowiedników analizatora. Odwrócenie nie jest prawdziwe: Klasa, która pochodzi od `IRelogger` nie może być użyta jako Analizator. Korzystanie z analizatora w grupie ponownego rejestrowania jest typowym wzorcem. Gdy zostanie umieszczony na wczesnej pozycji grupy ponownego rejestrowania, Analizator może wstępnie obliczyć informacje i udostępnić je do ponownego rejestrowania w późniejszych miejscach.

Domyślna wartość zwracana dla wszystkich funkcji, które nie są zastępowane, to `AnalysisControl::CONTINUE` . Aby uzyskać więcej informacji, zobacz [AnalysisControl](analysis-control-enum-class.md).

## <a name="members"></a>Elementy członkowskie

Oprócz elementu członkowskiego [OnTraceInfo](irelogger-class.md#on-trace-info) z `IRelogger` interfejsu `IAnalyzer` Klasa zawiera następujące elementy członkowskie:

### <a name="destructor"></a>Destruktor

[~ IAnalyzer](#ianalyzer-destructor)

### <a name="functions"></a>Funkcje

[OnBeginAnalysis](#on-begin-analysis)\
[OnBeginAnalysisPass](#on-begin-analysis-pass)\
[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndAnalysis](#on-end-analysis)\
[OnEndAnalysisPass](#on-end-analysis-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStart](#on-start-activity)\
[Onzatrzymania](#on-stop-activity)

## <a name="ianalyzer"></a><a name="ianalyzer-destructor"></a> ~ IAnalyzer

Niszczy klasę IAnalyzer.

```cpp
virtual ~IAnalyzer();
```

## <a name="onbeginanalysis"></a><a name="on-begin-analysis"></a> OnBeginAnalysis

W przypadku analizatorów, część tej funkcji jest wywoływana przed rozpoczęciem pierwszego przebiegu analizy. Dla analizatorów części grupy ponownych uruchomień ta funkcja jest wywoływana przed rozpoczęciem przebiegu ponownego rejestrowania. W przypadku analizatorów, które są częścią tej samej sesji ponownego rejestrowania, ta funkcja jest wywoływana dwukrotnie przed rozpoczęciem pierwszego przebiegu analizy.

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onbeginanalysispass"></a><a name="on-begin-analysis-pass"></a> OnBeginAnalysisPass

W przypadku analizatorów, część tej funkcji jest wywoływana na początku każdego przebiegu analizy. Dla analizatorów części grupy ponownego rejestrowania ta funkcja jest wywoływana na początku przebiegu ponownego rejestrowania. W przypadku analizatorów w ramach obu tych samych sesji ponownego rejestrowania ta funkcja jest wywoływana na początku każdego przebiegu analizy i na początku przebiegu ponownego rejestratora.

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a> OnBeginRelogging

```cpp
AnalysisControl OnBeginRelogging() final;
```

Nie można zastąpić tej funkcji. Jest on wywoływany przez zestaw SDK platformy C++ build Insights, gdy analizator jest częścią grupy rejestratorów. Ta funkcja przekierowuje wywołanie do [OnBeginAnalysis](#on-begin-analysis).

### <a name="return-value"></a>Wartość zwracana

Wynik wywołania [OnBeginAnalysis](#on-begin-analysis) .

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a> OnBeginReloggingPass

Nie można zastąpić tej funkcji. Jest on wywoływany przez zestaw SDK platformy C++ build Insights, gdy analizator jest częścią grupy rejestratorów. Ta funkcja przekierowuje wywołanie do [OnBeginAnalysisPass](#on-begin-analysis-pass).

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>Wartość zwracana

Wynik wywołania [OnBeginAnalysisPass](#on-begin-analysis-pass) .

## <a name="onendanalysis"></a><a name="on-end-analysis"></a> OnEndAnalysis

W przypadku analizatorów, które są częścią grupy analizatora, ta funkcja jest wywoływana po zakończeniu ostatniego przebiegu analizy. W przypadku analizatorów, które są częścią grupy rerejestratora, ta funkcja jest wywoływana po zakończeniu przebiegu ponownego rejestrowania. W przypadku analizatorów, które są częścią tej samej sesji ponownego rejestrowania i grupy, to ta funkcja jest wywoływana dwukrotnie:

1. Po zakończeniu wszystkich przebiegów analizy i przed rozpoczęciem przebiegu rejestrowania
1. Po zakończeniu przebiegu rejestrowania.

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onendanalysispass"></a><a name="on-end-analysis-pass"></a> OnEndAnalysisPass

W przypadku analizatorów, część tej funkcji jest wywoływana po zakończeniu każdego przebiegu analizy. Dla analizatorów części grupy ponownego rejestrowania ta funkcja jest wywoływana na końcu przebiegu ponownego rejestrowania. W przypadku analizatorów w ramach obu tych samych sesji ponownego rejestrowania ta funkcja jest wywoływana na końcu każdego przebiegu analizy i na końcu przebiegu ponownego rejestratora.

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a> OnEndRelogging

Nie można zastąpić tej funkcji. Jest on wywoływany przez zestaw SDK platformy C++ build Insights, gdy analizator jest częścią grupy rejestratorów. Ta funkcja przekierowuje wywołanie do [OnEndAnalysis](#on-end-analysis).

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>Wartość zwracana

Wynik wywołania [OnEndAnalysis](#on-end-analysis) .

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a> OnEndReloggingPass

Nie można zastąpić tej funkcji. Jest on wywoływany przez zestaw SDK platformy C++ build Insights, gdy analizator jest częścią grupy rejestratorów. Ta funkcja przekierowuje wywołanie do [OnEndAnalysisPass](#on-end-analysis-pass).

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>Wartość zwracana

Wynik wywołania [OnEndAnalysisPass](#on-end-analysis-pass) .

## <a name="onsimpleevent"></a><a name="on-simple-event"></a> OnSimpleEvent

Ta funkcja jest wywoływana, gdy trwa przetwarzanie prostego zdarzenia. Nie można zastąpić drugiej wersji tej funkcji. Jest on wywoływany przez zestaw SDK platformy C++ build Insights, gdy analizator jest częścią grupy rejestratorów. Wszystkie wywołania wersji 2 są przekierowywane do wersji 1.

### <a name="version-1"></a>Wersja 1

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

### <a name="version-2"></a>Wersja 2

```cpp
AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Parametry

*eventStack*\
Stos zdarzeń dla tego prostego zdarzenia. Aby uzyskać więcej informacji na stosach zdarzeń, zobacz [zdarzenia](../event-table.md).

*relogSession*\
Ten parametr jest nieużywany.

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onstartactivity"></a><a name="on-start-activity"></a> OnStart

Ta funkcja jest wywoływana, gdy trwa przetwarzanie zdarzenia uruchomienia działania. Nie można zastąpić drugiej wersji tej funkcji. Jest on wywoływany przez zestaw SDK platformy C++ build Insights, gdy analizator jest częścią grupy rejestratorów. Wszystkie wywołania wersji 2 są przekierowywane do wersji 1.

### <a name="version-1"></a>Wersja 1

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>Wersja 2

```cpp
AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Parametry

*eventStack*\
Stos zdarzeń dla tego zdarzenia uruchomienia działania. Aby uzyskać więcej informacji na stosach zdarzeń, zobacz [zdarzenia](../event-table.md).

*relogSession*\
Ten parametr jest nieużywany.

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a> Onzatrzymania

Ta funkcja jest wywoływana, gdy trwa przetwarzanie zdarzenia zatrzymania działania. Nie można zastąpić drugiej wersji tej funkcji. Jest on wywoływany przez zestaw SDK platformy C++ build Insights, gdy analizator jest częścią grupy rejestratorów. Wszystkie wywołania wersji 2 są przekierowywane do wersji 1.

### <a name="version-1"></a>Wersja 1

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>Wersja 2

```cpp
AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>Parametry

*eventStack*\
Stos zdarzeń dla tego zdarzenia zatrzymania działania. Aby uzyskać więcej informacji na stosach zdarzeń, zobacz [zdarzenia](../event-table.md).

*relogSession*\
Ten parametr jest nieużywany.

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

::: moniker-end

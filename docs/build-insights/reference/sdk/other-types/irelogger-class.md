---
title: Klasa IRelogger
description: Odwołanie do klasy IRelogger zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e504ece95529f7279650062145f3ac0914449c98
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922519"
---
# <a name="irelogger-class"></a>Klasa IRelogger

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`IRelogger`Klasa udostępnia interfejs do rejestrowania śledzenia zdarzeń systemu Windows (ETW). Jest on używany z funkcjami [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md) i [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md) . Użyj `IRelogger` jako klasy bazowej do utworzenia własnego modułu rejestrującego, który może być częścią grupy modułu rejestrującego.

## <a name="syntax"></a>Składnia

```cpp
class IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
    virtual AnalysisControl OnBeginRelogging();
    virtual AnalysisControl OnEndRelogging();
    virtual AnalysisControl OnBeginReloggingPass();
    virtual AnalysisControl OnEndReloggingPass() ;

    virtual ~IRelogger();
};
```

## <a name="remarks"></a>Uwagi

Domyślna wartość zwracana dla wszystkich funkcji, które nie są zastępowane, to `AnalysisControl::CONTINUE` . Aby uzyskać więcej informacji, zobacz [AnalysisControl](analysis-control-enum-class.md).

## <a name="members"></a>Elementy członkowskie

### <a name="destructor"></a>Destruktor

[~ IRelogger](#irelogger-destructor)

### <a name="functions"></a>Funkcje

[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStart](#on-start-activity)\
[Onzatrzymania](#on-stop-activity)\
[OnTraceInfo](#on-trace-info)

## <a name="irelogger"></a><a name="irelogger-destructor"></a> ~ IRelogger

Niszczy klasę IRelogger.

```cpp
virtual ~IRelogger();
```

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a> OnBeginRelogging

Ta funkcja jest wywoływana przed rozpoczęciem przebiegu rejestrowania.

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a> OnBeginReloggingPass

Ta funkcja jest wywoływana na początku przebiegu rejestrowania.

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onendrelogging"></a><a name="on-end-relogging"></a> OnEndRelogging

Ta funkcja jest wywoływana po zakończeniu przebiegu rejestrowania.

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a> OnEndReloggingPass

Ta funkcja jest wywoływana po zakończeniu przebiegu rejestrowania.

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onsimpleevent"></a><a name="on-simple-event"></a> OnSimpleEvent

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

Ta funkcja jest wywoływana, gdy trwa przetwarzanie prostego zdarzenia.

### <a name="parameters"></a>Parametry

*eventStack*\
Stos zdarzeń dla tego prostego zdarzenia. Aby uzyskać więcej informacji na stosach zdarzeń, zobacz [zdarzenia](../event-table.md).

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onstartactivity"></a><a name="on-start-activity"></a> OnStart

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

Ta funkcja jest wywoływana, gdy trwa przetwarzanie zdarzenia uruchomienia działania.

### <a name="parameters"></a>Parametry

*eventStack*\
Stos zdarzeń dla tego zdarzenia uruchomienia działania. Aby uzyskać więcej informacji na stosach zdarzeń, zobacz [zdarzenia](../event-table.md).

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="onstopactivity"></a><a name="on-stop-activity"></a> Onzatrzymania

Ta funkcja jest wywoływana, gdy trwa przetwarzanie zdarzenia zatrzymania działania.

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>Parametry

*eventStack*\
Stos zdarzeń dla tego zdarzenia zatrzymania działania. Aby uzyskać więcej informacji na stosach zdarzeń, zobacz [zdarzenia](../event-table.md).

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

## <a name="ontraceinfo"></a><a name="on-trace-info"></a> OnTraceInfo

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

Ta funkcja jest wywoływana raz na początku każdej analizy lub zarejestrowaniu przebiegu.

### <a name="parameters"></a>Parametry

*traceInfo*\
Obiekt [TraceInfo](../cpp-event-data-types/trace-info.md) , który zawiera użyteczne właściwości dotyczące używanego śledzenia.

### <a name="return-value"></a>Wartość zwracana

Kod [AnalysisControl](analysis-control-enum-class.md) , który opisuje, co należy zrobić dalej.

::: moniker-end

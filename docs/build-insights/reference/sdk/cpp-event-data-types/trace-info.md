---
title: Klasa TraceInfo
description: Odwołanie do klasy TraceInfo zestawu SDK kompilacji C++ build.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b772cc13981720c73238e56a561ca92144775cb4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922918"
---
# <a name="traceinfo-class"></a>Klasa TraceInfo

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`TraceInfo`Klasa jest używana do uzyskiwania dostępu do przydatnych właściwości dotyczących analizowanego lub zarejestrowanego śledzenia.

## <a name="syntax"></a>Składnia

```cpp
class TraceInfo
{
public:
    TraceInfo(const TRACE_INFO_DATA& data);

    const unsigned long& LogicalProcessorCount() const;

    const long long& TickFrequency() const;
    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;

    std::chrono::nanoseconds Duration() const;
};
```

## <a name="remarks"></a>Uwagi

Odejmij `StartTimestamp` od, `StopTimestamp` Aby uzyskać liczbę taktów, które upłynęły podczas całego śledzenia. Służy `TickFrequency` do konwertowania wartości wyniku na jednostkę czasu. Aby zapoznać się z przykładem konwertowania taktów na czas, zobacz [EVENT_DATA](../c-event-data-types/event-data-struct.md).

Jeśli nie chcesz samodzielnie konwertować taktów, `TraceInfo` Klasa udostępnia funkcję członkowską, która zwraca czas trwania śledzenia w nanosekundach. Użyj standardowej biblioteki C++, `chrono` Aby przekonwertować tę wartość na inne jednostki czasu.

## <a name="members"></a>Elementy członkowskie

### <a name="constructors"></a>Konstruktory

[TraceInfo](#trace-info)

### <a name="functions"></a>Funkcje

[Czas trwania](#duration) 
 [LogicalProcessorCount](#logical-processor-count) 
 [StartTimestamp](#start-timestamp) 
 [StopTimestamp](#stop-timestamp) 
 [TickFrequency](#tick-frequency)

## <a name="duration"></a><a name="duration"></a> Trwania

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Wartość zwracana

Czas trwania działania w nanosekundach.

## <a name="logicalprocessorcount"></a><a name="logical-processor-count"></a> LogicalProcessorCount

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba procesorów logicznych na komputerze, na którym zebrano dane śledzenia.

## <a name="starttimestamp"></a><a name="start-timestamp"></a> StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość taktu przechwycona w momencie rozpoczęcia śledzenia.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a> StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość taktu przechwycona w momencie zatrzymania śledzenia.

## <a name="tickfrequency"></a><a name="tick-frequency"></a> TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba taktów na sekundę do użycia podczas oceniania czasu trwania mierzoną w taktach.

## <a name="traceinfo"></a><a name="trace-info"></a> TraceInfo

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>Parametry

*Data*\
Dane zawierające informacje o śledzeniu.

::: moniker-end

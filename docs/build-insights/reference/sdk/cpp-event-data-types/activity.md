---
title: Activity — Klasa
description: Odwołanie do klasy działań zestawu SDK usługi kompilacja dla języka C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ce7e4083411f1654064ca4628d10a767c7be1b7f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923406"
---
# <a name="activity-class"></a>Activity — Klasa

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`Activity`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj go, aby dopasować każde zdarzenie działania. Zapoznaj się z [tabelą zdarzeń](../event-table.md) , aby wyświetlić wszystkie zdarzenia, które mogą być dopasowane przez `Activity` klasę.

## <a name="syntax"></a>Składnia

```cpp
class Activity : public Event
{
public:
    Activity(const RawEvent& event);

    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;
    const long long& ExclusiveDurationTicks() const;
    const long long& CPUTicks() const;
    const long long& ExclusiveCPUTicks() const;
    const long long& WallClockTimeResponsibilityTicks() const;
    const long long& ExclusiveWallClockTimeResponsibilityTicks() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>Uwagi

Kilka funkcji Członkowskich w `Activity` klasie zwraca liczbę cykli. Szczegółowe informacje o kompilacji w języku C++ używają licznika wydajności systemu Windows jako źródła taktów. Liczba cykli musi być używana z częstotliwością taktu, aby przekonwertować ją na jednostkę czasu, taką jak sekundy. `TickFrequency`Funkcja członkowska dostępna w klasie podstawowej [zdarzenia](event.md) może zostać wywołana w celu uzyskania częstotliwości taktu. Na stronie [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) przedstawiono przykład konwersji taktów na jednostkę czasu.

Jeśli nie chcesz samodzielnie konwertować taktów do jednostek czasu, `Activity` Klasa zawiera funkcje członkowskie, które zwracają wartości czasu w nanosekundach. Użyj standardowej biblioteki C++, `chrono` Aby przekonwertować ją na inne jednostki czasu.

## <a name="members"></a>Elementy członkowskie

Wraz z członkami dziedziczonymi z klasy podstawowej [zdarzenia](event.md) `Activity` Klasa zawiera następujące elementy członkowskie:

### <a name="constructor"></a>Konstruktor

[Działanie](#activity)

### <a name="functions"></a>Funkcje

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Trwania](#duration)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeResponsibility](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeResponsibilityTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[StartTimestamp](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[WallClockTimeResponsibility](#wall-clock-time-responsibility)\
[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a><a name="activity"></a> Interakcyjn

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Dowolne zdarzenie działania.

## <a name="cputicks"></a><a name="cpu-ticks"></a> CPUTicks

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba cykli procesora CPU, które wystąpiły w trakcie tego działania. Cykl procesora CPU różni się od zwykłego taktu. Takty procesora są zliczane tylko wtedy, gdy procesor wykonuje kod w działaniu. Takty procesora nie są zliczane, gdy wątek skojarzony z działaniem jest uśpiony.

## <a name="cputime"></a><a name="cpu-time"></a> CPUTime

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>Wartość zwracana

Czas wykonywania przez procesor CPU kodu w ramach tego działania. Ta wartość może być większa niż czas trwania działania, jeśli działania podrzędne są wykonywane w oddzielnych wątkach. Wartość jest zwracana w nanosekundach.

## <a name="duration"></a><a name="duration"></a> Trwania

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>Wartość zwracana

Czas trwania działania w nanosekundach.

## <a name="exclusivecputicks"></a><a name="exclusive-cpu-ticks"></a> ExclusiveCPUTicks

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>Wartość zwracana

Analogicznie jak [CPUTicks](#cpu-ticks), ale nie obejmuje taktów procesora, które wystąpiły w działaniach podrzędnych.

## <a name="exclusivecputime"></a><a name="exclusive-cpu-time"></a> ExclusiveCPUTime

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>Wartość zwracana

Analogicznie jak [CPUTime](#cpu-time), z tą różnicą, że czas procesora działań podrzędnych nie jest uwzględniony.

## <a name="exclusiveduration"></a><a name="exclusive-duration"></a> ExclusiveDuration

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>Wartość zwracana

Czas trwania działania w nanosekundach, bez uwzględniania czasu spędzonego w działaniach podrzędnych.

## <a name="exclusivedurationticks"></a><a name="exclusive-duration-ticks"></a> ExclusiveDurationTicks

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba znaczników, które wystąpiły w tym działaniu, z wyłączeniem liczby taktów, które wystąpiły w działaniach podrzędnych.

## <a name="exclusivewallclocktimeresponsibility"></a><a name="exclusive-wall-clock-time-responsibility"></a> ExclusiveWallClockTimeResponsibility

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Wartość zwracana

Analogicznie jak [WallClockTimeResponsibility](#wall-clock-time-responsibility), ale nie obejmuje odpowiedzialności za czas zegara na działania podrzędne.

## <a name="exclusivewallclocktimeresponsibilityticks"></a><a name="exclusive-wall-clock-time-responsibility-ticks"></a> ExclusiveWallClockTimeResponsibilityTicks

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Wartość zwracana

Analogicznie jak [WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks), ale nie uwzględniające czasu zegarka odpowiedzialności za działania podrzędne.

## <a name="starttimestamp"></a><a name="start-timestamp"></a> StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość taktu przechwycona w momencie uruchomienia działania.

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a> StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość taktu przechwycona w momencie zatrzymania działania.

## <a name="wallclocktimeresponsibility"></a><a name="wall-clock-time-responsibility"></a> WallClockTimeResponsibility

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>Wartość zwracana

Czas zegarowy w nanosekundach, który jest odpowiedzialny za to działanie. Aby uzyskać więcej informacji o tym, co jest odpowiedzialne za czas zegara ściany, zobacz [WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks).

## <a name="wallclocktimeresponsibilityticks"></a><a name="wall-clock-time-responsibility-ticks"></a> WallClockTimeResponsibilityTicks

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba cykli, która reprezentuje udział tego działania w ogólnym czasie zegara ściany. Cykl odpowiedzialności w czasie zegara ściany różni się od zwykłego taktu. Cykle odpowiedzialności za zegary ścienne są uwzględniane równolegle między działaniami. Dwa działania równoległe mogą mieć czas trwania 50 taktów i ten sam czas rozpoczęcia i zakończenia. W takim przypadku oba te elementy otrzymują przypisany Czas zegarowy do 25 taktów.

::: moniker-end

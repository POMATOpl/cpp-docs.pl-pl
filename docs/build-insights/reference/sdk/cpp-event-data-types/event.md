---
title: Event — Klasa
description: Odwołanie do klasy zdarzeń zestawu SDK kompilacji usługi Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Event
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7dd96ffa3518c58e1b18312bb4fe2c36df26bd67
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923301"
---
# <a name="event-class"></a>Event — Klasa

::: moniker range="<=msvc-140"

Zestaw SDK usługi Build Insights jest zgodny z programem Visual Studio 2017 lub nowszym. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end
::: moniker range=">=msvc-150"

`Event`Klasa jest używana z funkcjami [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md)i [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) . Użyj jej do dopasowania dowolnego zdarzenia.

## <a name="syntax"></a>Składnia

```cpp
class Event
{
public:
    Event(const RawEvent& event);

    const unsigned short&        EventId() const;
    const unsigned long long&    EventInstanceId() const;
    const long long&             TickFrequency() const;
    const long long&             Timestamp() const;
    const unsigned long&         ProcessId() const;
    const unsigned long&         ThreadId() const;
    const unsigned short&        ProcessorIndex() const;
    const char*                  EventName() const;
    const wchar_t*               EventWideName() const;
};
```

## <a name="members"></a>Elementy członkowskie

### <a name="constructors"></a>Konstruktory

[Wydarzenie](#entity)

### <a name="functions"></a>Funkcje

[Dane](#data) 
 [EventID](#event-id)\
[EventInstanceId](#event-instance-id)\
[EventName](#event-name)\
[EventWideName](#event-wide-name)\
[Identyfikator](#process-id)\
[ProcessorIndex](#processor-index)\
[ThreadId](#thread-id)\
[TickFrequency](#tick-frequency)\
[Timestamp](#timestamp)

## <a name="event"></a><a name="entity"></a> Wydarzen

```cpp
Event(const RawEvent& event);
```

### <a name="parameters"></a>Parametry

*wydarzen*\
Dowolne zdarzenie.

## <a name="data"></a><a name="data"></a> Data

```cpp
const void* Data() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do dodatkowych danych zawartych w tym zdarzeniu. Aby uzyskać więcej informacji na temat interpretowania tego pola, zobacz [EVENT_DATA](../c-event-data-types/event-data-struct.md).

## <a name="eventid"></a><a name="event-id"></a> EventId

```cpp
const unsigned short& EventId() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba, która identyfikuje typ zdarzenia. Aby uzyskać listę identyfikatorów zdarzeń, zobacz [EVENT_ID](../c-event-data-types/event-id-enum.md).

## <a name="eventinstanceid"></a><a name="event-instance-id"></a> EventInstanceId

```cpp
const unsigned long long& EventInstanceId() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba, która jednoznacznie identyfikuje zdarzenie wewnątrz śladu. Ta wartość nie ulega zmianie podczas analizowania lub wielokrotnego rejestrowania tego samego śledzenia. Użyj tej wartości, aby zidentyfikować to samo zdarzenie w wielu analizach lub przerejestrowaniu przebiegów tego samego śledzenia.

## <a name="eventname"></a><a name="event-name"></a> EventName

```cpp
const char* EventName() const;
```

### <a name="return-value"></a>Wartość zwracana

Ciąg ANSI zawierający nazwę typu zdarzenia identyfikowanego przez [EventID](#event-id).

## <a name="eventwidename"></a><a name="event-wide-name"></a> EventWideName

```cpp
const wchar_t* EventWideName() const;
```

### <a name="return-value"></a>Wartość zwracana

Szeroki ciąg zawierający nazwę zdarzenia identyfikowanego przez [EventID](#event-id).

## <a name="processid"></a><a name="process-id"></a> Identyfikator

```cpp
const unsigned long& ProcessId() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator procesu, w którym wystąpiło zdarzenie.

## <a name="processorindex"></a><a name="processor-index"></a> ProcessorIndex

```cpp
const unsigned short& ProcessorIndex() const;
```

### <a name="return-value"></a>Wartość zwracana

Indeks (liczony od zera) dla procesora logicznego, w którym wystąpiło zdarzenie.

## <a name="threadid"></a><a name="thread-id"></a> ThreadId

```cpp
const unsigned long& ThreadId() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator wątku, w którym wystąpiło zdarzenie.

## <a name="tickfrequency"></a><a name="tick-frequency"></a> TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba taktów na sekundę, która ma być używana podczas obliczania czasu trwania mierzoną w taktach dla tego zdarzenia.

## <a name="timestamp"></a><a name="timestamp"></a> Znacznik czasu

```cpp
const long long& Timestamp() const;
```

### <a name="return-value"></a>Wartość zwracana

Jeśli zdarzenie jest działaniem, funkcja ta zwraca wartość taktu przechwyconą w momencie uruchomienia działania. W przypadku prostego zdarzenia ta funkcja zwraca wartość taktu przechwyconą w momencie wystąpienia zdarzenia.

::: moniker-end

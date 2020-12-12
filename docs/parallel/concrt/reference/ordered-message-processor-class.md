---
description: Dowiedz się więcej na temat klasy ordered_message_processor
title: ordered_message_processor — Klasa
ms.date: 11/04/2016
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
ms.openlocfilehash: bea7f2ae70b6eb87fc30ece578f3bd8c3b35b5ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167542"
---
# <a name="ordered_message_processor-class"></a>ordered_message_processor — Klasa

`ordered_message_processor`Jest to element `message_processor` , który umożliwia blokom komunikatów przetwarzanie komunikatów w kolejności, w jakiej zostały odebrane.

## <a name="syntax"></a>Składnia

```cpp
template<class T>
class ordered_message_processor : public message_processor<T>;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ ładunku komunikatów obsłużonych przez procesor.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`type`|Alias typu dla `T` .|

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[ordered_message_processor](#ctor)|Konstruuje `ordered_message_processor` obiekt.|
|[~ ordered_message_processor destruktor](#dtor)|Niszczy `ordered_message_processor` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[async_send](#async_send)|Asynchronicznie kolejkuje komunikaty i uruchamia zadanie przetwarzania, jeśli nie zostało to jeszcze zrobione. (Zastępuje [message_processor:: async_send](message-processor-class.md#async_send).)|
|[inicjacj](#initialize)|Inicjuje `ordered_message_processor` obiekt z odpowiednią funkcją wywołania zwrotnego, harmonogramem i grupą harmonogramów.|
|[initialize_batched_processing](#initialize_batched_processing)|Inicjowanie przetwarzania wsadowych komunikatów|
|[sync_send](#sync_send)|Synchronicznie kolejkuje komunikaty i uruchamia zadanie przetwarzania, jeśli nie zostało to jeszcze zrobione. (Zastępuje [message_processor:: sync_send](message-processor-class.md#sync_send).)|
|[trwa](#wait)|Odczekanie specyficzne dla procesora używany w destruktorach bloków komunikatów, aby upewnić się, że wszystkie zadania przetwarzania asynchronicznego mają czas zakończenia przed zniszczeniem bloku. (Zastępuje [message_processor:: wait](message-processor-class.md#wait).)|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Funkcja przetwarzania, która jest wywoływana asynchronicznie. Powoduje dekolejkowanie komunikatów i rozpoczyna ich przetwarzanie. (Zastępuje [message_processor::p rocess_incoming_message](message-processor-class.md#process_incoming_message).)|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[message_processor](message-processor-class.md)

`ordered_message_processor`

## <a name="requirements"></a>Wymagania

**Nagłówek:** agenci. h

**Przestrzeń nazw:** współbieżność

## <a name="async_send"></a><a name="async_send"></a> async_send

Asynchronicznie kolejkuje komunikaty i uruchamia zadanie przetwarzania, jeśli nie zostało to jeszcze zrobione.

```cpp
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Parametry

*_Msg*<br/>
Wskaźnik do komunikatu.

## <a name="initialize"></a><a name="initialize"></a> inicjacj

Inicjuje `ordered_message_processor` obiekt z odpowiednią funkcją wywołania zwrotnego, harmonogramem i grupą harmonogramów.

```cpp
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```

### <a name="parameters"></a>Parametry

*_PScheduler*<br/>
Wskaźnik do harmonogramu używany do planowania zadań z lekkim ważeniem.

*_PScheduleGroup*<br/>
Wskaźnik do grupy harmonogramów, który ma być używany do planowania zadań lekkich.

*_Handler*<br/>
Procedura obsługi Funktor wywołana podczas wywołania zwrotnego.

## <a name="initialize_batched_processing"></a><a name="initialize_batched_processing"></a> initialize_batched_processing

Inicjowanie przetwarzania wsadowych komunikatów

```cpp
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```

### <a name="parameters"></a>Parametry

*_Processor*<br/>
Funktor procesora został wywołany podczas wywołania zwrotnego.

*_Propagator*<br/>
Funktorer został wywołany podczas wywołania zwrotnego.

## <a name="ordered_message_processor"></a><a name="ctor"></a> ordered_message_processor

Konstruuje `ordered_message_processor` obiekt.

```cpp
ordered_message_processor();
```

### <a name="remarks"></a>Uwagi

`ordered_message_processor`Nie spowoduje to zaplanowania asynchronicznych lub synchronicznych programów obsługi do momentu `initialize` wywołania funkcji.

## <a name="ordered_message_processor"></a><a name="dtor"></a> ~ ordered_message_processor

Niszczy `ordered_message_processor` obiekt.

```cpp
virtual ~ordered_message_processor();
```

### <a name="remarks"></a>Uwagi

Czeka na wszystkie zaległe operacje asynchroniczne przed zniszczeniem procesora.

## <a name="process_incoming_message"></a><a name="process_incoming_message"></a> process_incoming_message

Funkcja przetwarzania, która jest wywoływana asynchronicznie. Powoduje dekolejkowanie komunikatów i rozpoczyna ich przetwarzanie.

```cpp
virtual void process_incoming_message();
```

## <a name="sync_send"></a><a name="sync_send"></a> sync_send

Synchronicznie kolejkuje komunikaty i uruchamia zadanie przetwarzania, jeśli nie zostało to jeszcze zrobione.

```cpp
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Parametry

*_Msg*<br/>
Wskaźnik do komunikatu.

## <a name="wait"></a><a name="wait"></a> trwa

Odczekanie specyficzne dla procesora używany w destruktorach bloków komunikatów, aby upewnić się, że wszystkie zadania przetwarzania asynchronicznego mają czas zakończenia przed zniszczeniem bloku.

```cpp
virtual void wait();
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)

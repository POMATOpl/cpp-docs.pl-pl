---
description: Dowiedz się więcej na temat klasy target_block
title: target_block — Klasa
ms.date: 11/04/2016
f1_keywords:
- target_block
- AGENTS/concurrency::target_block
- AGENTS/concurrency::target_block::target_block
- AGENTS/concurrency::target_block::propagate
- AGENTS/concurrency::target_block::send
- AGENTS/concurrency::target_block::async_send
- AGENTS/concurrency::target_block::decline_incoming_messages
- AGENTS/concurrency::target_block::enable_batched_processing
- AGENTS/concurrency::target_block::initialize_target
- AGENTS/concurrency::target_block::link_source
- AGENTS/concurrency::target_block::process_input_messages
- AGENTS/concurrency::target_block::process_message
- AGENTS/concurrency::target_block::propagate_message
- AGENTS/concurrency::target_block::register_filter
- AGENTS/concurrency::target_block::remove_sources
- AGENTS/concurrency::target_block::send_message
- AGENTS/concurrency::target_block::sync_send
- AGENTS/concurrency::target_block::unlink_source
- AGENTS/concurrency::target_block::unlink_sources
- AGENTS/concurrency::target_block::wait_for_async_sends
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
ms.openlocfilehash: 0860ff7b185eef997d7c76f61d67ad10056ca9cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188420"
---
# <a name="target_block-class"></a>target_block — Klasa

`target_block`Klasa jest abstrakcyjną klasą bazową, która zapewnia podstawowe funkcje zarządzania łączami i sprawdzanie błędów tylko dla bloków docelowych.

## <a name="syntax"></a>Składnia

```cpp
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>Parametry

*_SourceLinkRegistry*<br/>
Rejestr łącza, który ma być używany do przechowywania linków źródłowych.

*_MessageProcessorType*<br/>
Typ procesora do przetwarzania komunikatów.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`source_iterator`|Typ iteratora dla `source_link_manager` tego `target_block` obiektu.|

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[target_block](#ctor)|Konstruuje `target_block` obiekt.|
|[~ target_block destruktor](#dtor)|Niszczy `target_block` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[rozpowszechni](#propagate)|Asynchronicznie przekazuje komunikat z bloku źródłowego do tego bloku docelowego.|
|[Wyślij](#send)|Synchronicznie przekazuje komunikat z bloku źródłowego do tego bloku docelowego.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[async_send](#async_send)|Asynchronicznie wysyła komunikat do przetworzenia.|
|[decline_incoming_messages](#decline_incoming_messages)|Wskazuje blok, który powinien zostać odrzucony.|
|[enable_batched_processing](#enable_batched_processing)|Włącza przetwarzanie wsadowe dla tego bloku.|
|[initialize_target](#initialize_target)|Inicjuje obiekt podstawowy. `message_processor`Obiekt musi być zainicjowany.|
|[link_source](#link_source)|Łączy określony blok źródłowy z tym `target_block` obiektem.|
|[process_input_messages](#process_input_messages)|Przetwarza komunikaty odbierane jako dane wejściowe.|
|[process_message](#process_message)|Gdy jest zastępowany w klasie pochodnej, przetwarza komunikat, który został zaakceptowany przez ten `target_block` obiekt.|
|[propagate_message](#propagate_message)|Gdy jest zastępowany w klasie pochodnej, Metoda ta asynchronicznie przekazuje komunikat z `ISource` bloku do tego `target_block` obiektu. Jest wywoływana przez `propagate` metodę, gdy jest wywoływana przez blok źródłowy.|
|[register_filter](#register_filter)|Rejestruje metodę filtru, która będzie wywoływana dla każdego odebranego komunikatu.|
|[remove_sources](#remove_sources)|Odłącza wszystkie źródła po oczekiwaniu na zakończenie zaległych asynchronicznych operacji wysyłania.|
|[send_message](#send_message)|Gdy jest zastępowany w klasie pochodnej, Metoda synchronicznie przekazuje komunikat z `ISource` bloku do tego `target_block` obiektu. Jest wywoływana przez `send` metodę, gdy jest wywoływana przez blok źródłowy.|
|[sync_send](#sync_send)|Synchronicznie wysyła komunikat do przetwarzania.|
|[unlink_source](#unlink_source)|Odłącza określony blok źródłowy od tego `target_block` obiektu.|
|[unlink_sources](#unlink_sources)|Odłącza wszystkie bloki źródłowe z tego `target_block` obiektu. (Przesłania [ITarget:: unlink_sources](itarget-class.md#unlink_sources).)|
|[wait_for_async_sends](#wait_for_async_sends)|Czeka na zakończenie wszystkich propagacji asynchronicznych.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[ITarget](itarget-class.md)

`target_block`

## <a name="requirements"></a>Wymagania

**Nagłówek:** agenci. h

**Przestrzeń nazw:** współbieżność

## <a name="async_send"></a><a name="async_send"></a> async_send

Asynchronicznie wysyła komunikat do przetworzenia.

```cpp
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parametry

*_PMessage*<br/>
Wskaźnik do wysyłanej wiadomości.

## <a name="decline_incoming_messages"></a><a name="decline_incoming_messages"></a> decline_incoming_messages

Wskazuje blok, który powinien zostać odrzucony.

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>Uwagi

Ta metoda jest wywoływana przez destruktor, aby upewnić się, że nowe komunikaty są odrzucane, gdy zniszczenie jest w toku.

## <a name="enable_batched_processing"></a><a name="enable_batched_processing"></a> enable_batched_processing

Włącza przetwarzanie wsadowe dla tego bloku.

```cpp
void enable_batched_processing();
```

## <a name="initialize_target"></a><a name="initialize_target"></a> initialize_target

Inicjuje obiekt podstawowy. `message_processor`Obiekt musi być zainicjowany.

```cpp
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parametry

*_PScheduler*<br/>
Harmonogram, który ma być używany na potrzeby planowania zadań.

*_PScheduleGroup*<br/>
Grupa harmonogramu, która ma być używana na potrzeby planowania zadań.

## <a name="link_source"></a><a name="link_source"></a> link_source

Łączy określony blok źródłowy z tym `target_block` obiektem.

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametry

*_PSource*<br/>
Wskaźnik do `ISource` bloku, który ma być połączony.

### <a name="remarks"></a>Uwagi

Ta funkcja nie powinna być wywoływana bezpośrednio w `target_block` obiekcie. Bloki powinny być połączone przy użyciu `link_target` metody w `ISource` blokach, co spowoduje wywołanie `link_source` metody w odpowiadającym jej miejscu docelowym.

## <a name="process_input_messages"></a><a name="process_input_messages"></a> process_input_messages

Przetwarza komunikaty odbierane jako dane wejściowe.

```cpp
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parametry

*_PMessage*<br/>
Wskaźnik do wiadomości, która ma zostać przetworzona.

## <a name="process_message"></a><a name="process_message"></a> process_message

Gdy jest zastępowany w klasie pochodnej, przetwarza komunikat, który został zaakceptowany przez ten `target_block` obiekt.

```cpp
virtual void process_message(message<_Source_type> *);
```

## <a name="propagate"></a><a name="propagate"></a> rozpowszechni

Asynchronicznie przekazuje komunikat z bloku źródłowego do tego bloku docelowego.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametry

*_PMessage*<br/>
Wskaźnik do `message` obiektu.

*_PSource*<br/>
Wskaźnik do bloku źródłowego oferującego komunikat.

### <a name="return-value"></a>Wartość zwracana

[Message_status](concurrency-namespace-enums.md) wskazanie elementu docelowego, który zdecydował się wykonać wraz z wiadomością.

### <a name="remarks"></a>Uwagi

Metoda zgłasza wyjątek [invalid_argument](../../../standard-library/invalid-argument-class.md) , jeśli `_PMessage` `_PSource` parametr lub jest `NULL` .

## <a name="propagate_message"></a><a name="propagate_message"></a> propagate_message

Gdy jest zastępowany w klasie pochodnej, Metoda ta asynchronicznie przekazuje komunikat z `ISource` bloku do tego `target_block` obiektu. Jest wywoływana przez `propagate` metodę, gdy jest wywoływana przez blok źródłowy.

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>Parametry

*_PMessage*<br/>
Wskaźnik do `message` obiektu.

*_PSource*<br/>
Wskaźnik do bloku źródłowego oferującego komunikat.

### <a name="return-value"></a>Wartość zwracana

[Message_status](concurrency-namespace-enums.md) wskazanie elementu docelowego, który zdecydował się wykonać wraz z wiadomością.

## <a name="register_filter"></a><a name="register_filter"></a> register_filter

Rejestruje metodę filtru, która będzie wywoływana dla każdego odebranego komunikatu.

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>Parametry

*_Filter*<br/>
Metoda filtru.

## <a name="remove_sources"></a><a name="remove_sources"></a> remove_sources

Odłącza wszystkie źródła po oczekiwaniu na zakończenie zaległych asynchronicznych operacji wysyłania.

```cpp
void remove_sources();
```

### <a name="remarks"></a>Uwagi

Wszystkie bloki docelowe powinny wywołać tę procedurę, aby usunąć źródła w ich destruktorze.

## <a name="send"></a><a name="send"></a> Wyślij

Synchronicznie przekazuje komunikat z bloku źródłowego do tego bloku docelowego.

```cpp
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametry

*_PMessage*<br/>
Wskaźnik do `message` obiektu.

*_PSource*<br/>
Wskaźnik do bloku źródłowego oferującego komunikat.

### <a name="return-value"></a>Wartość zwracana

[Message_status](concurrency-namespace-enums.md) wskazanie elementu docelowego, który zdecydował się wykonać wraz z wiadomością.

### <a name="remarks"></a>Uwagi

Metoda zgłasza wyjątek [invalid_argument](../../../standard-library/invalid-argument-class.md) , jeśli `_PMessage` `_PSource` parametr lub jest `NULL` .

Użycie `send` metody poza inicjacją komunikatów i propagowanie komunikatów w sieci jest niebezpieczne i może prowadzić do zakleszczenia.

Gdy `send` zwraca, wiadomość została już zaakceptowana i przekazana do bloku docelowego lub została odrzucona przez element docelowy.

## <a name="send_message"></a><a name="send_message"></a> send_message

Gdy jest zastępowany w klasie pochodnej, Metoda synchronicznie przekazuje komunikat z `ISource` bloku do tego `target_block` obiektu. Jest wywoływana przez `send` metodę, gdy jest wywoływana przez blok źródłowy.

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Wartość zwracana

[Message_status](concurrency-namespace-enums.md) wskazanie elementu docelowego, który zdecydował się wykonać wraz z wiadomością.

### <a name="remarks"></a>Uwagi

Domyślnie ten blok zwraca, `declined` chyba że jest zastępowany przez klasę pochodną.

## <a name="sync_send"></a><a name="sync_send"></a> sync_send

Synchronicznie wysyła komunikat do przetwarzania.

```cpp
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parametry

*_PMessage*<br/>
Wskaźnik do wysyłanej wiadomości.

## <a name="target_block"></a><a name="ctor"></a> target_block

Konstruuje `target_block` obiekt.

```cpp
target_block();
```

## <a name="target_block"></a><a name="dtor"></a> ~ target_block

Niszczy `target_block` obiekt.

```cpp
virtual ~target_block();
```

## <a name="unlink_source"></a><a name="unlink_source"></a> unlink_source

Odłącza określony blok źródłowy od tego `target_block` obiektu.

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametry

*_PSource*<br/>
Wskaźnik do `ISource` bloku, który ma zostać odłączone.

## <a name="unlink_sources"></a><a name="unlink_sources"></a> unlink_sources

Odłącza wszystkie bloki źródłowe z tego `target_block` obiektu.

```cpp
virtual void unlink_sources();
```

## <a name="wait_for_async_sends"></a><a name="wait_for_async_sends"></a> wait_for_async_sends

Czeka na zakończenie wszystkich propagacji asynchronicznych.

```cpp
void wait_for_async_sends();
```

### <a name="remarks"></a>Uwagi

Ta metoda jest używana przez destruktory bloku komunikatów, aby upewnić się, że wszystkie operacje asynchroniczne miały czas na zakończenie przed zniszczeniem bloku.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Klasa ITarget](itarget-class.md)

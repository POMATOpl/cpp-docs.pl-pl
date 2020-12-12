---
description: Dowiedz się więcej na temat klasy propagator_block
title: propagator_block — Klasa
ms.date: 11/04/2016
f1_keywords:
- propagator_block
- AGENTS/concurrency::propagator_block
- AGENTS/concurrency::propagator_block::propagator_block
- AGENTS/concurrency::propagator_block::propagate
- AGENTS/concurrency::propagator_block::send
- AGENTS/concurrency::propagator_block::decline_incoming_messages
- AGENTS/concurrency::propagator_block::initialize_source_and_target
- AGENTS/concurrency::propagator_block::link_source
- AGENTS/concurrency::propagator_block::process_input_messages
- AGENTS/concurrency::propagator_block::propagate_message
- AGENTS/concurrency::propagator_block::register_filter
- AGENTS/concurrency::propagator_block::remove_network_links
- AGENTS/concurrency::propagator_block::send_message
- AGENTS/concurrency::propagator_block::unlink_source
- AGENTS/concurrency::propagator_block::unlink_sources
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
ms.openlocfilehash: 4dd006829e01f663be20be76a2cc2e0364ef7b38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115264"
---
# <a name="propagator_block-class"></a>propagator_block — Klasa

`propagator_block`Klasa jest abstrakcyjną klasą bazową dla bloków komunikatów, które są zarówno źródłowym, jak i docelowym. Łączy ona funkcje obu `source_block` `target_block` klas i.

## <a name="syntax"></a>Składnia

```cpp
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>Parametry

*_TargetLinkRegistry*<br/>
Rejestr łącza, który ma być używany do przechowywania linków docelowych.

*_SourceLinkRegistry*<br/>
Rejestr łącza, który ma być używany do przechowywania linków źródłowych.

*_MessageProcessorType*<br/>
Typ procesora do przetwarzania komunikatów.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`source_iterator`|Typ iteratora dla `source_link_manager` tego elementu `propagator_block` .|

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[propagator_block](#ctor)|Konstruuje `propagator_block` obiekt.|
|[~ propagator_block destruktor](#dtor)|Niszczy `propagator_block` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[rozpowszechni](#propagate)|Asynchronicznie przekazuje komunikat z bloku źródłowego do tego bloku docelowego.|
|[Wyślij](#send)|Synchronicznie inicjuje komunikat do tego bloku. Wywoływane przez `ISource` blok. Gdy ta funkcja zostanie ukończona, komunikat zostanie już rozpropagowany do bloku.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[decline_incoming_messages](#decline_incoming_messages)|Wskazuje blok, który powinien zostać odrzucony.|
|[initialize_source_and_target](#initialize_source_and_target)|Inicjuje obiekt podstawowy. `message_processor`Obiekt musi być zainicjowany.|
|[link_source](#link_source)|Łączy określony blok źródłowy z tym `propagator_block` obiektem.|
|[process_input_messages](#process_input_messages)|Przetwarzanie komunikatów wejściowych. Jest to przydatne tylko w przypadku bloków propagator, które pochodzą z source_block (zastąpień [source_block::p rocess_input_messages](source-block-class.md#process_input_messages)).|
|[propagate_message](#propagate_message)|Gdy jest zastępowany w klasie pochodnej, Metoda ta asynchronicznie przekazuje komunikat z `ISource` bloku do tego `propagator_block` obiektu. Jest wywoływana przez `propagate` metodę, gdy jest wywoływana przez blok źródłowy.|
|[register_filter](#register_filter)|Rejestruje metodę filtru, która będzie wywoływana dla każdej otrzymanej wiadomości.|
|[remove_network_links](#remove_network_links)|Usuwa wszystkie źródłowe i docelowe linki sieciowe z tego `propagator_block` obiektu.|
|[send_message](#send_message)|Gdy jest zastępowany w klasie pochodnej, Metoda synchronicznie przekazuje komunikat z `ISource` bloku do tego `propagator_block` obiektu. Jest wywoływana przez `send` metodę, gdy jest wywoływana przez blok źródłowy.|
|[unlink_source](#unlink_source)|Odłącza określony blok źródłowy od tego `propagator_block` obiektu.|
|[unlink_sources](#unlink_sources)|Odłącza wszystkie bloki źródłowe z tego `propagator_block` obiektu. (Przesłania [ITarget:: unlink_sources](itarget-class.md#unlink_sources).)|

## <a name="remarks"></a>Uwagi

Aby uniknąć wielokrotnego dziedziczenia, `propagator_block` Klasa dziedziczy z klasy `source_block` i `ITarget` klasy abstrakcyjnej. Większość funkcji w `target_block` klasie jest replikowana w tym miejscu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

`propagator_block`

## <a name="requirements"></a>Wymagania

**Nagłówek:** agenci. h

**Przestrzeń nazw:** współbieżność

## <a name="decline_incoming_messages"></a><a name="decline_incoming_messages"></a> decline_incoming_messages

Wskazuje blok, który powinien zostać odrzucony.

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>Uwagi

Ta metoda jest wywoływana przez destruktor, aby upewnić się, że nowe komunikaty są odrzucane, gdy zniszczenie jest w toku.

## <a name="initialize_source_and_target"></a><a name="initialize_source_and_target"></a> initialize_source_and_target

Inicjuje obiekt podstawowy. `message_processor`Obiekt musi być zainicjowany.

```cpp
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parametry

*_PScheduler*<br/>
Harmonogram, który ma być używany na potrzeby planowania zadań.

*_PScheduleGroup*<br/>
Grupa harmonogramu, która ma być używana na potrzeby planowania zadań.

## <a name="link_source"></a><a name="link_source"></a> link_source

Łączy określony blok źródłowy z tym `propagator_block` obiektem.

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametry

*_PSource*<br/>
Wskaźnik do `ISource` bloku, który ma być połączony.

## <a name="process_input_messages"></a><a name="process_input_messages"></a> process_input_messages

Przetwarzanie komunikatów wejściowych. Jest to przydatne tylko w przypadku bloków propagator, które pochodzą z source_block

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parametry

*_PMessage*<br/>
Wskaźnik do wiadomości, która ma zostać przetworzona.

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

`propagate`Metoda jest wywoływana w bloku docelowym przez połączony blok źródłowy. Kolejkuje zadanie asynchroniczne, aby obsłużyć komunikat, jeśli nie został jeszcze umieszczony w kolejce lub wykonane.

Metoda zgłasza wyjątek [invalid_argument](../../../standard-library/invalid-argument-class.md) , jeśli `_PMessage` `_PSource` parametr lub jest `NULL` .

## <a name="propagate_message"></a><a name="propagate_message"></a> propagate_message

Gdy jest zastępowany w klasie pochodnej, Metoda ta asynchronicznie przekazuje komunikat z `ISource` bloku do tego `propagator_block` obiektu. Jest wywoływana przez `propagate` metodę, gdy jest wywoływana przez blok źródłowy.

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

## <a name="propagator_block"></a><a name="ctor"></a> propagator_block

Konstruuje `propagator_block` obiekt.

```cpp
propagator_block();
```

## <a name="propagator_block"></a><a name="dtor"></a> ~ propagator_block

Niszczy `propagator_block` obiekt.

```cpp
virtual ~propagator_block();
```

## <a name="register_filter"></a><a name="register_filter"></a> register_filter

Rejestruje metodę filtru, która będzie wywoływana dla każdej otrzymanej wiadomości.

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>Parametry

*_Filter*<br/>
Metoda filtru.

## <a name="remove_network_links"></a><a name="remove_network_links"></a> remove_network_links

Usuwa wszystkie źródłowe i docelowe linki sieciowe z tego `propagator_block` obiektu.

```cpp
void remove_network_links();
```

## <a name="send"></a><a name="send"></a> Wyślij

Synchronicznie inicjuje komunikat do tego bloku. Wywoływane przez `ISource` blok. Gdy ta funkcja zostanie ukończona, komunikat zostanie już rozpropagowany do bloku.

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

Ta metoda zgłasza wyjątek [invalid_argument](../../../standard-library/invalid-argument-class.md) , jeśli `_PMessage` `_PSource` parametr lub jest `NULL` .

## <a name="send_message"></a><a name="send_message"></a> send_message

Gdy jest zastępowany w klasie pochodnej, Metoda synchronicznie przekazuje komunikat z `ISource` bloku do tego `propagator_block` obiektu. Jest wywoływana przez `send` metodę, gdy jest wywoływana przez blok źródłowy.

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Wartość zwracana

[Message_status](concurrency-namespace-enums.md) wskazanie elementu docelowego, który zdecydował się wykonać wraz z wiadomością.

### <a name="remarks"></a>Uwagi

Domyślnie ten blok zwraca, `declined` chyba że jest zastępowany przez klasę pochodną.

## <a name="unlink_source"></a><a name="unlink_source"></a> unlink_source

Odłącza określony blok źródłowy od tego `propagator_block` obiektu.

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parametry

*_PSource*<br/>
Wskaźnik do `ISource` bloku, który ma zostać odłączone.

## <a name="unlink_sources"></a><a name="unlink_sources"></a> unlink_sources

Odłącza wszystkie bloki źródłowe z tego `propagator_block` obiektu.

```cpp
virtual void unlink_sources();
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Klasa source_block](source-block-class.md)<br/>
[Klasa ITarget](itarget-class.md)

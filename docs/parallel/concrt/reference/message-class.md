---
description: 'Dowiedz się więcej o: Klasa komunikatów'
title: message — Klasa
ms.date: 11/04/2016
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
ms.openlocfilehash: 0e15dafd9606e68f7a6ed1bed3795791c0f6870c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202317"
---
# <a name="message-class"></a>message — Klasa

Podstawowa koperta komunikatów zawierająca ładunek danych przesyłanych między blokami obsługi komunikatów.

## <a name="syntax"></a>Składnia

```cpp
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych ładunku w komunikacie.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`type`|Alias typu dla `T` .|

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Komunikat](#ctor)|Przeciążone. Konstruuje `message` obiekt.|
|[~ Message — destruktor](#dtor)|Niszczy `message` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[add_ref](#add_ref)|Dodaje do liczby odwołań dla `message` obiektu. Używany dla bloków komunikatów, które wymagają zliczania odwołań, aby określić okresy istnienia wiadomości.|
|[msg_id](#msg_id)|Zwraca identyfikator `message` obiektu.|
|[remove_ref](#remove_ref)|Odejmuje od liczby odwołań dla `message` obiektu. Używany dla bloków komunikatów, które wymagają zliczania odwołań, aby określić okresy istnienia wiadomości.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[payload](#payload)|Ładunek `message` obiektu.|

## <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [asynchroniczne bloki komunikatów](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`message`

## <a name="requirements"></a>Wymagania

**Nagłówek:** agenci. h

**Przestrzeń nazw:** współbieżność

## <a name="add_ref"></a><a name="add_ref"></a> add_ref

Dodaje do liczby odwołań dla `message` obiektu. Używany dla bloków komunikatów, które wymagają zliczania odwołań, aby określić okresy istnienia wiadomości.

```cpp
long add_ref();
```

### <a name="return-value"></a>Wartość zwracana

Nowa wartość liczby odwołań.

## <a name="message"></a><a name="ctor"></a> Komunikat

Konstruuje `message` obiekt.

```cpp
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```

### <a name="parameters"></a>Parametry

*_P*<br/>
Ładunek tej wiadomości.

*_Id*<br/>
Unikatowy identyfikator tej wiadomości.

*_Msg*<br/>
Odwołanie lub wskaźnik do `message` obiektu.

### <a name="remarks"></a>Uwagi

Konstruktor, który Pobiera wskaźnik do `message` obiektu jako argument zwraca wyjątek [invalid_argument](../../../standard-library/invalid-argument-class.md) , jeśli parametr `_Msg` ma wartość `NULL` .

## <a name="message"></a><a name="dtor"></a> komunikat ~

Niszczy `message` obiekt.

```cpp
virtual ~message();
```

## <a name="msg_id"></a><a name="msg_id"></a> msg_id

Zwraca identyfikator `message` obiektu.

```cpp
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>Wartość zwracana

`runtime_object_identity` `message` Obiektu.

## <a name="payload"></a><a name="payload"></a> ładunku

Ładunek `message` obiektu.

```cpp
T const payload;
```

## <a name="remove_ref"></a><a name="remove_ref"></a> remove_ref

Odejmuje od liczby odwołań dla `message` obiektu. Używany dla bloków komunikatów, które wymagają zliczania odwołań, aby określić okresy istnienia wiadomości.

```cpp
long remove_ref();
```

### <a name="return-value"></a>Wartość zwracana

Nowa wartość liczby odwołań.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)

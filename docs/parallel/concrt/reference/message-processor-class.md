---
description: Dowiedz się więcej na temat klasy message_processor
title: message_processor — Klasa
ms.date: 11/04/2016
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
ms.openlocfilehash: f74314bde6e12ea8b00bfc7bfd2567ca15864f75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202200"
---
# <a name="message_processor-class"></a>message_processor — Klasa

`message_processor`Klasa jest abstrakcyjną klasą bazową do przetwarzania `message` obiektów. Nie ma gwarancji dotyczącej kolejności komunikatów.

## <a name="syntax"></a>Składnia

```cpp
template<class T>
class message_processor;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ danych ładunku w komunikatach obsłużonych przez ten `message_processor` obiekt.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`type`|Alias typu dla `T` .|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[async_send](#async_send)|Gdy jest zastępowany w klasie pochodnej, umieszcza komunikaty w bloku asynchronicznie.|
|[sync_send](#sync_send)|Gdy jest zastępowany w klasie pochodnej, umieszcza komunikaty w bloku synchronicznie.|
|[trwa](#wait)|Gdy jest zastępowany w klasie pochodnej, czeka na zakończenie wszystkich operacji asynchronicznych.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|W przypadku zastąpienia w klasie pochodnej program wykonuje przetwarzanie komunikatów do przodu w bloku. Wywoływana raz za każdym razem, gdy zostanie dodany nowy komunikat, a kolejka jest pusta.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`message_processor`

## <a name="requirements"></a>Wymagania

**Nagłówek:** agenci. h

**Przestrzeń nazw:** współbieżność

## <a name="async_send"></a><a name="async_send"></a> async_send

Gdy jest zastępowany w klasie pochodnej, umieszcza komunikaty w bloku asynchronicznie.

```cpp
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parametry

*_Msg*<br/>
`message`Obiekt, który ma zostać wysłany asynchronicznie.

### <a name="remarks"></a>Uwagi

Implementacje procesora powinny przesłaniać tę metodę.

## <a name="process_incoming_message"></a><a name="process_incoming_message"></a> process_incoming_message

W przypadku zastąpienia w klasie pochodnej program wykonuje przetwarzanie komunikatów do przodu w bloku. Wywoływana raz za każdym razem, gdy zostanie dodany nowy komunikat, a kolejka jest pusta.

```cpp
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>Uwagi

Implementacje bloku komunikatów powinny przesłaniać tę metodę.

## <a name="sync_send"></a><a name="sync_send"></a> sync_send

Gdy jest zastępowany w klasie pochodnej, umieszcza komunikaty w bloku synchronicznie.

```cpp
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parametry

*_Msg*<br/>
`message`Obiekt do synchronicznego wysłania.

### <a name="remarks"></a>Uwagi

Implementacje procesora powinny przesłaniać tę metodę.

## <a name="wait"></a><a name="wait"></a> trwa

Gdy jest zastępowany w klasie pochodnej, czeka na zakończenie wszystkich operacji asynchronicznych.

```cpp
virtual void wait() = 0;
```

### <a name="remarks"></a>Uwagi

Implementacje procesora powinny przesłaniać tę metodę.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Klasa ordered_message_processor](ordered-message-processor-class.md)

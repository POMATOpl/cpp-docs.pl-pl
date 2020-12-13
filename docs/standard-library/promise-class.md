---
description: Dowiedz się więcej o klasie Promise
title: promise — Klasa
ms.date: 10/18/2018
f1_keywords:
- future/std::promise
- future/std::promise::promise
- future/std::promise::get_future
- future/std::promise::set_exception
- future/std::promise::set_exception_at_thread_exit
- future/std::promise::set_value
- future/std::promise::set_value_at_thread_exit
- future/std::promise::swap
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
helpviewer_keywords:
- std::promise [C++]
- std::promise [C++], promise
- std::promise [C++], get_future
- std::promise [C++], set_exception
- std::promise [C++], set_exception_at_thread_exit
- std::promise [C++], set_value
- std::promise [C++], set_value_at_thread_exit
- std::promise [C++], swap
ms.openlocfilehash: bf65a3d1f42cb331c2e87ab418f2917947b0bed7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340635"
---
# <a name="promise-class"></a>promise — Klasa

Opisuje *dostawcę asynchronicznego*.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
class promise;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[firmy](#promise)|Konstruuje `promise` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[get_future](#get_future)|Zwraca [przyszłość](../standard-library/future-class.md) skojarzoną z tym obietnicą.|
|[set_exception](#set_exception)|Niepodzielnie ustawia wynik tej obietnicy, aby wskazać wyjątek.|
|[set_exception_at_thread_exit](#set_exception_at_thread_exit)|Niepodzielnie ustawia wynik tego obietnicy, aby wskazać wyjątek, i dostarcza powiadomienia dopiero po zniszczeniu wszystkich obiektów lokalnych wątków w bieżącym wątku (zazwyczaj przy wyjściu wątku).|
|[set_value](#set_value)|Niepodzielnie ustawia wynik tej obietnicy, aby wskazać wartość.|
|[set_value_at_thread_exit](#set_value_at_thread_exit)|Niepodzielnie ustawia wynik tej obietnicy, aby wskazać wartość, i dostarcza powiadomienia dopiero po zniszczeniu wszystkich obiektów lokalnych wątków w bieżącym wątku (zazwyczaj przy wyjściu wątku).|
|[wymiany](#swap)|Wymienia związany z tym *stan asynchroniczny* tego obietnicy z określonym obiektem Promise.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Promise:: operator =](#op_eq)|Przypisanie udostępnionego stanu tego obiektu obietnicy.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

*firmy*

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<future>

**Przestrzeń nazw:** std

## <a name="promiseget_future"></a><a name="get_future"></a> Promise:: get_future

Zwraca [przyszły](../standard-library/future-class.md) obiekt, który ma ten sam *skojarzony stan asynchroniczny* , co to obietnice.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Uwagi

Jeśli obiekt obietnicy jest pusty, ta metoda zgłasza [future_error](../standard-library/future-error-class.md) , który ma [error_code](../standard-library/error-code-class.md) `no_state` .

Jeśli ta metoda została już wywołana dla obiektu obietnicy, który ma ten sam, skojarzony stan asynchroniczny, metoda zgłasza, `future_error` że ma `error_code` `future_already_retrieved` .

## <a name="promiseoperator"></a><a name="op_eq"></a> Promise:: operator =

Przenosi *skojarzony stan asynchroniczny* z określonego `promise` obiektu.

```cpp
promise& operator=(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parametry

*Różnych*\
Obiekt `promise`.

### <a name="return-value"></a>Wartość zwracana

`*this`

### <a name="remarks"></a>Uwagi

Ten operator przenosi skojarzony stan asynchroniczny z *innego*. Po przeniesieniu *inne* jest *puste*.

## <a name="promisepromise-constructor"></a><a name="promise"></a> Promise::p Konstruktor romise

Konstruuje `promise` obiekt.

```cpp
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parametry

*Wsp*\
Alokator pamięci. [\<allocators>](../standard-library/allocators-header.md)Aby uzyskać więcej informacji, zobacz.

*Różnych*\
Obiekt `promise`.

### <a name="remarks"></a>Uwagi

Pierwszy Konstruktor konstruuje *pusty* `promise` obiekt.

Drugi Konstruktor konstruuje pusty `promise` obiekt i używa *Al* do przydzielania pamięci.

Trzeci Konstruktor konstruuje `promise` obiekt i transferuje skojarzony stan asynchroniczny z *innych* i pozostawia *inne* puste.

## <a name="promiseset_exception"></a><a name="set_exception"></a> Promise:: set_exception

Niepodzielne przechowuje wyjątek jako wynik tego `promise` obiektu i ustawia *skojarzony stan asynchroniczny* na *gotowy*.

```cpp
void set_exception(exception_ptr Exc);
```

### <a name="parameters"></a>Parametry

*Wyłączne*\
[Exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) , który jest przechowywany przez tę metodę jako wynik wyjątku.

### <a name="remarks"></a>Uwagi

Jeśli `promise` obiekt nie ma skojarzonego stanu asynchronicznego, ta metoda zgłasza [future_error](../standard-library/future-error-class.md) , który ma kod błędu `no_state` .

Jeśli `set_exception` [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value)lub [set_value_at_thread_exit](#set_value_at_thread_exit) zostało już wywołane dla `promise` obiektu, który ma ten sam stan asynchroniczny, ta metoda zgłasza, `future_error` że ma kod błędu `promise_already_satisfied` .

W wyniku tej metody wszystkie wątki, które są blokowane w skojarzonym stanie asynchronicznym, zostaną odblokowane.

## <a name="promiseset_exception_at_thread_exit"></a><a name="set_exception_at_thread_exit"></a> Promise:: set_exception_at_thread_exit

Niepodzielnie ustawia wynik tej wartości `promise` , aby wskazać wyjątek, dostarczając powiadomienie tylko po usunięciu wszystkich obiektów lokalnych wątków w bieżącym wątku (zazwyczaj przy wyjściu wątku).

```cpp
void set_exception_at_thread_exit(exception_ptr Exc);
```

### <a name="parameters"></a>Parametry

*Wyłączne*\
[Exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) , który jest przechowywany przez tę metodę jako wynik wyjątku.

### <a name="remarks"></a>Uwagi

Jeśli obiekt obietnicy nie ma *skojarzonego stanu asynchronicznego*, ta metoda zgłasza [future_error](../standard-library/future-error-class.md) , który ma kod błędu `no_state` .

Jeśli [set_exception](#set_exception), `set_exception_at_thread_exit` , [set_value](#set_value)lub [set_value_at_thread_exit](#set_value_at_thread_exit) zostało już wywołane dla `promise` obiektu, który ma ten sam stan asynchroniczny, ta metoda zgłasza, `future_error` że ma kod błędu `promise_already_satisfied` .

W przeciwieństwie do [set_exception](#set_exception)ta metoda nie ustawia skojarzonego stanu asynchronicznego na gotowe do momentu zniszczenia wszystkich obiektów lokalnych wątków w bieżącym wątku. Zazwyczaj wątki, które są blokowane w skojarzonym stanie asynchronicznym, nie są odblokowywane do momentu zakończenia bieżącego wątku.

## <a name="promiseset_value"></a><a name="set_value"></a> Promise:: set_value

Niepodzielnie zapisuje wartość jako wynik tego `promise` obiektu i ustawia *skojarzony stan asynchroniczny* na *gotowy*.

```cpp
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```

### <a name="parameters"></a>Parametry

*Użyte*\
Wartość, która ma być przechowywana w wyniku.

### <a name="remarks"></a>Uwagi

Jeśli `promise` obiekt nie ma skojarzonego stanu asynchronicznego, ta metoda zgłasza [future_error](../standard-library/future-error-class.md) , który ma kod błędu `no_state` .

Jeśli [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), `set_value` lub [set_value_at_thread_exit](#set_value_at_thread_exit) zostało już wywołane dla `promise` obiektu, który ma ten sam stan asynchroniczny, ta metoda zgłasza, `future_error` że ma kod błędu `promise_already_satisfied` .

W wyniku tej metody wszystkie wątki, które są blokowane w skojarzonym stanie asynchronicznym, zostaną odblokowane.

Pierwsza metoda zgłasza również każdy wyjątek, który jest generowany, gdy *Val* jest kopiowany do skojarzonego stanu asynchronicznego. W tej sytuacji skojarzony stan asynchroniczny nie jest ustawiony na wartość gotowe.

Druga metoda zgłasza również każdy wyjątek, który jest generowany, gdy *Val* zostanie przeniesiony do skojarzonego stanu asynchronicznego. W tej sytuacji skojarzony stan asynchroniczny nie jest ustawiony na wartość gotowe.

W przypadku częściowej specjalizacji `promise<Ty&>` przechowywana wartość jest w efekcie odwołaniem do *Val*.

Dla specjalizacji `promise<void>` nie istnieje żadna przechowywana wartość.

## <a name="promiseset_value_at_thread_exit"></a><a name="set_value_at_thread_exit"></a> Promise:: set_value_at_thread_exit

Niepodzielnie zapisuje wartość jako wynik tego `promise` obiektu.

```cpp
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```

### <a name="parameters"></a>Parametry

*Użyte*\
Wartość, która ma być przechowywana w wyniku.

### <a name="remarks"></a>Uwagi

Jeśli obiekt obietnicy nie ma *skojarzonego stanu asynchronicznego*, ta metoda zgłasza [future_error](../standard-library/future-error-class.md) , który ma kod błędu `no_state` .

Jeśli [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value)lub `set_value_at_thread_exit` zostało już wywołane dla `promise` obiektu, który ma ten sam stan asynchroniczny, ta metoda zgłasza, `future_error` że ma kod błędu `promise_already_satisfied` .

W przeciwieństwie do `set_value` , skojarzony stan asynchroniczny nie jest ustawiony na gotowe do momentu zniszczenia wszystkich obiektów lokalnych wątków w bieżącym wątku. Zazwyczaj wątki, które są blokowane w skojarzonym stanie asynchronicznym, nie są odblokowywane do momentu zakończenia bieżącego wątku.

Pierwsza metoda zgłasza również każdy wyjątek, który jest generowany, gdy *Val* jest kopiowany do skojarzonego stanu asynchronicznego.

Druga metoda zgłasza również każdy wyjątek, który jest generowany, gdy *Val* zostanie przeniesiony do skojarzonego stanu asynchronicznego.

W przypadku częściowej specjalizacji `promise<Ty&>` przechowywana wartość jest efektywnie odwołaniem do wartości *Val*.

Dla specjalizacji `promise<void>` nie istnieje żadna przechowywana wartość.

## <a name="promiseswap"></a><a name="swap"></a> Promise:: swap

Wymienia *skojarzony stan asynchroniczny* tego obiektu obietnicy z określonym obiektem.

```cpp
void swap(promise& Other) noexcept;
```

### <a name="parameters"></a>Parametry

*Różnych*\
Obiekt `promise`.

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)

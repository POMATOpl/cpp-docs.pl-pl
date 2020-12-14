---
description: Dowiedz się więcej na temat struktury scheduler_ptr
title: Struktura scheduler_ptr
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 314f587c0fd55772a8b1b7b5b8fdf3ddeb53a7a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188784"
---
# <a name="scheduler_ptr-structure"></a>Struktura scheduler_ptr

Reprezentuje wskaźnik do harmonogramu. Ta klasa istnieje, aby zezwolić na specyfikację wspólnego okresu istnienia przy użyciu shared_ptr lub tylko zwykłego odwołania przy użyciu wskaźnika RAW.

## <a name="syntax"></a>Składnia

```cpp
struct scheduler_ptr;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[scheduler_ptr:: scheduler_ptr](#ctor)|Przeciążone. Tworzy wskaźnik harmonogramu z shared_ptr do harmonogramu|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[scheduler_ptr:: Get](#get)|Zwraca surowy wskaźnik do harmonogramu|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[scheduler_ptr:: operator — bool](#operator_bool)|Sprawdź, czy wskaźnik harmonogramu ma wartość różną od null|
|[scheduler_ptr:: operator-&gt;](#operator_ptr)|Zachowuje się jak wskaźnik|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`scheduler_ptr`

## <a name="requirements"></a>Wymagania

**Nagłówek:** pplinterface. h

**Przestrzeń nazw:** współbieżność

## <a name="scheduler_ptrget-method"></a><a name="get"></a> scheduler_ptr:: Get — Metoda

Zwraca surowy wskaźnik do harmonogramu.

```cpp
scheduler_interface* get() const;
```

### <a name="return-value"></a>Wartość zwracana

## <a name="scheduler_ptroperator-bool"></a><a name="operator_bool"></a> scheduler_ptr:: operator — bool

Testuje, czy wskaźnik harmonogramu jest inny niż null.

```cpp
operator bool() const;
```

## <a name="scheduler_ptroperator-gt"></a><a name="operator_ptr"></a> scheduler_ptr:: operator-&gt;

Zachowuje się jak wskaźnik.

```cpp
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>Wartość zwracana

## <a name="scheduler_ptrscheduler_ptr-constructor"></a><a name="ctor"></a> scheduler_ptr:: scheduler_ptr, Konstruktor

Tworzy wskaźnik harmonogramu z shared_ptr do harmonogramu.

```cpp
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>Parametry

*pracę*<br/>
Harmonogram do przekonwertowania.

*pScheduler*<br/>
Wskaźnik harmonogramu do przekonwertowania.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)

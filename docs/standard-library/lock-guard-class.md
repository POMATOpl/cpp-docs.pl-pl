---
description: Dowiedz się więcej na temat klasy lock_guard
title: lock_guard — Klasa
ms.date: 11/04/2016
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
ms.openlocfilehash: d8965f1e781d99f0b84c58dcc3288a4532e4351c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277729"
---
# <a name="lock_guard-class"></a>lock_guard — Klasa

Reprezentuje szablon, który może być skonkretyzowany do utworzenia obiektu, którego destruktor odblokowuje `mutex` .

## <a name="syntax"></a>Składnia

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>Uwagi

Argument szablonu `Mutex` musi mieć nazwę *typu muteksu*.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`lock_guard::mutex_type`|Synonim argumentu szablonu `Mutex` .|

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[lock_guard](#lock_guard)|Konstruuje `lock_guard` obiekt.|
|[lock_guard:: ~ lock_guard, destruktor](#dtorlock_guard_destructor)|Odblokowuje `mutex` , który został przesłany do konstruktora.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<mutex>

**Przestrzeń nazw:** std

## <a name="lock_guardlock_guard-constructor"></a><a name="lock_guard"></a> lock_guard:: lock_guard, Konstruktor

Konstruuje `lock_guard` obiekt.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>Parametry

*MTX*\
Obiekt *typu mutex* .

### <a name="remarks"></a>Uwagi

Pierwszy Konstruktor konstruuje obiekt typu `lock_guard` i blokuje *MTX*. Jeśli *MTX* nie jest cyklicznym obiektem mutex, musi być odblokowany, gdy ten konstruktor jest wywoływany.

Drugi Konstruktor nie blokuje *MTX*. *MTX* musi być zablokowany, gdy ten konstruktor jest wywoływany. Konstruktor nie zgłasza wyjątków.

## <a name="lock_guardlock_guard-destructor"></a><a name="dtorlock_guard_destructor"></a> lock_guard:: ~ lock_guard, destruktor

Odblokowuje `mutex` , który został przesłany do konstruktora.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Uwagi

Jeśli nie `mutex` istnieje w trakcie działania destruktora, zachowanie jest niezdefiniowane.

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)

---
description: Dowiedz się więcej &lt; o &gt; funkcjach i zmiennych mutex
title: '&lt;&gt;funkcje i zmienne muteksu'
ms.date: 11/04/2016
f1_keywords:
- mutex/std::adopt_lock
- mutex/std::call_once
- mutex/std::defer_lock
- mutex/std::lock
- mutex/std::try_to_lock
ms.assetid: 78ab3c8b-c7db-4226-ac93-e2e78ff8b964
helpviewer_keywords:
- std::adopt_lock [C++]
- std::call_once [C++]
- std::defer_lock [C++]
- std::lock [C++]
- std::try_to_lock [C++]
ms.openlocfilehash: e06fe09c78d8b79f5dd804e64ef11e84c558ba24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338260"
---
# <a name="ltmutexgt-functions-and-variables"></a>&lt;&gt;funkcje i zmienne muteksu

## <a name="adopt_lock"></a><a name="adopt_lock"></a> adopt_lock

Reprezentuje obiekt, który może zostać przesłany do konstruktorów dla [lock_guard](../standard-library/lock-guard-class.md) i [unique_lock](../standard-library/unique-lock-class.md) , aby wskazać, że obiekt mutex, który jest również przesyłany do konstruktora jest zablokowany.

```cpp
const adopt_lock_t adopt_lock;
```

## <a name="call_once"></a><a name="call_once"></a> call_once

Zapewnia mechanizm wywoływania określonego możliwego do wywołania obiektu dokładnie raz podczas wykonywania.

```cpp
template <class Callable, class... Args>
void call_once(once_flag& Flag,
    Callable F&&, Args&&... A);
```

### <a name="parameters"></a>Parametry

*Znacznik*\
Obiekt [once_flag](../standard-library/once-flag-structure.md) , który zapewnia, że obiekt możliwy do wywołania jest wywoływany tylko raz.

*N*\
Obiekt możliwy do narzutu.

*Z*\
Lista argumentów.

### <a name="remarks"></a>Uwagi

Jeśli *Flaga* jest nieprawidłowa, funkcja zgłasza [system_error](../standard-library/system-error-class.md) , który ma kod błędu `invalid_argument` . W przeciwnym razie funkcja szablonu używa jej argumentu *flagi* , aby upewnić się, że wywołuje `F(A...)` pomyślnie dokładnie jeden raz, niezależnie od tego, ile razy funkcja szablonu jest wywoływana. Jeśli `F(A...)` kończy działanie przez wyrzucanie wyjątku, wywołanie nie powiodło się.

## <a name="defer_lock"></a><a name="defer_lock"></a> defer_lock

Reprezentuje obiekt, który może zostać przesłany do konstruktora dla [unique_lock](../standard-library/unique-lock-class.md). Oznacza to, że Konstruktor nie powinien blokować obiektu mutex, który jest również przekazywać do niego.

```cpp
const defer_lock_t defer_lock;
```

## <a name="lock"></a><a name="lock"></a> skręt

Próbuje zablokować wszystkie argumenty bez zakleszczenia.

```cpp
template <class L1, class L2, class... L3>
void lock(L1&, L2&, L3&...);
```

### <a name="remarks"></a>Uwagi

Argumenty funkcji szablonu muszą być *typami muteksów*, z wyjątkiem tego, że wywołania `try_lock` mogą zgłaszać wyjątki.

Funkcja blokuje wszystkie argumenty bez zakleszczenia przez wywołania do `lock` , `try_lock` , i `unlock` . Jeśli wywołanie `lock` lub `try_lock` zgłasza wyjątek, funkcja wywołuje `unlock` wszystkie obiekty mutex, które zostały pomyślnie zablokowane przed ponownym zgłoszeniem wyjątku.

## <a name="swap"></a><a name="swap"></a> wymiany

```cpp
template <class Mutex>
void swap(unique_lock<Mutex>& x, unique_lock<Mutex>& y) noexcept;
```

## <a name="try_lock"></a><a name="try_lock"></a> try_lock

```cpp
template <class L1, class L2, class... L3> int try_lock(L1&, L2&, L3&...);
```

## <a name="try_to_lock"></a><a name="try_to_lock"></a> try_to_lock

Reprezentuje obiekt, który może zostać przesłany do konstruktora dla [unique_lock](../standard-library/unique-lock-class.md) , aby wskazać, że Konstruktor powinien próbować odblokować, `mutex` który jest również przekazywać do niego bez blokowania.

```cpp
const try_to_lock_t try_to_lock;
```

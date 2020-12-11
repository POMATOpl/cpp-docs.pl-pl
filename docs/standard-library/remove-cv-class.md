---
description: Dowiedz się więcej na temat klasy remove_cv
title: remove_cv — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_cv
helpviewer_keywords:
- remove_cv class
- remove_cv
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
ms.openlocfilehash: 2842c250ef46bf4fe1d36e6159bfaaf09b872034
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159690"
---
# <a name="remove_cv-class"></a>remove_cv — Klasa

Tworzy typ inny niż const/volatile z typu.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct remove_cv;

template <class T>
using remove_cv_t = typename remove_cv<T>::type;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Wystąpienie `remove_cv<T>` zawiera zmodyfikowany typ, który jest, `T1` gdy *t* ma postać `const T1` , `volatile T1` lub `const volatile T1` , w przeciwnym razie *t*.

## <a name="example"></a>Przykład

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_cv_t<const volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_cv_t<const volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_cv_t<const volatile int> == int
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[Klasa remove_const](../standard-library/remove-const-class.md)\
[Klasa remove_volatile](../standard-library/remove-volatile-class.md)

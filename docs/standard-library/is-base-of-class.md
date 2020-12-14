---
description: Dowiedz się więcej na temat klasy is_base_of
title: is_base_of — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_base_of
helpviewer_keywords:
- is_base_of class
- is_base_of
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
ms.openlocfilehash: 6cb2b55a6df687fbb7da74ca3c696a8a9b0ffbad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231267"
---
# <a name="is_base_of-class"></a>is_base_of — Klasa

Testuje, czy jeden typ jest podstawą innego.

## <a name="syntax"></a>Składnia

```cpp
template <class Base, class Derived>
struct is_base_of;
```

### <a name="parameters"></a>Parametry

*Opiera*\
Klasa bazowa do przetestowania.

*Pozyskiwan*\
Typ pochodny do przetestowania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *podstawowy* jest klasą bazową typu *pochodnego*, w przeciwnym razie ma wartość false.

## <a name="example"></a>Przykład

```cpp
#include <type_traits>
#include <iostream>

struct base
    {
    int val;
    };

struct derived
    : public base
    {
    };

int main()
    {
    std::cout << "is_base_of<base, base> == " << std::boolalpha
        << std::is_base_of<base, base>::value << std::endl;
    std::cout << "is_base_of<base, derived> == " << std::boolalpha
        << std::is_base_of<base, derived>::value << std::endl;
    std::cout << "is_base_of<derived, base> == " << std::boolalpha
        << std::is_base_of<derived, base>::value << std::endl;

    return (0);
    }
```

```Output
is_base_of<base, base> == true
is_base_of<base, derived> == true
is_base_of<derived, base> == false
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[Klasa is_convertible](../standard-library/is-convertible-class.md)

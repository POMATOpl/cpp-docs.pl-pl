---
description: Dowiedz się więcej na temat klasy is_convertible
title: is_convertible — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_convertible
helpviewer_keywords:
- is_convertible class
- is_convertible
ms.assetid: 75614008-1894-42ea-bd57-974399628536
ms.openlocfilehash: 4f5c9413eb33dd38d68929fe6b92f4581eced521
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231202"
---
# <a name="is_convertible-class"></a>is_convertible — Klasa

Testuje, czy jeden typ jest konwertowany na inny.

## <a name="syntax"></a>Składnia

```cpp
template <class From, class To>
struct is_convertible;
```

### <a name="parameters"></a>Parametry

*Wniosek*\
Typ, z którego ma zostać przeprowadzona konwersja.

*Br*\
Typ do przekonwertowania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli wyrażenie `To to = from;` , gdzie `from` jest obiektem typu `From` , jest poprawnie sformułowane.

## <a name="example"></a>Przykład

```cpp
// std__type_traits__is_convertible.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha
        << std::is_convertible<trivial, int>::value << std::endl;
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha
        << std::is_convertible<trivial, trivial>::value << std::endl;
    std::cout << "is_convertible<char, int> == " << std::boolalpha
        << std::is_convertible<char, int>::value << std::endl;

    return (0);
    }
```

```Output
is_convertible<trivial, int> == false
is_convertible<trivial, trivial> == true
is_convertible<char, int> == true
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[Klasa is_base_of](../standard-library/is-base-of-class.md)

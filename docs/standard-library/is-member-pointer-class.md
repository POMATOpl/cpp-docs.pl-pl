---
description: Dowiedz się więcej na temat klasy is_member_pointer
title: is_member_pointer — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_member_pointer
helpviewer_keywords:
- is_member_pointer class
- is_member_pointer
ms.assetid: da07ff4e-9ee0-4baa-ad93-1741f10913d1
ms.openlocfilehash: e1e2e5be39859109dd707f55a368fabe19f477a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323649"
---
# <a name="is_member_pointer-class"></a>is_member_pointer — Klasa

Testuje, czy typ jest wskaźnikiem do elementu członkowskiego.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_member_pointer;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *ty* jest wskaźnikiem do funkcji składowej lub wskaźnikiem do obiektu elementu członkowskiego lub z `cv-qualified` jednym z nich, w przeciwnym razie ma wartość false.

## <a name="example"></a>Przykład

```cpp
// std__type_traits__is_member_pointer.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct functional
    {
    int f();
    };

int main()
    {
    std::cout << "is_member_pointer<trivial *> == "
        << std::boolalpha
        << std::is_member_pointer<trivial *>::value
        << std::endl;
    std::cout << "is_member_pointer<int trivial::*> == "
        << std::boolalpha
        << std::is_member_pointer<int trivial::*>::value
        << std::endl;
    std::cout << "is_member_pointer<int (functional::*)()> == "
        << std::boolalpha
        << std::is_member_pointer<int (functional::*)()>::value
        << std::endl;

    return (0);
    }
```

```Output
is_member_pointer<trivial *> == false
is_member_pointer<int trivial::*> == true
is_member_pointer<int (functional::*)()> == true
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[Klasa is_member_function_pointer](../standard-library/is-member-function-pointer-class.md)\
[Klasa is_member_object_pointer](../standard-library/is-member-object-pointer-class.md)\
[Klasa is_pointer](../standard-library/is-pointer-class.md)

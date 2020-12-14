---
description: Dowiedz się więcej na temat klasy is_pointer
title: is_pointer — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_pointer
helpviewer_keywords:
- is_pointer class
- is_pointer
ms.assetid: 44e0a403-7241-4e0a-8922-32877bcb9a4c
ms.openlocfilehash: 003f25a40edd3f4c0b80a8402d38027cd81949cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230643"
---
# <a name="is_pointer-class"></a>is_pointer — Klasa

Testuje, czy typ jest wskaźnikiem.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_pointer;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *ty* jest wskaźnikiem do **`void`** , wskaźnikiem do obiektu lub wskaźnikiem do funkcji, lub `cv-qualified` postaci jednego z nich, w przeciwnym razie ma wartość false. Należy pamiętać, że `is_pointer` ma wartość false, jeśli *ty* jest wskaźnikiem do elementu członkowskiego lub wskaźnikiem do funkcji składowej.

## <a name="example"></a>Przykład

```cpp
// std__type_traits__is_pointer.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_pointer<trivial> == " << std::boolalpha
        << std::is_pointer<trivial>::value << std::endl;
    std::cout << "is_pointer<int trivial::*> == " << std::boolalpha
        << std::is_pointer<int trivial::*>::value << std::endl;
    std::cout << "is_pointer<trivial *> == " << std::boolalpha
        << std::is_pointer<trivial *>::value << std::endl;
    std::cout << "is_pointer<int> == " << std::boolalpha
        << std::is_pointer<int>::value << std::endl;
    std::cout << "is_pointer<int *> == " << std::boolalpha
        << std::is_pointer<int *>::value << std::endl;

    return (0);
    }
```

```Output
is_pointer<trivial> == false
is_pointer<int trivial::*> == false
is_pointer<trivial *> == true
is_pointer<int> == false
is_pointer<int *> == true
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[Klasa is_member_pointer](../standard-library/is-member-pointer-class.md)\
[Klasa is_reference](../standard-library/is-reference-class.md)

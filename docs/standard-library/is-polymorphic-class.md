---
description: Dowiedz się więcej na temat klasy is_polymorphic
title: is_polymorphic — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_polymorphic
helpviewer_keywords:
- is_polymorphic class
- is_polymorphic
ms.assetid: 4e1704db-d6f9-4154-a100-0ba02a373f20
ms.openlocfilehash: 983c27e0e314a5a4e9b3e71a3be8824e7de12512
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323528"
---
# <a name="is_polymorphic-class"></a>is_polymorphic — Klasa

Testuje, czy typ ma funkcję wirtualną.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_polymorphic;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie predykatu typu ma wartość true, jeśli typ *ty* jest klasą, która deklaruje lub dziedziczy funkcję wirtualną, w przeciwnym razie ma wartość false.

## <a name="example"></a>Przykład

```cpp
// std__type_traits__is_polymorphic.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct throws
    {
    throws() throw(int)
        {
        }

    throws(const throws&) throw(int)
        {
        }

    throws& operator=(const throws&) throw(int)
        {
        }

    virtual ~throws()
        {
        }

    int val;
    };

int main()
    {
    std::cout << "is_polymorphic<trivial> == " << std::boolalpha
        << std::is_polymorphic<trivial>::value << std::endl;
    std::cout << "is_polymorphic<throws> == " << std::boolalpha
        << std::is_polymorphic<throws>::value << std::endl;

    return (0);
    }
```

```Output
is_polymorphic<trivial> == false
is_polymorphic<throws> == true
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[Klasa is_abstract](../standard-library/is-abstract-class.md)

---
description: Dowiedz się więcej na temat klasy add_const
title: add_const — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_const
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
ms.openlocfilehash: ce1dd895a5968234feca7905d3b9f8d571336053
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319947"
---
# <a name="add_const-class"></a>add_const — Klasa

Tworzy typ const z typu.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>Parametry

*Br*\
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Wystąpienie modyfikatora typu posiada zmodyfikowany typ, który jest *ty* , jeśli *ty* jest odwołaniem, funkcją lub typem kwalifikowanym z kwalifikatorem, w przeciwnym razie `const Ty` .

## <a name="example"></a>Przykład

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](type-traits.md)\
[Klasa remove_const](remove-const-class.md)

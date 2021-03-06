---
description: Dowiedz się więcej na temat klasy add_volatile
title: add_volatile — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: 6f138c9009d127efe2d640124d9af1e114eb0732
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319872"
---
# <a name="add_volatile-class"></a>add_volatile — Klasa

Tworzy **`volatile`** Typ z określonego typu.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Wystąpienie `add_volatile<T>` ma element członkowski, który ma wartość **`typedef`** `type` *t* , jeśli *t* jest odwołaniem, funkcją lub typem kwalifikowanym nietrwałym, w przeciwnym razie **`volatile`** . Alias `add_volatile_t` jest skrótem, aby uzyskać dostęp do elementu członkowskiego **`typedef`** `type` .

## <a name="example"></a>Przykład

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_volatile_t<int> *p = (volatile int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_volatile<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_volatile<int> == int
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](type-traits.md)\
[Klasa remove_volatile](remove-volatile-class.md)

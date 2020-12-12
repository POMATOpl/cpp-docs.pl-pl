---
description: Dowiedz się więcej na temat klasy add_pointer
title: add_pointer — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_pointer
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
ms.openlocfilehash: 36f262c68c17dbcaca603c2a78e2450f0de64aa6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319898"
---
# <a name="add_pointer-class"></a>add_pointer — Klasa

Tworzy wskaźnik do typu z określonego typu.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct add_pointer;

template <class T>
using add_pointer_t = typename add_pointer<T>::type;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Nazwa elementu członkowskiego tego **`typedef`** `type` samego typu co `remove_reference<T>::type*` . Alias `add_pointer_t` jest skrótem, aby uzyskać dostęp do elementu członkowskiego **`typedef`** `type` .

Ponieważ nie jest to prawidłowe, aby można było utworzyć wskaźnik z odwołania, `add_pointer` usuwa odwołanie, jeśli istnieje, z określonego typu, zanim przetworzy wskaźnik do typu. W związku z tym można użyć typu z `add_pointer` bez względu na to, czy typ jest odwołaniem.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, że `add_pointer` Typ jest taki sam jak wskaźnik do tego typu.

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_pointer_t<int> *p = (int **)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_pointer_t<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_pointer_t<int> == int *
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](type-traits.md)\
[Klasa remove_pointer](remove-pointer-class.md)

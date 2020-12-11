---
description: Dowiedz się więcej na temat klasy remove_reference
title: remove_reference — Klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_reference
helpviewer_keywords:
- remove_reference class
- remove_reference
ms.assetid: 294e1965-3ae3-46ee-bc42-4fdf60c24717
ms.openlocfilehash: ccde3e2070e38ca06ca519b7c184fce7dcdbb90d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159625"
---
# <a name="remove_reference-class"></a>remove_reference — Klasa

Tworzy typ inny niż odwołanie z typu.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
struct remove_reference;

template <class T>
using remove_reference_t = typename remove_reference<T>::type;
```

### <a name="parameters"></a>Parametry

*&*\
Typ do modyfikacji.

## <a name="remarks"></a>Uwagi

Wystąpienie ma `remove_reference<T>` zmodyfikowany typ, który jest `T1` , gdy *t* ma postać `T1&` , w przeciwnym razie *t*.

## <a name="example"></a>Przykład

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_reference_t<int&> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_reference_t<int&> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_reference_t<int&> == int
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<type_traits>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[<type_traits>](../standard-library/type-traits.md)\
[Klasa add_lvalue_reference](../standard-library/add-lvalue-reference-class.md)

---
title: is_function — klasa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is
dev_langs:
- C++
helpviewer_keywords:
- is_function class
- is
ms.assetid: e5c0dbcd-829b-415f-853f-8c5be47c5040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f470f07c59860118b682784dca6c83587ee87b04
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
---
# <a name="isfunction-class"></a>is_function — Klasa

Testy, jeśli typ jest typem funkcji.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_function;
```

### <a name="parameters"></a>Parametry

`Ty` Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie typu predykatu posiada wartość true Jeśli typ `Ty` jest typem funkcji, w przeciwnym razie posiada wartość false.

## <a name="example"></a>Przykład

```cpp
// std__type_traits__is_function.cpp
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
    std::cout << "is_function<trivial> == " << std::boolalpha
        << std::is_function<trivial>::value << std::endl;
    std::cout << "is_function<functional> == " << std::boolalpha
        << std::is_function<functional>::value << std::endl;
    std::cout << "is_function<float()> == " << std::boolalpha
        << std::is_function<float()>::value << std::endl;

    return (0);
    }

```

```Output
is_function<trivial> == false
is_function<functional> == false
is_function<float()> == true
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<type_traits >

**Namespace:** Standard

## <a name="see-also"></a>Zobacz także

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_object, klasa](../standard-library/is-object-class.md)<br/>

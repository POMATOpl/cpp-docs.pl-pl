---
title: is_empty — klasa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_empty
dev_langs:
- C++
helpviewer_keywords:
- is_empty class
- is_empty
ms.assetid: 44a6fc92-7e55-4fbe-9a24-2a0ce2dccba0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10fe3f311211e3bbde61aef37c9a152ba2105126
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843577"
---
# <a name="isempty-class"></a>is_empty — Klasa

Testy, jeśli typ jest pustą klasę.

## <a name="syntax"></a>Składnia

```cpp
template <class Ty>
struct is_empty;
```

### <a name="parameters"></a>Parametry

`Ty` Typ do zapytania.

## <a name="remarks"></a>Uwagi

Wystąpienie typu predykatu posiada wartość true Jeśli typ `Ty` jest pustą klasę, w przeciwnym razie posiada wartość false.

## <a name="example"></a>Przykład

```cpp
// std__type_traits__is_empty.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct empty
    {
    };

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_empty<trivial> == " << std::boolalpha
        << std::is_empty<trivial>::value << std::endl;
    std::cout << "is_empty<empty> == " << std::boolalpha
        << std::is_empty<empty>::value << std::endl;
    std::cout << "is_empty<int> == " << std::boolalpha
        << std::is_empty<int>::value << std::endl;

    return (0);
    }

```

```Output
is_empty<trivial> == false
is_empty<empty> == true
is_empty<int> == false
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<type_traits >

**Namespace:** Standard

## <a name="see-also"></a>Zobacz także

[<type_traits>](../standard-library/type-traits.md)<br/>

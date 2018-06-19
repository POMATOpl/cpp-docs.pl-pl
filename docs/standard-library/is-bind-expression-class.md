---
title: is_bind_expression — klasa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::is_bind_expression
dev_langs:
- C++
helpviewer_keywords:
- is_bind_expression class
ms.assetid: 0715f9e9-2239-4778-a1cf-2c21f49dfd47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38cf4c4e9e92704e1f6ce635f2a429b4dc9bfcbb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842165"
---
# <a name="isbindexpression-class"></a>is_bind_expression — Klasa

Sprawdza, czy typ jest generowany przez wywołanie metody `bind`.

## <a name="syntax"></a>Składnia

Szablon<class Ty> is_bind_expression — struktura {const bool wartości statycznej;};

## <a name="remarks"></a>Uwagi

Członek stałej `value` jest wartość true, jeśli typ `Ty` jest typ zwrócony przez wywołanie do `bind`, w przeciwnym razie wartość false.

## <a name="example"></a>Przykład

```cpp
// std__functional__is_bind_expression.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

template<class Expr>
void test_for_bind(const Expr&)
{
    std::cout << std::is_bind_expression<Expr>::value << std::endl;
}

int main()
{
    test_for_bind(3.0 * 3.0);
    test_for_bind(std::bind(square, 3));

    return (0);
}
```

```Output
0
1
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<funkcjonalności >

**Namespace:** Standard

## <a name="see-also"></a>Zobacz także

[BIND](../standard-library/functional-functions.md#bind)<br/>

---
description: 'Dowiedz się więcej o: Jednoargumentowe operatory arytmetyczne'
title: Jednoargumentowe operatory arytmetyczne
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], unary
- tilde (~) one's complement operator
- bitwise-complement operator
- arithmetic operators [C++], unary
- + operator, unary operators
- unary operators
- exclamation points
- ~ operator, one's complement operator
- logical negation
- '! operator, unary arithmetic operators'
ms.assetid: 78c91415-d469-499e-9dfe-4435350fd333
ms.openlocfilehash: e4abf78f0db41d85a5954137fac1dba913735a1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318406"
---
# <a name="unary-arithmetic-operators"></a>Jednoargumentowe operatory arytmetyczne

Jednoargumentowy C plus, negacja arytmetyczna, uzupełnienie i operatory negacji logicznej omawiane są na poniższej liście:

|Operator|Opis|
|--------------|-----------------|
|**+**|Jednoargumentowy operator plus poprzedzający wyrażenie w nawiasach wymusza grupowanie zamkniętych działań. Jest używany z wyrażeniami dotyczącymi więcej niż jednego operatora binarnego zespolonego lub przemiennego. Argument musi być typu arytmetycznego. Wynikiem jest wartość operandu. Operand wewnętrzny ulega promocji typu całkowitego. Typ wyniku jest typem promowanego operandu.|
|**-**|Operator arytmetyczny negacji daje wartość negatywną (dopełnienie dwójki) swojego operandu. Argument musi być wartością typu całkowitego lub zmiennoprzecinkowego. Ten operator wykonuje zwykle konwersje arytmetyczne.|
|`~`|Operator uzupełnienia bitowego (lub bitowego NOT) wytwarza bitowe uzupełnienie swojego operandu. Argument musi być typu całkowitego. Ten operator wykonuje zwykle konwersje arytmetyczne; wynik ma typ operandu po konwersji.|
|**!**|Operator logiczny negacji (logicznego NOT) produkuje wartość 0, jeżeli jej operand ma wartość true (niezerową) i wartość 1, jeśli jej operand ma wartość false (0). Wynik ma **`int`** Typ. Operand musi być wartością typu całkowitego, zmiennoprzecinkowego lub wartością wskaźnika.|

Jednoargumentowe operatory arytmetyczne na wskaźniki są niedozwolone.

## <a name="examples"></a>Przykłady

Poniższe przykłady ilustrują jednoargumentowe operatory arytmetyczne:

```
short x = 987;
    x = -x;
```

W powyższym przykładzie nowa wartość jest wartością `x` ujemną równą 987 lub-987.

```
unsigned short y = 0xAAAA;
    y = ~y;
```

W tym przykładzie nowa wartość przypisana do `y` jest uzupełnieniem wartości bez znaku 0xAAAA lub 0x5555.

```
if( !(x < y) )
```

Jeśli `x` jest większy lub równy od `y`, wynikiem wyrażenia jest 1 (true). Jeśli `x` jest mniejszy od `y`, wynik jest równy 0 (false).

## <a name="see-also"></a>Zobacz też

[Wyrażenia z operatorami jednoargumentowymi](../cpp/expressions-with-unary-operators.md)

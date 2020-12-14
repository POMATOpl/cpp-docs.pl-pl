---
description: 'Dowiedz się więcej o: typowe konwersje arytmetyczne'
title: Popularne konwersje arytmetyczne
ms.date: 11/04/2016
helpviewer_keywords:
- arithmetic conversions [C++]
- type conversion [C++], arithmetic
- operators [C], arithmetic conversions
- data type conversion [C++], arithmetic
- conversions [C++], arithmetic
- arithmetic operators [C++], type conversions
ms.assetid: bfa49803-0efd-45d0-b987-111412a140d7
ms.openlocfilehash: 443d61b3ff295431a5c1507886cb0821a1f5b205
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198898"
---
# <a name="usual-arithmetic-conversions"></a>Popularne konwersje arytmetyczne

Większość operatorów języka C wykonuje konwersje typów, aby przenieść operandy wyrażenia do wspólnego typu lub w celu rozdzielenia krótkich wartości do rozmiaru całkowitego używanego w operacjach maszynowych. Konwersje wykonywane przez operatory języka C zależą od określonego operatora i typu operandu lub operandów. Jednak wiele operatorów wykonuje podobne konwersje na operandach typu całkowitego i zmiennoprzecinkowego. Te konwersje są znane jako "konwersje arytmetyczne". Konwersja wartości operandu na typ zgodny nie powoduje zmiany jej wartości.

Wymienione poniżej konwersje arytmetyczne są nazywane "typowymi konwersjemi arytmetycznymi". Te kroki są stosowane tylko w przypadku operatorów binarnych, które oczekują typu arytmetycznego. Celem jest uzyskanie wspólnego typu, który jest również typem wyniku. Aby określić, które konwersje rzeczywiście miały miejsce, kompilator stosuje następujący algorytm do operacji binarnych w wyrażeniu. Poniższe kroki nie są kolejnością pierwszeństwa.

1. Jeśli oba operandy są typu **`long double`** , drugi operand jest konwertowany na typ **`long double`** .

1. Jeśli powyższy warunek nie jest spełniony, a każdy z operandów jest typu **`double`** , drugi operand jest konwertowany na typ **`double`** .

1. Jeśli powyższe dwa warunki nie są spełnione, a oba operandy są typu **`float`** , drugi operand jest konwertowany na typ **`float`** .

1. Jeśli powyższe trzy warunki nie są spełnione (żaden z operandów nie ma typów zmiennoprzecinkowych), konwersje całkowite są wykonywane na operandach w następujący sposób:

   - Jeśli oba operandy są typu **`unsigned long`** , drugi operand jest konwertowany na typ **`unsigned long`** .

   - Jeśli powyższy warunek nie jest spełniony, a którykolwiek z operandów jest typu **`long`** i innego typu **`unsigned int`** , oba operandy są konwertowane na typ **`unsigned long`** .

   - Jeśli powyższe dwa warunki nie są spełnione, a oba operandy są typu **`long`** , drugi operand jest konwertowany na typ **`long`** .

   - Jeśli powyższe trzy warunki nie są spełnione, a oba operandy są typu **`unsigned int`** , drugi operand jest konwertowany na typ **`unsigned int`** .

   - Jeśli żaden z powyższych warunków nie zostanie spełniony, oba operandy są konwertowane na typ **`int`** .

Poniższy kod ilustruje następujące reguły konwersji:

```
float   fVal;
double  dVal;
int   iVal;
unsigned long ulVal;

dVal = iVal * ulVal; /* iVal converted to unsigned long
                      * Uses step 4.
                      * Result of multiplication converted to double
                      */
dVal = ulVal + fVal; /* ulVal converted to float
                      * Uses step 3.
                      * Result of addition converted to double
                      */
```

## <a name="see-also"></a>Zobacz też

[Operatory języka C](../c-language/c-operators.md)

---
description: 'Dowiedz się więcej na temat: Dlaczego Floating-Point liczby mogą utracić dokładnooć'
title: Dlaczego liczby zmiennoprzecinkowe mogą tracić dokładność
ms.date: 11/04/2016
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
ms.openlocfilehash: 97daabd7342e94022f309937c9986b61cbc8668c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120773"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>Dlaczego liczby zmiennoprzecinkowe mogą tracić dokładność

Wartości dziesiętne zmiennoprzecinkowe zwykle nie mają dokładnej reprezentacji binarnej. Jest to efekt uboczny przedstawiający sposób, w jaki procesor CPU reprezentuje dane zmiennoprzecinkowe. Z tego powodu może wystąpić pewna utrata dokładności, a niektóre operacje zmiennoprzecinkowe mogą spowodować nieoczekiwane wyniki.

To zachowanie jest wynikiem jednego z następujących elementów:

- Reprezentacja binarna liczby dziesiętnej może być niedokładna.

- Występuje niezgodność typów między używanymi liczbami (na przykład mieszanie zmiennoprzecinkowe i podwójne).

Aby rozwiązać ten problem, większość programistów upewnia się, że wartość jest większa lub mniejsza niż to, co jest potrzebne, lub uzyskuje i używa biblioteki binarnej kodowanej dziesiętnej (BCD), która będzie zachować precyzję.

Reprezentacja binarna wartości zmiennoprzecinkowych ma wpływ na precyzję i dokładność obliczeń zmiennoprzecinkowych. Microsoft Visual C++ używa [formatu IEEE zmiennoprzecinkowego](ieee-floating-point-representation.md).

## <a name="example"></a>Przykład

```c
// Floating-point_number_precision.c
// Compile options needed: none. Value of c is printed with a decimal
// point precision of 10 and 6 (printf rounded value by default) to
// show the difference
#include <stdio.h>

#define EPSILON 0.0001   // Define your own tolerance
#define FLOAT_EQ(x,v) (((v - EPSILON) < x) && (x <( v + EPSILON)))

int main() {
   float a, b, c;

   a = 1.345f;
   b = 1.123f;
   c = a + b;
   // if (FLOAT_EQ(c, 2.468)) // Remove comment for correct result
   if (c == 2.468)            // Comment this line for correct result
      printf_s("They are equal.\n");
   else
      printf_s("They are not equal! The value of c is %13.10f "
                "or %f",c,c);
}
```

```Output
They are not equal! The value of c is  2.4679999352 or 2.468000
```

## <a name="comments"></a>Komentarze

W przypadku wartości EPSILON można użyć stałych FLT_EPSILON, które są zdefiniowane dla wartości zmiennoprzecinkowych jako 1.192092896 e-07F lub DBL_EPSILON, które są zdefiniowane dla podwójnego 2.2204460492503131 e-016. Musisz dołączyć wartości zmiennoprzecinkowe. h dla tych stałych. Te stałe są definiowane jako najmniejszy dodatnia liczba x, tak że x + 1.0 nie jest równe 1,0. Ponieważ jest to bardzo mała liczba, należy zastosować tolerancję zdefiniowaną przez użytkownika dla obliczeń obejmujących bardzo duże liczby.

## <a name="see-also"></a>Zobacz też

[Optymalizowanie kodu](optimizing-your-code.md)

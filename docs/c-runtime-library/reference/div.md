---
title: DIV, ldiv, LLDiv
description: Funkcja DIV, ldiv i LLDiv biblioteki środowiska uruchomieniowego Microsoft C oblicza iloraz i resztę dwóch wartości całkowitych.
ms.date: 11/21/2020
api_name:
- div
- ldiv
- lldiv
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-utility-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- div
- ldiv
- lldiv
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.openlocfilehash: d87b2e3a84e389be8b14970a3aa611bb288cbec8
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440283"
---
# <a name="div-ldiv-lldiv"></a>`div`, `ldiv`, `lldiv`

Oblicza iloraz i resztę dwóch wartości całkowitych.

## <a name="syntax"></a>Składnia

```C
div_t div(
   int numer,
   int denom
);
ldiv_t ldiv(
   long numer,
   long denom
);
lldiv_t lldiv(
   long long numer,
   long long denom
);
```

```cpp
ldiv_t div(
   long numer,
   long denom
); /* C++ only */
lldiv_t div(
   long long numer,
   long long denom
); /* C++ only */
```

### <a name="parameters"></a>Parametry

*`numer`*\
Licznik.

*`denom`*\
Mianownik.

## <a name="return-value"></a>Wartość zwracana

**`div`** wywoływana za pomocą argumentów typu **`int`** zwraca strukturę typu `div_t` , która zawiera iloraz i resztę. Wartością zwracaną z argumentami typu **`long`** jest `ldiv_t` , a zwracaną wartością z argumentami typu **`long long`** jest `lldiv_t` . `div_t`Typy, `ldiv_t` i `lldiv_t` są zdefiniowane w \<stdlib.h> .

## <a name="remarks"></a>Uwagi

**`div`** Funkcja jest dzielona *`numer`* przez *`denom`* i oblicza iloraz i resztę. [`div_t`](../../c-runtime-library/standard-types.md)Struktura zawiera iloraz, `quot` i resztę, `rem` . Znak ilorazu jest taki sam jak znak ilorazu matematycznego. Wartość bezwzględna jest największą liczbą całkowitą, która jest mniejsza niż wartość bezwzględna ilorazu matematycznego. Jeśli mianownik ma wartość 0, program kończy pracę z komunikatem o błędzie.

Przeciążenia **`div`** przyjmujące argumenty typu **`long`** lub **`long long`** są dostępne tylko dla kodu C++. Typy zwracane [`ldiv_t`](../../c-runtime-library/standard-types.md) i [`lldiv_t`](../../c-runtime-library/standard-types.md) zawiera elementy członkowskie `quot` i `rem` , które mają takie same znaczenie jak elementy członkowskie `div_t` .

## <a name="requirements"></a>Wymagania

| Procedura | Wymagany nagłówek |
|--|--|
| **`div`**, **`ldiv`**, **`lldiv`** | \<stdlib.h> |

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_div.c
// arguments: 876 13

// This example takes two integers as command-line
// arguments and displays the results of the integer
// division. This program accepts two arguments on the
// command line following the program name, then calls
// div to divide the first argument by the second.
// Finally, it prints the structure members quot and rem.
//

#include <stdlib.h>
#include <stdio.h>
#include <math.h>

int main( int argc, char *argv[] )
{
   int x,y;
   div_t div_result;

   x = atoi( argv[1] );
   y = atoi( argv[2] );

   printf( "x is %d, y is %d\n", x, y );
   div_result = div( x, y );
   printf( "The quotient is %d, and the remainder is %d\n",
           div_result.quot, div_result.rem );
}
```

```Output
x is 876, y is 13
The quotient is 67, and the remainder is 5
```

## <a name="see-also"></a>Zobacz także

[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)\
[`imaxdiv`](imaxdiv.md)

---
title: DIV ldiv —, lldiv — | Dokumenty Microsoft
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- div
apilocation:
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
apitype: DLLExport
f1_keywords:
- div
dev_langs:
- C++
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ba1625105adf6edbc6419bd4fdabc8bda5d0e98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396595"
---
# <a name="div-ldiv-lldiv"></a>DIV ldiv —, lldiv —

Oblicza iloraz i pozostałej części dwóch wartości całkowite.

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

*numer*<br/>
Licznik.

*denom*<br/>
Denominator.

## <a name="return-value"></a>Wartość zwracana

**DIV** wywoływane przy użyciu argumentów typu **int** zwraca struktura typu **div_t —**, która obejmuje iloraz, a reszta. Wartość zwracana z argumentami typu **długi** jest **ldiv_t —** i wartość zwracaną z argumentami typu **długi** **długi** jest **lldiv_t**. **div_t —**, **ldiv_t —**, i **lldiv_t** są zdefiniowane w \<stdlib.h >.

## <a name="remarks"></a>Uwagi

**Div** funkcji bez reszty *numer* przez *denom* i tym samym oblicza iloraz, a reszta. [Div_t —](../../c-runtime-library/standard-types.md) struktura zawiera iloraz, **quot**, a reszta, **rem**. Znak iloraz jest taka sama jak iloraz matematycznych. Największa liczba całkowita, która jest mniejsza niż wartość bezwzględną liczby matematyczne iloraz ma jego wartość bezwzględna. Jeżeli dzielnik wynosi 0, program zakończy się z komunikatem o błędzie.

Przeciążeń **div** argumentów typu, które wymagają **długi** lub **długi** **długi** są dostępne tylko dla kodu języka C++. Zwracane typy [ldiv_t —](../../c-runtime-library/standard-types.md) i [lldiv_t](../../c-runtime-library/standard-types.md) zawiera elementy członkowskie **quot** i **rem**, który ma tego samego znaczenia jak członkowie **div_t —**.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**DIV**, **ldiv —**, **lldiv —**|\<stdlib.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md).

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

[Obsługa liczb zmiennoprzecinkowych](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>

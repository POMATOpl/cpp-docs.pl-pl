---
title: DIV ldiv, lldiv
ms.date: 04/05/2018
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
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
ms.openlocfilehash: 0ee1b3b6a5d7b15470ffe1e667b4077d1f9581e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339263"
---
# <a name="div-ldiv-lldiv"></a>DIV ldiv, lldiv

Oblicza iloraz i resztę dwóch liczb całkowitych.

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
Mianownik.

## <a name="return-value"></a>Wartość zwracana

**DIV** wywołana z wykorzystaniem argumentów typu **int** zwraca strukturę typu **div_t**, który obejmuje iloraz i resztę. Wartość zwracana z argumentami typu **długie** jest **ldiv_t**i wartość zwracana z argumentami typu **długie** **długie** jest **lldiv_t**. **div_t**, **ldiv_t**, i **lldiv_t** są zdefiniowane w \<stdlib.h >.

## <a name="remarks"></a>Uwagi

**Div** funkcja dzieli *numer* przez *denom* a tym samym oblicza iloraz i resztę. [Div_t](../../c-runtime-library/standard-types.md) struktura zawiera iloraz, **quot**, jak i resztę, **rem**. Znak iloraz jest tożsamy z ilorazem matematycznych. Wartość bezwzględna jest największą liczbą całkowitą, która jest mniejsza niż wartość bezwzględna ilorazu matematycznego. Jeżeli mianownik wynosi 0, program kończy się komunikat o błędzie.

Przeciążenia **div** które przyjmują argumenty typu **długie** lub **długie** **długie** są dostępne tylko dla kodu w języku C++. Typy zwracane występujące [ldiv_t](../../c-runtime-library/standard-types.md) i [lldiv_t](../../c-runtime-library/standard-types.md) zawiera elementy członkowskie **quot** i **rem**, które mają samych znaczeń jako członkowie **div_t**.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**DIV**, **ldiv**, **lldiv**|\<stdlib.h>|

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

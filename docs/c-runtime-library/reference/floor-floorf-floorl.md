---
title: floor, floorf, floorl
description: Dokumentacja interfejsu API dla podłogi, floorf — i podłogi; który oblicza piętro wartości.
ms.date: 9/1/2020
api_name:
- floorf
- floorl
- floor
- _o_floor
- _o_floorf
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
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- floor
- floorl
- _floorl
- floorf
helpviewer_keywords:
- floor function
- floorf function
- calculating floors of values
- floorl function
ms.assetid: e9955f70-d659-414f-8050-132e13c8ff36
ms.openlocfilehash: 6af047d3da891270ab6a596dfc3ebef0941a91cf
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556739"
---
# <a name="floor-floorf-floorl"></a>floor, floorf, floorl

Oblicza piętro wartości.

## <a name="syntax"></a>Składnia

```C
double floor(
   double x
);
float floor(
   float x
); // C++ only
long double floor(
   long double x
); // C++ only
float floorf(
   float x
);
long double floorl(
   long double x
);
#define floor(X) // Requires C11 or higher
```

### <a name="parameters"></a>Parametry

*y*\
Wartość zmiennoprzecinkowa.

## <a name="return-value"></a>Wartość zwracana

Funkcje **podłogi** zwracają wartość zmiennoprzecinkową, która reprezentuje największą liczbę całkowitą, która jest mniejsza lub równa *x*. Nie ma żadnego powrotu błędu.

|Dane wejściowe|Wyjątek SEH|Wyjątek Matherr|
|-----------|-------------------|-----------------------|
|QNAN, IND|brak|_DOMAIN|

**piętro** ma implementację, która używa Streaming SIMD Extensions 2 (SSE2). Informacje i ograniczenia dotyczące korzystania z implementacji SSE2 można znaleźć w temacie [_set_SSE2_enable](set-sse2-enable.md).

## <a name="remarks"></a>Uwagi

Język C++ pozwala na Przeciążenie, dlatego można wywoływać przeciążenia, **które** pobierają i zwracają **`float`** **`long double`** wartości. W programie C, jeśli nie używasz \<tgmath.h> makra do wywołania tej funkcji, **podłoga** zawsze przyjmuje i zwraca **`double`** .

Jeśli używasz \<tgmath.h> `floor()` makra, typ argumentu określa, która wersja funkcji jest wybrana. Aby uzyskać szczegółowe informacje, zobacz [matematyka typu ogólnego](../../c-runtime-library/tgmath.md) .

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**piętro**, **floorf —y**, **piętro**|\<math.h>|
|**Floor** — makro | \<tgmath.h> ||

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_floor.c
// This example displays the largest integers
// less than or equal to the floating-point values 2.8
// and -2.8. It then shows the smallest integers greater
// than or equal to 2.8 and -2.8.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double y;

   y = floor( 2.8 );
   printf( "The floor of 2.8 is %f\n", y );
   y = floor( -2.8 );
   printf( "The floor of -2.8 is %f\n", y );

   y = ceil( 2.8 );
   printf( "The ceil of 2.8 is %f\n", y );
   y = ceil( -2.8 );
   printf( "The ceil of -2.8 is %f\n", y );
}
```

```Output
The floor of 2.8 is 2.000000
The floor of -2.8 is -3.000000
The ceil of 2.8 is 3.000000
The ceil of -2.8 is -2.000000
```

## <a name="see-also"></a>Zobacz też

[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[round, roundf, roundl](round-roundf-roundl.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>

---
title: atanh, atanhf, atanhl
description: Dokumentacja interfejsu API dla atanh —, atanhf — i atanhl; które oblicza odwrotny tangens hiperboliczny wartości zmiennoprzecinkowej.
ms.date: 08/31/2020
api_name:
- atanhl
- atanhf
- atanh
- _o_atanh
- _o_atanhf
- _o_atanhl
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
- atanhl
- atanhf
- atanh
helpviewer_keywords:
- atanhf function
- atanhl function
- atanh funciton
ms.assetid: 83a43b5b-2580-4461-854f-dc84236d9f32
ms.openlocfilehash: c0a8e06963519553144c7e49d26e61dbbde51c21
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89555595"
---
# <a name="atanh-atanhf-atanhl"></a>atanh, atanhf, atanhl

Oblicza odwrotny tangens hiperboliczny.

## <a name="syntax"></a>Składnia

```C
double atanh( double x );
float atanhf( float x );
long double atanhl( long double x );
#define atanh(X) // Requires C11 or higher

float atanh( float x );  // C++ only
long double atanh( long double x );  // C++ only
```

### <a name="parameters"></a>Parametry

*y*\
Wartość zmiennoprzecinkowa.

## <a name="return-value"></a>Wartość zwracana

Funkcje **ATANH —** zwracają arcus tangens hyberbolic (łuk hiperboliczny) *x*. Jeśli wartość *x* jest większa niż 1 lub mniejsza niż-1, **errno** jest ustawiona na **Edom** , a wynikiem jest cichy NaN. Jeśli wartość *x* jest równa 1 lub-1, zwracana jest nieskończona lub ujemna Negacja, odpowiednio i **errno** jest ustawiona na **ERANGE**.

|Dane wejściowe|Wyjątek SEH|**Matherr** Oprócz|
|-----------|-------------------|-------------------------|
|QNAN, IND|brak|brak|
|*X* ≥ 1; *x* ≤-1|brak|brak|

## <a name="remarks"></a>Uwagi

Ponieważ C++ pozwala na Przeciążenie, można wywoływać przeciążenia **ATANH —** , które pobierają i zwracają **`float`** **`long double`** wartości. W programie C, jeśli nie używasz \<tgmath.h> makra do wywołania tej funkcji, **ATANH —** zawsze przyjmuje i zwraca **`double`** .

Jeśli używasz \<tgmath.h> `atanh()` makra, typ argumentu określa, która wersja funkcji jest wybrana. Aby uzyskać szczegółowe informacje, zobacz [matematyka typu ogólnego](../../c-runtime-library/tgmath.md) .

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Nagłówek języka C|Nagłówek C++|
|--------------|--------------|------------------|
|**ATANH —**, **atanhf —**, **atanhl**|\<math.h>|\<cmath> lub \<math.h>|
|**ATANH — ()** — makro | \<tgmath.h> ||

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_atanh.c
// This program displays the hyperbolic tangent of pi / 4
// and the arc hyperbolic tangent of the result.
//

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = tanh( pi / 4 );
   y = atanh( x );
   printf( "tanh( %f ) = %f\n", pi/4, x );
   printf( "atanh( %f ) = %f\n", x, y );
}
```

```Output
tanh( 0.785398 ) = 0.655794
atanh( 0.655794 ) = 0.785398
```

## <a name="see-also"></a>Zobacz też

[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>

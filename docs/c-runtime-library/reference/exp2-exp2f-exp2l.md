---
title: exp2, exp2f, exp2l
description: Odwołania do interfejsu API dla exp2 — (), exp2f — () i exp2l (), które oblicza wartość 2 podniesioną do określonej wartości.
ms.date: 9/1/2020
api_name:
- exp2
- exp2f
- exp2l
- _o_exp2
- _o_exp2f
- _o_exp2l
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
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
ms.openlocfilehash: 518525a38ef575583fde3b7732561f2fa553dd18
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556622"
---
# <a name="exp2-exp2f-exp2l"></a>exp2, exp2f, exp2l

Oblicza wartość 2 podniesioną do określonej wartości.

## <a name="syntax"></a>Składnia

```C
double exp2(
   double x
);

float exp2(
   float x
);  // C++ only

long double exp2(
   long double x
); // C++ only

float exp2f(
   float x
);

long double exp2l(
   long double x
);
#define exp2(X) // Requires C11 or higher
```

### <a name="parameters"></a>Parametry

*y*\
Wartość wykładnika.

## <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, zwraca wykładnik Base-2 *x*, czyli 2<sup>x</sup>. W przeciwnym razie zwraca jedną z następujących wartości:

|Problem|Przesłać|
|-----------|------------|
|*x* = ± 0|1|
|*x* = — nieskończoność|+0|
|*x* = + nieskończoność|+ NIESKOŃCZONość|
|*x* = NaN|NaN|
|Błąd przepełnienia zakresu|+ HUGE_VAL, + HUGE_VALF lub + HUGE_VALL|
|Błąd zakresu niedopełnienia|Prawidłowy wynik po zaokrągleniu|

Błędy są raportowane zgodnie z opisem w [_matherr](matherr.md).

## <a name="remarks"></a>Uwagi

Ponieważ C++ pozwala na Przeciążenie, można wywoływać przeciążenia **exp2 —** , które pobierają i zwracają **`float`** **`long double`** typy. W programie C, jeśli nie używasz \<tgmath.h> makra do wywołania tej funkcji, **exp2 —** zawsze przyjmuje i zwraca **`double`** , chyba że używasz makra w <tgmath. h>.

Jeśli używasz \<tgmath.h> `exp2()` makra, typ argumentu określa, która wersja funkcji jest wybrana. Aby uzyskać szczegółowe informacje, zobacz [matematyka typu ogólnego](../../c-runtime-library/tgmath.md) .

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Nagłówek języka C|Nagłówek C++|
|-------------|--------------|------------------|
|**exp2 —**, **expf2**, **expl2**|\<math.h>|\<cmath>|
|**exp2 —** — makro | \<tgmath.h> ||

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>

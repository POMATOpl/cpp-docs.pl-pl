---
title: cbrt, cbrtf, cbrtl
ms.date: 4/2/2020
api_name:
- cbrt
- cbrtf
- cbrtl
- _o_cbrt
- _o_cbrtf
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- cbrtl
- cbrt
- cbrtf
helpviewer_keywords:
- cbrtl function
- cbrtf function
- cbrt function
ms.assetid: ab51d916-3db2-4beb-b46a-28b4062cd33f
ms.openlocfilehash: a63c30368e23feda4b7845f367ad394249a50d4d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333568"
---
# <a name="cbrt-cbrtf-cbrtl"></a>cbrt, cbrtf, cbrtl

Oblicza katalog główny modułu.

## <a name="syntax"></a>Składnia

```C
double cbrt(
   double x
);
float cbrt(
   float x
);  // C++ only
long double cbrt(
   long double x
);  // C++ only
float cbrtf(
   float x
);
long double cbrtl(
   long double x
);
```

### <a name="parameters"></a>Parametry

*X*<br/>
Wartość zmiennoprzecinowa

## <a name="return-value"></a>Wartość zwracana

Funkcje **cbrt** zwracają katalog główny x *.*

|Dane wejściowe|Wyjątek SEH|**_matherr** Wyjątek|
|-----------|-------------------|--------------------------|
|± ∞, QNAN, IND|brak|brak|

## <a name="remarks"></a>Uwagi

Ponieważ C++ umożliwia przeciążenie, można wywołać przeciążenia **cbrt,** które mają **float** lub **długie** **podwójne** typy. W programie **C, cbrt** zawsze ma i zwraca **dwukrotnie**.

Domyślnie stan globalny tej funkcji jest ograniczony do aplikacji. Aby to zmienić, zobacz [Stan globalny w crt](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Nagłówek C|Nagłówek języka C++|
|--------------|--------------|------------------|
|**cbrt**, **cbrtf**, **cbrtl**|\<> math.h|\<> cmath|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [Zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_cbrt.c
// Compile using: cl /W4 crt_cbrt.c
// This program calculates a cube root.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double question = -64.64;
   double answer;

   answer = cbrt(question);
   printf("The cube root of %.2f is %.6f\n", question, answer);
}
```

```Output
The cube root of -64.64 is -4.013289
```

## <a name="see-also"></a>Zobacz też

[Obsługa zmiennoprzecinkowej](../../c-runtime-library/floating-point-support.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>

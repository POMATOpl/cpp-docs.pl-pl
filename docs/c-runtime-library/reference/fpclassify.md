---
description: 'Dowiedz się więcej na temat: fpclassify —'
title: fpclassify
ms.date: 04/05/2018
api_name:
- fpclassify
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
api_type:
- HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: 716684f15e82fb439c16239a61401b892a244f93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164838"
---
# <a name="fpclassify"></a>fpclassify

Zwraca klasyfikację zmiennoprzecinkową argumentu.

## <a name="syntax"></a>Składnia

```C
int fpclassify(
   /* floating-point */ x
);

int fpclassify(
   float x
); // C++ only

int fpclassify(
   double x
); // C++ only

int fpclassify(
   long double x
); // C++ only
```

### <a name="parameters"></a>Parametry

*x*<br/>
Wartość zmiennoprzecinkowa do przetestowania.

## <a name="return-value"></a>Wartość zwracana

**fpclassify —** zwraca liczbę całkowitą wskazującą klasę zmiennoprzecinkową argumentu *x*. W tej tabeli przedstawiono możliwe wartości zwrócone przez **fpclassify —**, zdefiniowane w \<math.h> .

|Wartość|Opis|
|-----------|-----------------|
|**FP_NAN**|Cichy, sygnalizujący lub nieokreślony NaN|
|**FP_INFINITE**|Dodatnia lub ujemna nieskończoność|
|**FP_NORMAL**|Dodatnia lub negatywna znormalizowana wartość różna od zera|
|**FP_SUBNORMAL**|Wartość dodatnia lub ujemna nieznormalizowana|
|**FP_ZERO**|Dodatnia lub ujemna wartość zerowa|

## <a name="remarks"></a>Uwagi

W C, **fpclassify —** to makro; w języku C++ **fpclassify —** jest funkcją przeciążoną przy użyciu typów argumentów **`float`** , **`double`** , lub **`long double`** . W obu przypadkach zwracana wartość zależy od typu obowiązywania wyrażenia argumentu, a nie na żadnej pośredniej reprezentacji. Na przykład normalna **`double`** lub **`long double`** wartość może być wartością nieskończoną, nienormalną lub zerową, gdy jest konwertowany na **`float`** .

## <a name="requirements"></a>Wymagania

|Funkcja/makro|Wymagany nagłówek (C)|Wymagany nagłówek (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> lub \<cmath>|

Makra **fpclassify —** i funkcje **fpclassify —** są zgodne ze specyfikacjami ISO C99 i c++ 11. Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>

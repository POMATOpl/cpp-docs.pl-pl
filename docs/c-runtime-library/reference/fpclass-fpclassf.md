---
title: _fpclass, _fpclassf
ms.date: 04/05/2018
apiname:
- _fpclass
- _fpclassf
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
ms.openlocfilehash: 987c87cc7a03f4a24e47654ae52e8a2416a15184
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590973"
---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf

Zwraca wartość wskazującą klasyfikacji zmiennoprzecinkową argumentu.

## <a name="syntax"></a>Składnia

```C
int _fpclass(
   double x
);

int _fpclassf(
   float x
); /* x64 only */
```

### <a name="parameters"></a>Parametry

*x*<br/>
Wartość zmiennoprzecinkowa do testowania.

## <a name="return-value"></a>Wartość zwracana

**_Fpclass** i **_fpclassf** funkcje zwracają wartość całkowitą, która wskazuje klasyfikacji zmiennoprzecinkową argumentu *x*. Klasyfikacja może mieć jedną z następujących wartości, zdefiniowane w \<float.h >.

|Wartość|Opis|
|-----------|-----------------|
|**_FPCLASS_SNAN**|Sygnalizowanie NaN|
|**_FPCLASS_QNAN**|Ciche NaN|
|**_FPCLASS_NINF**|Nieskończoność ujemna (-INF)|
|**_FPCLASS_NN**|Ujemna znormalizowane różna od zera|
|**_FPCLASS_ND**|Ujemna nieznormalizowane|
|**_FPCLASS_NZ**|Zero ujemna (- 0)|
|**_FPCLASS_PZ**|0 dodatnią (+ 0)|
|**_FPCLASS_PD**|Wynik dodatni nieznormalizowane|
|**_FPCLASS_PN**|Wynik dodatni znormalizowane różna od zera|
|**_FPCLASS_PINF**|Nieskończoności dodatniej (+ INF)|

## <a name="remarks"></a>Uwagi

**_Fpclass** i **_fpclassf** funkcje są specyficzne dla firmy Microsoft. Są one podobne do [fpclassify —](fpclassify.md), ale powróci, bardziej szczegółowe informacje o argumentu. **_Fpclassf** funkcja jest dostępna, gdy kompilowany x64 tylko platformy.

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**_fpclass**, **_fpclassf**|\<float.h>|

Aby uzyskać więcej informacji zgodności i zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz także

[Obsługa liczb zmiennoprzecinkowych](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[fpclassify](fpclassify.md)<br/>
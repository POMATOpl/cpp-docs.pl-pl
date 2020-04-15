---
title: _fpclass, _fpclassf
ms.date: 4/2/2020
api_name:
- _fpclass
- _fpclassf
- _o__fpclass
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
ms.openlocfilehash: b16655fed046114e9dd8592c5e1fd3fc5f7ed4bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346277"
---
# <a name="_fpclass-_fpclassf"></a>_fpclass, _fpclassf

Zwraca wartość wskazującą klasyfikację zmiennoprzecinkową argumentu.

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

*X*<br/>
Wartość zmiennoprzecinkowa do przetestowania.

## <a name="return-value"></a>Wartość zwracana

Funkcje **_fpclass** i **_fpclassf** zwracają wartość całkowitą wskazującą zmiennoprzecinkową klasyfikację argumentu *x*. Klasyfikacja może mieć jedną z następujących \<wartości, zdefiniowaną w> float.h.

|Wartość|Opis|
|-----------|-----------------|
|**_FPCLASS_SNAN**|Sygnalizacja NaN|
|**_FPCLASS_QNAN**|Cichy NaN|
|**_FPCLASS_NINF**|Ujemna nieskończoność ( -INF)|
|**_FPCLASS_NN**|Ujemna znormalizowana wartość niezerowa|
|**_FPCLASS_ND**|Ujemna denormalized|
|**_FPCLASS_NZ**|Ujemne zero ( - 0)|
|**_FPCLASS_PZ**|Dodatnia 0 (+0)|
|**_FPCLASS_PD**|Dodatnia denormalized|
|**_FPCLASS_PN**|Dodatnia znormalizowana niezerowa|
|**_FPCLASS_PINF**|Dodatnia nieskończoność (+INF)|

## <a name="remarks"></a>Uwagi

Funkcje **_fpclass** i **_fpclassf** są specyficzne dla firmy Microsoft. Są one podobne do [fpclassify](fpclassify.md), ale zwracają bardziej szczegółowe informacje na temat argumentu. Funkcja **_fpclassf** jest dostępna tylko po skompilowaniu dla platformy x64.

Domyślnie stan globalny tej funkcji jest ograniczony do aplikacji. Aby to zmienić, zobacz [Stan globalny w crt](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**_fpclass** **, _fpclassf**|\<> float.h|

Aby uzyskać więcej informacji o zgodności i zgodności, zobacz [Zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Obsługa zmiennoprzecinkowej](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[fpclassify](fpclassify.md)<br/>

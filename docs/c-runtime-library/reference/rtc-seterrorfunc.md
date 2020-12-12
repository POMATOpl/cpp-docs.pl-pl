---
description: 'Dowiedz się więcej na temat: _RTC_SetErrorFunc'
title: _RTC_SetErrorFunc
ms.date: 11/04/2016
api_name:
- _RTC_SetErrorFunc
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
- DLLExport
topic_type:
- apiref
f1_keywords:
- RTC_SetErrorFunc
- _RTC_SetErrorFunc
helpviewer_keywords:
- RTC_SetErrorFunc function
- _RTC_SetErrorFunc function
ms.assetid: b2292722-0d83-4092-83df-3d5b19880666
ms.openlocfilehash: 454fd54e0960e8ce52c94b4e4a1e0a93ea99d3eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268941"
---
# <a name="_rtc_seterrorfunc"></a>_RTC_SetErrorFunc

Określa funkcję jako procedurę obsługi dla sprawdzania błędów czasu wykonywania raportowania (RTCs). Ta funkcja jest przestarzała; Zamiast tego użyj **_RTC_SetErrorFuncW** .

## <a name="syntax"></a>Składnia

```C
_RTC_error_fn _RTC_SetErrorFunc(
   _RTC_error_fn function
);
```

### <a name="parameters"></a>Parametry

*funkcyjn*<br/>
Adres funkcji, która będzie obsługiwać sprawdzanie błędów w czasie wykonywania.

## <a name="return-value"></a>Wartość zwracana

Wcześniej zdefiniowana funkcja błędu. Jeśli nie ma wcześniej zdefiniowanej funkcji, zwraca **wartość null**.

## <a name="remarks"></a>Uwagi

Nie należy używać tej funkcji; Zamiast tego należy użyć **_RTC_SetErrorFuncW**. Jest on przechowywany tylko w celu zapewnienia zgodności z poprzednimi wersjami.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_RTC_SetErrorFunc**|\<rtcapi.h>|

Aby uzyskać więcej informacji, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Zobacz też

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Sprawdzanie błędów czasu wykonywania](../../c-runtime-library/run-time-error-checking.md)<br/>

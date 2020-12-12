---
description: 'Dowiedz się więcej na temat: _RTC_GetErrDesc'
title: _RTC_GetErrDesc
ms.date: 11/04/2016
api_name:
- _RTC_GetErrDesc
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
- RTC_GetErrDesc
- _RTC_GetErrDesc
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
ms.openlocfilehash: 5e9beccec5e13d6c2c00e3edaefec695a8e16737
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168725"
---
# <a name="_rtc_geterrdesc"></a>_RTC_GetErrDesc

Zwraca Krótki opis typu sprawdzania błędów czasu wykonywania (RTC).

## <a name="syntax"></a>Składnia

```C
const char * _RTC_GetErrDesc(
   _RTC_ErrorNumber errnum
);
```

### <a name="parameters"></a>Parametry

*errnum*<br/>
Liczba z przedziału od zera do jednej mniejszej niż wartość zwrócona przez **_RTC_NumErrors**.

## <a name="return-value"></a>Wartość zwracana

Ciąg znaków zawierający krótki opis jednego z typów błędów wykrytych przez system sprawdzania błędów czasu wykonywania. Jeśli wartość błędu jest mniejsza od zera lub większa lub równa wartości zwróconej przez [_RTC_NumErrors](rtc-numerrors.md), **_RTC_GetErrDesc** zwraca **wartość null**.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapi.h>|

Aby uzyskać więcej informacji, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Zobacz też

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[Sprawdzanie błędów czasu wykonywania](../../c-runtime-library/run-time-error-checking.md)<br/>

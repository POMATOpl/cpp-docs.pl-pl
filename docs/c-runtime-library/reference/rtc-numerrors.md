---
description: 'Dowiedz się więcej na temat: _RTC_NumErrors'
title: _RTC_NumErrors
ms.date: 11/04/2016
api_name:
- _RTC_NumErrors
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
- _RTC_NumErrors
- RTC_NumErrors
helpviewer_keywords:
- run-time errors
- _RTC_NumErrors function
- RTC_NumErrors function
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
ms.openlocfilehash: df103f5aada8c896669b82abc1b65621597acf1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168712"
---
# <a name="_rtc_numerrors"></a>_RTC_NumErrors

Zwraca łączną liczbę błędów, które mogą zostać wykryte przez sprawdzanie błędów czasu wykonywania (RTC). Tej liczby można użyć jako formantu w **`for`** pętli, gdzie każda wartość w pętli jest przenoszona do [_RTC_GetErrDesc](rtc-geterrdesc.md).

## <a name="syntax"></a>Składnia

```C

int _RTC_NumErrors( void );
```

## <a name="return-value"></a>Wartość zwracana

Liczba całkowita, której wartość reprezentuje całkowitą liczbę błędów, które mogą zostać wykryte przez Visual C++ sprawdzenia błędów czasu wykonywania.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_RTC_NumErrors**|\<rtcapi.h>|

Aby uzyskać więcej informacji, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Zobacz też

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Sprawdzanie błędów czasu wykonywania](../../c-runtime-library/run-time-error-checking.md)<br/>

---
description: 'Dowiedz się więcej na temat: _RTC_SetErrorType'
title: _RTC_SetErrorType
ms.date: 11/04/2016
api_name:
- _RTC_SetErrorType
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
- RTC_SetErrorType
- _RTC_SetErrorType
helpviewer_keywords:
- run-time errors
- RTC_SetErrorType function
- _RTC_SetErrorType function
ms.assetid: f5f99be7-d357-4b11-b8f5-ddd3428f2b06
ms.openlocfilehash: 8b0b28eaf97a27dbfcf4dcb414c9a17f03df7f9e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168699"
---
# <a name="_rtc_seterrortype"></a>_RTC_SetErrorType

Kojarzy błąd, który został wykryty przez sprawdzanie błędów czasu wykonywania (RTCs) z typem. Procedura obsługi błędów przetwarza sposób wyprowadzania błędów określonego typu.

## <a name="syntax"></a>Składnia

```C
int _RTC_SetErrorType(
   _RTC_ErrorNumber errnum,
   int ErrType
);
```

### <a name="parameters"></a>Parametry

*errnum*<br/>
Liczba z przedziału od zera do jednej mniejszej niż wartość zwrócona przez [_RTC_NumErrors](rtc-numerrors.md).

*ErrType*<br/>
Wartość, która ma zostać przypisana do tego *errnum*. Można na przykład użyć **_CRT_ERROR**. Jeśli używasz **_CrtDbgReport** jako programu obsługi błędów, *ErrType* może być tylko jednym z symboli zdefiniowanych w [_CrtSetReportMode](crtsetreportmode.md). Jeśli masz własną procedurę obsługi błędów ([_RTC_SetErrorFunc](rtc-seterrorfunc.md)), możesz mieć dowolną liczbę *ErrType* s, ponieważ *errnum* s.

*ErrType* _RTC_ERRTYPE_IGNORE ma specjalne znaczenie dla **_CrtSetReportMode**; błąd jest ignorowany.

## <a name="return-value"></a>Wartość zwracana

Poprzednia *wartość typu błędu.*

## <a name="remarks"></a>Uwagi

Domyślnie wszystkie błędy są ustawiane na *ErrType* = 1, co odnosi się do **_CRT_ERROR**. Aby uzyskać więcej informacji na temat domyślnych typów błędów, takich jak **_CRT_ERROR**, zobacz [_CrtDbgReport](crtdbgreport-crtdbgreportw.md).

Aby można było wywołać tę funkcję, należy najpierw wywołać jedną z funkcji inicjalizacji sprawdzania błędów czasu wykonywania; Zobacz [używanie Run-Time checks bez biblioteki Run-Time C](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_RTC_SetErrorType**|\<rtcapi.h>|

Aby uzyskać więcej informacji, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Zobacz też

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Sprawdzanie błędów czasu wykonywania](../../c-runtime-library/run-time-error-checking.md)<br/>

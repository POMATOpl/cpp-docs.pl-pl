---
description: 'Dowiedz się więcej na temat: _RTC_SetErrorFuncW'
title: _RTC_SetErrorFuncW
ms.date: 11/04/2016
api_name:
- _RTC_SetErrorFuncW
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
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
ms.openlocfilehash: e1f92b791f986c7881f0c65a22c24432c03160e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341428"
---
# <a name="_rtc_seterrorfuncw"></a>_RTC_SetErrorFuncW

Określa funkcję jako program obsługi raportowania błędów czasu wykonywania (RTCs).

## <a name="syntax"></a>Składnia

```C
_RTC_error_fnW _RTC_SetErrorFuncW(
   _RTC_error_fnW function
);
```

### <a name="parameters"></a>Parametry

*funkcyjn*<br/>
Adres funkcji, która będzie obsługiwać sprawdzanie błędów w czasie wykonywania.

## <a name="return-value"></a>Wartość zwracana

Wcześniej zdefiniowana funkcja błędu; lub **wartość null** , jeśli nie ma wcześniej zdefiniowanej funkcji.

## <a name="remarks"></a>Uwagi

W obszarze nowy kod Użyj tylko **_RTC_SetErrorFuncW**. **_RTC_SetErrorFunc** jest dostępna tylko w bibliotece w celu zapewnienia zgodności z poprzednimi wersjami.

Wywołanie zwrotne **_RTC_SetErrorFuncW** ma zastosowanie tylko do składnika, w którym został on połączony, ale nie globalnie.

Upewnij się, że adres, który został przekazany do **_RTC_SetErrorFuncW** jest prawidłowym funkcją obsługi błędów.

Jeśli do błędu przypisano typ-1 za pomocą [_RTC_SetErrorType](rtc-seterrortype.md), funkcja obsługi błędów nie zostanie wywołana.

Aby można było wywołać tę funkcję, należy najpierw wywołać jedną z funkcji inicjowania sprawdzania błędów w czasie wykonywania. Aby uzyskać więcej informacji, zobacz [Using Run-Time checks bez biblioteki C Run-Time](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library).

**_RTC_error_fnW** definiuje się w następujący sposób:

```cpp
typedef int (__cdecl * _RTC_error_fnW)(
    int errorType,
    const wchar_t * filename,
    int linenumber,
    const wchar_t * moduleName,
    const wchar_t * format,
    ... );
```

gdzie:

*błądtype*<br/>
Typ błędu, który jest określony przez [_RTC_SetErrorType](rtc-seterrortype.md).

*Nazwa pliku*<br/>
Plik źródłowy, w którym wystąpił błąd lub wartość null, jeśli nie ma dostępnych informacji o debugowaniu.

*LineNumber*<br/>
Wiersz w *nazwie pliku* , w którym wystąpił błąd, lub 0, jeśli informacje debugowania nie są dostępne.

*moduleName*<br/>
Nazwa pliku DLL lub pliku wykonywalnego, w którym wystąpił błąd.

*Formatowanie*<br/>
printf ciąg stylu, aby wyświetlić komunikat o błędzie przy użyciu pozostałych parametrów. Pierwszym argumentem VA_ARGLIST jest numer błędu RTC, który wystąpił.

Aby zapoznać się z przykładem, który pokazuje, jak używać **_RTC_error_fnW**, zobacz [Native Run-Time checks](/visualstudio/debugger/native-run-time-checks-customization).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_RTC_SetErrorFuncW**|\<rtcapi.h>|

Aby uzyskać więcej informacji, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Zobacz też

[_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md)<br/>
[Sprawdzanie błędów czasu wykonywania](../../c-runtime-library/run-time-error-checking.md)<br/>

---
description: 'Dowiedz się więcej na temat: _get_daylight'
title: _get_daylight
ms.date: 4/2/2020
api_name:
- __daylight
- _get_daylight
- _o___daylight
- _o__get_daylight
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_daylight
- _get_daylight
helpviewer_keywords:
- get_daylight function
- daylight saving time offset
- _get_daylight function
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
ms.openlocfilehash: dcb4ffb80ea79d89cad84617d4c8e4dceb1735c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341480"
---
# <a name="_get_daylight"></a>_get_daylight

Pobiera przesunięcie czasu letniego w godzinach.

## <a name="syntax"></a>Składnia

```C
error_t _get_daylight( int* hours );
```

### <a name="parameters"></a>Parametry

*liczb*<br/>
Przesunięcie w godzinach czasu letniego.

## <a name="return-value"></a>Wartość zwracana

Zero, jeśli wystąpi błąd lub wartość **errno** w przypadku wystąpienia błędu.

## <a name="remarks"></a>Uwagi

Funkcja **_get_daylight** Pobiera liczbę godzin w czasie letnim w postaci liczby całkowitej. Jeśli obowiązuje czas letni, domyślne przesunięcie wynosi godzinę (chociaż kilka regionów obserwuje przesunięcie dwugodzinne).

Jeśli *godziny* mają **wartość null**, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, ta funkcja ustawia **errno** na **EINVAL** i zwraca **EINVAL**.

Zalecamy używanie tej funkcji zamiast makra **_daylight** lub przestarzałej funkcji **__daylight**.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_get_daylight**|\<time.h>|

Aby uzyskać więcej informacji, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Zarządzanie czasem](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>

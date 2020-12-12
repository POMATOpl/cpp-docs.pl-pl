---
description: 'Dowiedz się więcej na temat: _get_dstbias'
title: _get_dstbias
ms.date: 4/2/2020
api_name:
- _get_dstbias
- __dstbias
- _o___dstbias
- _o__get_dstbias
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
- __dstbias
- _get_dstbias
- get_dstbias
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
ms.openlocfilehash: 00c5cef0e7c1e5e79cbcc2ce37a13e3f56d27029
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341454"
---
# <a name="_get_dstbias"></a>_get_dstbias

Pobiera przesunięcie czasu letniego w sekundach.

## <a name="syntax"></a>Składnia

```C
error_t _get_dstbias( int* seconds );
```

### <a name="parameters"></a>Parametry

*s*<br/>
Przesunięcie (w sekundach) czasu letniego.

## <a name="return-value"></a>Wartość zwracana

Zero, jeśli wystąpi błąd lub wartość **errno** w przypadku wystąpienia błędu.

## <a name="remarks"></a>Uwagi

Funkcja **_get_dstbias** Pobiera liczbę sekund w czasie zmiany czasu w postaci liczby całkowitej. Jeśli obowiązuje czas letni, domyślne przesunięcie wynosi 3600 sekund, czyli liczbę sekund w ciągu godziny (chociaż kilka regionów obserwuje przesunięcia dwugodzinne).

Jeśli *sekundy* ma **wartość null**, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, ta funkcja ustawia **errno** na **EINVAL** i zwraca **EINVAL**.

Zalecamy używanie tej funkcji zamiast makra **_dstbias** lub przestarzałej funkcji **__dstbias**.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_get_dstbias**|\<time.h>|

Aby uzyskać więcej informacji, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Zarządzanie czasem](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>

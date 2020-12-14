---
description: 'Dowiedz się więcej na temat: _daylight, _dstbias, _timezone i _tzname'
title: _daylight, _dstbias, _timezone, i _tzname
ms.date: 11/04/2016
f1_keywords:
- tzname
- _timezone
- timezone
- _daylight
- _tzname
- daylight
helpviewer_keywords:
- time zones
- time adjustments
- timezone variables
- _tzname function
- _daylight function
- _timezone function
- daylight function
- local time adjustments
- timezone function
- tzname function
- time-zone variables
ms.assetid: d06c7292-6b99-4aba-b284-16a96570c856
ms.openlocfilehash: aaa1d76276e4b4117d5f07695875481215c4122e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258787"
---
# <a name="_daylight-_dstbias-_timezone-and-_tzname"></a>_daylight, _dstbias, _timezone, i _tzname

`_daylight`, `_dstbias` , `_timezone` i `_tzname` są używane w niektórych procedurach czasu i dat, aby wprowadzić korekty w czasie lokalnym. Te zmienne globalne są przestarzałe dla bezpieczniejszych wersji funkcjonalnych, które powinny być używane zamiast zmiennych globalnych.

|Zmienna globalna|Odpowiednik funkcjonalny|
|---------------------|---------------------------|
|`_daylight`|[_get_daylight](../c-runtime-library/reference/get-daylight.md)|
|`_dstbias`|[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)|
|`_timezone`|[_get_timezone](../c-runtime-library/reference/get-timezone.md)|
|`_tzname`|[_get_tzname](../c-runtime-library/reference/get-tzname.md)|

Są one deklarowane w czasie. h w następujący sposób.

## <a name="syntax"></a>Składnia

```
extern int _daylight;
extern int _dstbias;
extern long _timezone;
extern char *_tzname[2];
```

## <a name="remarks"></a>Uwagi

W wywołaniu metody, `_ftime` `localtime` , lub `_tzset` , wartości `_daylight` ,, `_dstbias` `_timezone` i `_tzname` są określane na podstawie wartości `TZ` zmiennej środowiskowej. Jeśli nie ustawisz jawnie wartości `TZ` `_tzname[0]` i `_tzname[1]` Ustawienia domyślne ustawień "PST" i "PDT".  Funkcje manipulowania czasami ([_tzset](../c-runtime-library/reference/tzset.md), [_ftime](../c-runtime-library/reference/ftime-ftime32-ftime64.md)i [localtime](../c-runtime-library/reference/localtime-localtime32-localtime64.md)) podejmują próbę ustawienia wartości `_daylight` `_dstbias` i `_timezone` przez zapytanie do systemu operacyjnego o wartość domyślną każdej zmiennej. W poniższej tabeli przedstawiono wartości zmiennej globalnej strefy czasowej.

|Zmienna|Wartość|
|--------------|-----------|
|`_daylight`|Wartość różna od zera, jeśli strefa czasu letniego jest określona w `TZ` systemie lub określona przez system operacyjny; w przeciwnym razie 0. Wartość domyślna to 1.|
|`_dstbias`|Przesunięcie czasu letniego.|
|`_timezone`|Różnica w sekundach między uniwersalnym czasem koordynowanym i czasem lokalnym. Wartość domyślna to 28 800.|
|`_tzname[0]`|Nazwa strefy czasowej pochodnej od `TZ` zmiennej środowiskowej. Wartość domyślna to "PST".|
|`_tzname[1]`|Nazwa strefy DST pochodzącej ze `TZ` zmiennej środowiskowej. Wartość domyślna to "PDT" (czas pacyficzny).|

## <a name="see-also"></a>Zobacz też

[Zmienne globalne](../c-runtime-library/global-variables.md)<br/>
[_get_daylight](../c-runtime-library/reference/get-daylight.md)<br/>
[_get_dstbias](../c-runtime-library/reference/get-dstbias.md)<br/>
[_get_timezone](../c-runtime-library/reference/get-timezone.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)

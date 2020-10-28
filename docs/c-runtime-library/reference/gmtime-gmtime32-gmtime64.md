---
title: gmtime, _gmtime32, _gmtime64
description: Dokumentacja interfejsu API dla `gmtime` , `_gmtime32` i `_gmtime64` , która konwertuje `time_t` wartość na `tm` strukturę.
ms.date: 10/27/2020
api_name:
- _gmtime32
- gmtime
- _gmtime64
- _o__gmtime32
- _o__gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
ms.openlocfilehash: bb8bee6b752f64d85dfb0f8c9e5ba7acf204a76f
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907548"
---
# <a name="gmtime-_gmtime32-_gmtime64"></a>`gmtime`, `_gmtime32`, `_gmtime64`

Konwertuje `time_t` wartość czasu na `tm` strukturę. Bardziej bezpieczne wersje tych funkcji są dostępne; Zobacz [ `gmtime_s` , `_gmtime32_s` , `_gmtime64_s` ](gmtime-s-gmtime32-s-gmtime64-s.md).

## <a name="syntax"></a>Składnia

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>Parametry

*`sourceTime`*\
Wskaźnik na czas przechowywania. Czas jest reprezentowany jako sekund, które upłynęły od północy (00:00:00), 1 stycznia 1970, uniwersalny czas koordynowany (UTC).

## <a name="return-value"></a>Wartość zwracana

Wskaźnik do struktury typu [`tm`](../../c-runtime-library/standard-types.md) . Pola w zwracanej strukturze przechowują obliczoną wartość *`sourceTime`* argumentu w formacie UTC, a nie w czasie lokalnym. Każde z pól struktury jest typu `int` , w następujący sposób:

|Pole|Opis|
|-|-|
|`tm_sec`|Sekund po minucie (0-59).|
|`tm_min`|Minut po godzinie (0-59).|
|`tm_hour`|Godz. od północy (0-23).|
|`tm_mday`|Dzień miesiąca (1-31).|
|`tm_mon`|Miesiąc (0-11; Styczeń = 0).|
|`tm_year`|Year (bieżący rok minus 1900).|
|`tm_wday`|Dzień tygodnia (0-6; Niedziela = 0).|
|`tm_yday`|Dzień roku (0-365; 1 stycznia = 0).|
|`tm_isdst`|Zawsze 0 dla **gmtime** .|

Zarówno 32-bitowe, jak i 64-bitowe wersje **`gmtime`** , [`mktime`](mktime-mktime32-mktime64.md) , [`mkgmtime`](mkgmtime-mkgmtime32-mkgmtime64.md) , i [`localtime`](localtime-localtime32-localtime64.md) wszystkie używają jednej wspólnej `tm` struktury na wątek dla konwersji. Każde wywołanie jednej z tych funkcji niszczy wynik poprzedniego wywołania. Jeśli *`sourceTime`* reprezentuje datę przed północy, 1 stycznia 1970, **`gmtime`** zwraca `NULL` . Nie ma żadnego powrotu błędu.

**_gmtime64** , która korzysta ze `__time64_t` struktury, umożliwia wyrażanie dat do 23:59:59 grudnia, 3000, UTC. **`_gmtime32`** reprezentuje tylko daty do 23:59:59 stycznia 18, 2038, UTC. Północ, 1 stycznia 1970, to Dolna granica zakresu dat dla obu funkcji.

**`gmtime`** jest wbudowaną funkcją **`_gmtime64`** , która `time_t` jest równoważna z, i jest równoznaczna z, `__time64_t` chyba że `_USE_32BIT_TIME_T` jest zdefiniowany. Jeśli trzeba wymusić, aby kompilator mógł interpretować `time_t` jako stary 32-bitowy `time_t` , można zdefiniować `_USE_32BIT_TIME_T` , ale to spowoduje, że **`gmtime`** będą one w wierszu **`_gmtime32`** i `time_t` zdefiniowane jako `__time32_t` . Nie zalecamy tego, ponieważ nie jest to dozwolone na platformach 64-bitowych. W każdym przypadku aplikacja może zakończyć się niepowodzeniem po 18 stycznia 2038.

Te funkcje sprawdzają poprawność swoich parametrów. Jeśli *`sourceTime`* jest wskaźnikiem typu null lub jeśli *`sourceTime`* wartość jest ujemna, te funkcje wywołują procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, funkcje zwracają `NULL` i ustawiają `errno` na `EINVAL` .

## <a name="remarks"></a>Uwagi

**`_gmtime32`** Funkcja przerywa *`sourceTime`* wartość i zapisuje ją w statycznie przydzieloną strukturę typu `tm` , zdefiniowane w `TIME.H` . Wartość *`sourceTime`* jest zazwyczaj uzyskiwana z wywołania [`time`](time-time32-time64.md) funkcji.

> [!NOTE]
> W większości przypadków środowisko docelowe próbuje określić, czy obowiązuje czas letni. Biblioteka środowiska uruchomieniowego C zakłada, że używane są reguły Stany Zjednoczone do implementowania obliczeń czasu letniego (DST).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek C|Wymagany nagłówek C++|
|-------------|---------------------|-|
|**`gmtime`** , **`_gmtime32`** , **`_gmtime64`**|`<time.h>`| `<ctime>` lub `<time.h>`|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_gmtime.c
// compile with: /W3
// This program uses _gmtime64 to convert a long-
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main(void)
{
   struct tm *newtime;
   __int64 ltime;
   char buff[80];

   _time64( &ltime );

   // Obtain coordinated universal time:
   newtime = _gmtime64( &ltime ); // C4996
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s
   asctime_s( buff, sizeof(buff), newtime );
   printf( "Coordinated universal time is %s\n", buff );
}
```

```Output
Coordinated universal time is Tue Feb 12 23:11:31 2002
```

## <a name="see-also"></a>Zobacz także

[Zarządzanie czasem](../../c-runtime-library/time-management.md)\
[`asctime`, `_wasctime`](asctime-wasctime.md)\
[`ctime`, `_ctime32`, `_ctime64`, `_wctime`, `_wctime32`, `_wctime64`](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)\
[`_ftime`, `_ftime32`, `_ftime64`](ftime-ftime32-ftime64.md)\
[`gmtime_s`, `_gmtime32_s`, `_gmtime64_s`](gmtime-s-gmtime32-s-gmtime64-s.md)\
[`localtime`, `_localtime32`, `_localtime64`](localtime-localtime32-localtime64.md)\
[`_mkgmtime`, `_mkgmtime32`, `_mkgmtime64`](mkgmtime-mkgmtime32-mkgmtime64.md)\
[`mktime`, `_mktime32`, `_mktime64`](mktime-mktime32-mktime64.md)\
[`time`, `_time32`, `_time64`](time-time32-time64.md)

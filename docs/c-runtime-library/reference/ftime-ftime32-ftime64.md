---
title: _ftime, _ftime32, _ftime64
ms.date: 4/2/2020
api_name:
- _ftime64
- _ftime
- _ftime32
- _o__ftime32
- _o__ftime64
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ftime32
- _ftime
- _ftime64
- ftime64
- ftime
- ftime32
helpviewer_keywords:
- ftime64 function
- _ftime64 function
- current time
- _ftime function
- ftime function
- _ftime32 function
- ftime32 function
- time, getting current
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
ms.openlocfilehash: 4e06eec975f02744c4b49c1980383c2ab2338ddc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345583"
---
# <a name="_ftime-_ftime32-_ftime64"></a>_ftime, _ftime32, _ftime64

Uzyskaj bieżący czas. Dostępne są bezpieczniejsze wersje tych funkcji; zobacz [_ftime_s, _ftime32_s, _ftime64_s](ftime-s-ftime32-s-ftime64-s.md).

## <a name="syntax"></a>Składnia

```C
void _ftime( struct _timeb *timeptr );
void _ftime32( struct __timeb32 *timeptr );
void _ftime64( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>Parametry

*timeptr*<br/>
Wskaźnik do **_timeb,** **__timeb32**lub **__timeb64** struktury.

## <a name="remarks"></a>Uwagi

Funkcja **_ftime** pobiera bieżący czas lokalny i przechowuje go w strukturze wskazanej przez *timeptr*. Struktury **_timeb** **, __timeb32**i **__timeb64** są zdefiniowane w \<> sys\\timeb.h. Zawierają one cztery pola, które są wymienione w poniższej tabeli.

|Pole|Opis|
|-|-|
|**żużel**|Niezerowe, jeśli czas letni jest obecnie w mocy dla lokalnej strefy czasowej. (Zobacz [_tzset,](tzset.md) aby uzyskać wyjaśnienie, w jaki sposób określa się czas letni).|
|**miliitm**|Ułamek sekundy w milisekundach.|
|**Czas**|Czas w sekundach od północy (00:00:00), 1 stycznia 1970, czas uniwersalny (UTC).|
|**Strefa czasowa**|Różnica w minutach, przesuwając się na zachód, między CZASEM UTC a czasem lokalnym. Wartość **strefy czasowej** jest ustawiana na podstawie wartości **zmiennej** globalnej _timezone (patrz **_tzset**).|

Funkcja **_ftime64,** która używa **__timeb64** struktury, umożliwia wyrażenie dat tworzenia plików do godziny 23:59:59, 31 grudnia 3000, UTC; mając na **uwadze, że _ftime32** reprezentuje tylko daty do 23:59:59 18 stycznia 2038, UTC. Północ, 1 stycznia 1970 r., jest dolną granicą zakresu dat dla wszystkich tych funkcji.

Funkcja **_ftime** jest odpowiednikiem **_ftime64**i **_timeb** zawiera czas 64-bitowy, chyba że zdefiniowano **_USE_32BIT_TIME_T,** w którym to przypadku obowiązuje stare zachowanie; **_ftime** używa czasu 32-bitowego, a **_timeb** zawiera czas 32-bitowy.

**_ftime** sprawdza poprawność jego parametrów. Jeśli przeszedł wskaźnik null jako *timepter*, funkcja wywołuje nieprawidłowy program obsługi parametrów, zgodnie z opisem w [sprawdzanie poprawności parametrów](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie jest dozwolone, funkcja ustawia **errno** na **EINVAL**.

Domyślnie stan globalny tej funkcji jest ograniczony do aplikacji. Aby to zmienić, zobacz [Stan globalny w crt](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**_ftime**|\<sys/types.h> i \<sys/timeb.h>|
|**_ftime32**|\<sys/types.h> i \<sys/timeb.h>|
|**_ftime64**|\<sys/types.h> i \<sys/timeb.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [Zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_ftime.c
// compile with: /W3
// This program uses _ftime to obtain the current
// time and then stores this time in timebuffer.

#include <stdio.h>
#include <sys/timeb.h>
#include <time.h>

int main( void )
{
   struct _timeb timebuffer;
   char timeline[26];
   errno_t err;
   time_t time1;
   unsigned short millitm1;
   short timezone1;
   short dstflag1;

   _ftime( &timebuffer ); // C4996
   // Note: _ftime is deprecated; consider using _ftime_s instead

   time1 = timebuffer.time;
   millitm1 = timebuffer.millitm;
   timezone1 = timebuffer.timezone;
   dstflag1 = timebuffer.dstflag;

   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",
   time1);
   printf( "Milliseconds: %d\n", millitm1);
   printf( "Minutes between UTC and local time: %d\n", timezone1);
   printf( "Daylight savings time flag (1 means Daylight time is in "
           "effect): %d\n", dstflag1);

   err = ctime_s( timeline, 26, & ( timebuffer.time ) );
   if (err)
   {
       printf("Invalid argument to ctime_s. ");
   }
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,
           &timeline[20] );
}
```

```Output
Seconds since midnight, January 1, 1970 (UTC): 1051553334
Milliseconds: 230
Minutes between UTC and local time: 480
Daylight savings time flag (1 means Daylight time is in effect): 1
The time is Mon Apr 28 11:08:54.230 2003
```

## <a name="see-also"></a>Zobacz też

[Zarządzanie czasem](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>

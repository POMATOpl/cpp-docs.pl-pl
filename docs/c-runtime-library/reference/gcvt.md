---
description: 'Dowiedz się więcej na temat: _gcvt'
title: _gcvt
ms.date: 4/2/2020
api_name:
- _gcvt
- _o__gcvt
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _gcvt
helpviewer_keywords:
- _gcvt function
- _CVTBUFSIZE
- gcvt function
- floating-point functions, converting number to string
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
ms.openlocfilehash: 942f233e3b0e4c1ac3bc96d1fa64fd46cdccbcc2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341506"
---
# <a name="_gcvt"></a>_gcvt

Konwertuje wartość zmiennoprzecinkową na ciąg, który jest przechowywany w buforze. Dostępna jest bezpieczniejsza wersja tej funkcji; Zobacz [_gcvt_s](gcvt-s.md).

## <a name="syntax"></a>Składnia

```C
char *_gcvt(
   double value,
   int digits,
   char *buffer
);
```

### <a name="parameters"></a>Parametry

*wartość*<br/>
Wartość do przekonwertowania.

*cyfry*<br/>
Liczba przechowywanych cyfr znaczących.

*buforu*<br/>
Lokalizacja przechowywania dla wyniku.

## <a name="return-value"></a>Wartość zwracana

**_gcvt** zwraca wskaźnik do ciągu cyfr.

## <a name="remarks"></a>Uwagi

Funkcja **_gcvt** konwertuje *wartość* zmiennoprzecinkową na ciąg znaków (który zawiera separator dziesiętny i możliwy bajt znaku) i przechowuje ciąg w *buforze*. *Bufor* powinien być wystarczająco duży, aby pomieścić przekonwertowaną wartość oraz kończący znak null, który jest dołączany automatycznie. Jeśli jest używany rozmiar bufora *cyfr* + 1, funkcja zastępuje koniec buforu. Wynika to z faktu, że przekonwertowany ciąg zawiera punkt dziesiętny i może zawierać informacje dotyczące podpisywania i wykładnika. Brak obsługi dla przepełnienia. **_gcvt** próbuje utworzyć *cyfry cyfr w* formacie dziesiętnym. Jeśli nie *, generuje cyfry cyfr w* formacie wykładniczym. Końcowe zera mogą być pomijane w konwersji.

*Bufor* o długości **_CVTBUFSIZE** jest wystarczający dla każdej wartości zmiennoprzecinkowej.

Ta funkcja sprawdza poprawność swoich parametrów. Jeśli *bufor* ma **wartość null**, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, ta funkcja ustawia **errno** na **EINVAL** i zwraca **wartość null**.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_gcvt**|\<stdlib.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_gcvt.c
// compile with: /W3
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

int main( void )
{
   char buffer[_CVTBUFSIZE];
   double value = -1234567890.123;
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );
   _gcvt( value, 12, buffer ); // C4996
   // Note: _gcvt is deprecated; consider using _gcvt_s instead
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value *= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );

   printf( "\n" );
   value = -12.34567890123;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
   value /= 10;
   _gcvt( value, 12, buffer ); // C4996
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );
}
```

```Output
The following numbers were converted by _gcvt(value,12,buffer):
buffer: '-1234567890.12' (14 chars)
buffer: '-12345678901.2' (14 chars)
buffer: '-123456789012' (13 chars)
buffer: '-1.23456789012e+012' (19 chars)

buffer: '-12.3456789012' (14 chars)
buffer: '-1.23456789012' (14 chars)
buffer: '-0.123456789012' (15 chars)
buffer: '-1.23456789012e-002' (19 chars)
```

## <a name="see-also"></a>Zobacz także

[Konwersja danych](../../c-runtime-library/data-conversion.md)<br/>
[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>

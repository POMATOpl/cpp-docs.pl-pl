---
description: 'Dowiedz się więcej na temat: atol, _atol_l, _wtol, _wtol_l'
title: atol, _atol_l, _wtol, _wtol_l
ms.date: 4/2/2020
api_name:
- atol
- _wtol_l
- _wtol
- _atol_l
- _o__atol_l
- _o__wtol
- _o__wtol_l
- _o_atol
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
- _atol_l
- _ttol_l
- _tstol_l
- _tstol
- _wtol
- _ttol
- _wtol_l
helpviewer_keywords:
- tstol function
- atol function
- ttol function
- _atol_l function
- _tstol_l function
- string conversion, to integers
- _tstol function
- _ttol function
- _ttol_l function
- atol_l function
- wtol_l function
- _wtol_l function
- wtol function
- _wtol function
ms.assetid: cedfc21c-2d64-4e9c-bd04-bdf60b12db46
ms.openlocfilehash: 99830a76d3392af71cf3f55992a4207dc3b6ce18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303690"
---
# <a name="atol-_atol_l-_wtol-_wtol_l"></a>atol, _atol_l, _wtol, _wtol_l

Konwertuj ciąg na długą liczbę całkowitą.

## <a name="syntax"></a>Składnia

```C
long atol(
   const char *str
);
long _atol_l(
   const char *str,
   _locale_t locale
);
long _wtol(
   const wchar_t *str
);
long _wtol_l(
   const wchar_t *str,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametry

*str*<br/>
Ciąg do przekonwertowania.

*locale*<br/>
Ustawienia regionalne do użycia.

## <a name="return-value"></a>Wartość zwracana

Każda funkcja zwraca **`long`** wartość wygenerowaną przez interpretowanie znaków wejściowych jako liczby. Wartość zwracana jest 0L dla **Atol** , jeśli nie można przekonwertować danych wejściowych na wartość tego typu.

W przypadku przepełnienia z dużymi dodatnimi wartościami całkowitymi funkcja **Atol** zwraca **LONG_MAX**; w przypadku przepełnienia z dużymi ujemnymi wartościami całkowitymi **LONG_MIN** jest zwracana. We wszystkich przypadkach poza zakresem **errno** jest ustawiony na **ERANGE**. Jeśli przekazanie parametru ma **wartość null**, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, te funkcje ustawiają **errno** na **EINVAL** i zwracają 0.

## <a name="remarks"></a>Uwagi

Te funkcje konwertują ciąg znaków na wartość Long Integer (**Atol**).

Ciąg wejściowy jest sekwencją znaków, które mogą być interpretowane jako wartość liczbowa określonego typu. Funkcja przestaje odczytywać ciąg wejściowy przy pierwszym znaku, którego nie może rozpoznać jako część liczby. Ten znak może być znakiem null (' \ 0 ' lub L ' \ 0 '), który kończy ciąg.

Argument *str* **Atol** ma następującą postać:

> [*odstęp*] [*Sign*] [*cyfry*]]

*Odstęp* składa się ze znaków spacji lub tabulatora, które są ignorowane; *znak* jest znakiem plus (+) lub minus (-); i *cyfry* to jedna lub więcej cyfr.

**_wtol** jest taka sama jak **Atol** , z tą różnicą, że pobiera ciąg znaków dwubajtowych.

Wersje tych funkcji z sufiksem **_l** są identyczne, z tą różnicą, że korzystają z przekazaną parametrem ustawień regionalnych zamiast bieżących ustawień regionalnych. Aby uzyskać więcej informacji, zobacz [Ustawienia regionalne](../../c-runtime-library/locale.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura TCHAR.H|Nie zdefiniowano _MBCS _UNICODE &|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstol**|**atol**|**atol**|**_wtol**|
|**_ttol**|**atol**|**atol**|**_wtol**|

## <a name="requirements"></a>Wymagania

|Procedury|Wymagany nagłówek|
|--------------|---------------------|
|**atol**|\<stdlib.h>|
|**_atol_l**, **_wtol**, **_wtol_l**|\<stdlib.h> i \<wchar.h>|

## <a name="example"></a>Przykład

Ten program pokazuje, jak liczby przechowywane jako ciągi mogą być konwertowane na wartości liczbowe przy użyciu funkcji **Atol** .

```C
// crt_atol.c
// This program shows how numbers stored as
// strings can be converted to numeric values
// using the atol functions.
#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
    char    *str = NULL;
    long    value = 0;

    // An example of the atol function
    // with leading and trailing white spaces.
    str = "  -2309 ";
    value = atol( str );
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );

    // Another example of the atol function
    // with an arbitrary decimal point.
    str = "314127.64";
    value = atol( str );
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );

    // Another example of the atol function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = atol( str );
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: atol( "  -2309 " ) = -2309
Function: atol( "314127.64" ) = 314127
Function: atol( "3336402735171707160320" ) = 2147483647
Overflow condition occurred.
```

## <a name="see-also"></a>Zobacz też

[Konwersja danych](../../c-runtime-library/data-conversion.md)<br/>
[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[Ustawienie](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>

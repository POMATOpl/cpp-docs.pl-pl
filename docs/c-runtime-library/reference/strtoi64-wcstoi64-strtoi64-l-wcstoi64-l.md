---
description: 'Dowiedz się więcej na temat: _strtoi64, _wcstoi64, _strtoi64_l _wcstoi64_l'
title: _strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l
ms.date: 4/2/2020
api_name:
- _strtoi64
- _strtoi64_l
- _wcstoi64_l
- _wcstoi64
- _o__strtoi64
- _o__strtoi64_l
- _o__wcstoi64
- _o__wcstoi64_l
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
- _strtoi64
- strtoi64
- _stroi64_l
- _wcstoi64_l
- wcstoi64_l
- _wcstoi64
- wcstoi64
- strtoi64_l
helpviewer_keywords:
- _strtoi64 function
- _wcstoi64 function
- _strtoi64_l function
- string conversion, to integers
- _wcstoi64_l function
- strtoi64_l function
- wcstoi64 function
- strtoi64 function
- wcstoi64_l function
ms.assetid: ea2abc50-7bfe-420e-a46b-703c3153593a
ms.openlocfilehash: 5aaf65f3b1c15d24c9a858ff366cc2d53eab481a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288766"
---
# <a name="_strtoi64-_wcstoi64-_strtoi64_l-_wcstoi64_l"></a>_strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l

Konwertuj ciąg na **`__int64`** wartość.

## <a name="syntax"></a>Składnia

```C
__int64 _strtoi64(
   const char *strSource,
   char **endptr,
   int base
);
__int64 _wcstoi64(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
__int64 _strtoi64_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
__int64 _wcstoi64_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametry

*strSource*<br/>
Ciąg zakończony znakiem null do przekonwertowania.

*endptr*<br/>
Wskaźnik do znaku, który powoduje zatrzymanie skanowania.

*base*<br/>
Numer bazowy do użycia.

*locale*<br/>
Ustawienia regionalne do użycia.

## <a name="return-value"></a>Wartość zwracana

**_strtoi64** zwraca wartość reprezentowaną w ciągu *strSource*, z wyjątkiem sytuacji, gdy reprezentacja spowodowałoby przepełnienie, w takim przypadku zwraca **_I64_MAX** lub **_I64_MIN**. Funkcja zwróci wartość 0, jeśli nie można wykonać konwersji. **_wcstoi64** zwraca wartości analogicznie do **strtoi64**.

**_I64_MAX** i **_I64_MIN** są zdefiniowane w limitach. H.

Jeśli *strSource* ma **wartość null** lub *podstawa* jest różna od zera i jest mniejsza niż 2 lub większa niż 36, **errno** jest ustawiona na **EINVAL**.

Aby uzyskać więcej informacji na temat tych i innych kodów powrotu, zobacz [_doserrno, errno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Uwagi

Funkcja **_strtoi64** konwertuje *strSource* na **`__int64`** . Obie funkcje przerywają odczytywanie ciągu *strSource* na pierwszym znaku, którego nie mogą rozpoznać jako części liczby. Może to być kończący znak null lub może być pierwszym znakiem numerycznym większym lub równym *Base*. **_wcstoi64** to dwubajtowa wersja **_strtoi64**; jego argument *strSource* jest ciągiem znaków dwubajtowych. Funkcje te zachowują się identycznie w inny sposób.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura TCHAR.H|Nie zdefiniowano _MBCS _UNICODE &|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoi64**|**_strtoi64**|**_strtoi64**|**_wcstoi64**|
|**_tcstoi64_l**|**_strtoi64_l**|**_strtoi64_l**|**_wcstoi64_l**|

Ustawienie kategorii **LC_NUMERIC** ustawień regionalnych określa rozpoznawanie znaku podstawy w *strSource*; Aby uzyskać więcej informacji, zobacz [setlocale](setlocale-wsetlocale.md). Funkcje bez sufiksu _l używają bieżących ustawień regionalnych; **_strtoi64_l** i **_wcstoi64_l** są identyczne z odpowiadającą jej funkcją bez sufiksu **_l** , z tą różnicą, że w zamian korzystają z przekazaną ustawieniami regionalnymi. Aby uzyskać więcej informacji, zobacz [Ustawienia regionalne](../../c-runtime-library/locale.md).

Jeśli *endptr* nie ma **wartości null**, wskaźnik do znaku, który zatrzymał skanowanie jest przechowywany w lokalizacji wskazywanej przez *endptr*. Jeśli konwersja nie może być wykonywana (nie znaleziono prawidłowych cyfr lub określono nieprawidłową podstawę), wartość *strSource* jest przechowywana w lokalizacji wskazywanej przez *endptr*.

**_strtoi64** oczekuje, że *strSource* wskaże ciąg o następującej postaci:

> [*odstęp*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*cyfry*  &#124; *litery*]

*Odstępy* mogą składać się ze znaków spacji i tabulatora, które są ignorowane; *cyfry* są jedną lub większą liczbą cyfr dziesiętnych; *litery* są jedną lub większą literą od "a" do "z" (lub od "a" do "z").  Pierwszy znak, który nie pasuje do tego formularza, zatrzyma skanowanie. Jeśli *baza* jest z przedziału od 2 do 36, zostanie użyta jako podstawa liczby. Jeśli *Base* ma wartość 0, początkowe znaki ciągu wskazywane przez *strSource* są używane do określenia podstawy. Jeśli pierwszym znakiem jest 0, a drugi znak nie jest "x" lub "X", ciąg jest interpretowany jako ósemkowa liczba całkowita. Jeśli pierwszy znak to "0", a drugi znak to "x" lub "X", ciąg jest interpretowany jako Szesnastkowa liczba całkowita. Jeśli pierwszym znakiem jest "1" do "9", ciąg jest interpretowany jako dziesiętna liczba całkowita. Litery od "a" do "z" (lub "A" do "z") mają przypisane wartości od 10 do 35; dozwolone są tylko litery, których przypisane wartości są mniejsze niż *podstawowe* . Pierwszy znak poza zakresem podstawy powoduje zatrzymanie skanowania. Na przykład jeśli *Base* ma wartość 0, a pierwszy znak skanowany to "0", zakłada się liczbę całkowitą, a znak "8" lub "9" spowoduje zatrzymanie skanowania.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_strtoi64**, **_strtoi64_l**|\<stdlib.h>|
|**_wcstoi64**, **_wcstoi64_l**|\<stdlib.h> lub \<wchar.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Konwersja danych](../../c-runtime-library/data-conversion.md)<br/>
[Ustawienie](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Funkcje ciągu do wartości numerycznych](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>

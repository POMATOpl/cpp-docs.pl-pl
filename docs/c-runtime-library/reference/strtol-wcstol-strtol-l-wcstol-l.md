---
description: Dowiedz się więcej strtol na temat:, wcstol , _strtol_l , _wcstol_l
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 4/2/2020
api_name:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- _o__strtol_l
- _o__wcstol_l
- _o_strtol
- _o_wcstol
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
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
no-loc:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- LONG_MAX
- LONG_MIN
- errno
- ERANGE
- EINVAL
- LC_NUMERIC
- _tcstol
- _tcstol_l
- localeconv
- setlocale
- _wsetlocale
- strtod
- _strtod_l
- wcstod
- _wcstod_l
- strtoll
- _strtoll_l
- wcstoll
- _wcstoll_l
- strtoul
- _strtoul_l
- wcstoul
- _wcstoul_l
- atof
- _atof_l
- _wtof
- _wtof_l
ms.openlocfilehash: 8dd175929335533f8ade91450608db7f39bc0cc3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288675"
---
# <a name="no-locstrtol-no-locwcstol-no-loc_strtol_l-no-loc_wcstol_l"></a>strtol, wcstol, _strtol_l, _wcstol_l

Konwertuje ciągi na **`long`** wartość całkowitą.

## <a name="syntax"></a>Składnia

```C
long strtol(
   const char *string,
   char **end_ptr,
   int base
);
long wcstol(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base
);
long _strtol_l(
   const char *string,
   char **end_ptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametry

*parametry*\
Ciąg zakończony znakiem null do przekonwertowania.

*end_ptr*\
Parametr wyjściowy, ustawiony na wartość wskaż znak po ostatnim interpretowanym znaku. Ignorowany, jeśli **wartość jest równa null**.

*opiera*\
Numer bazowy do użycia.

*ustawienie*\
Ustawienia regionalne do użycia.

## <a name="return-value"></a>Wartość zwracana

**strtol**, **wcstol** , **_strtol_l** i **_wcstol_l** zwracają wartość reprezentowaną w *ciągu*. Zwraca wartość 0, jeśli konwersja nie jest możliwa. Gdy reprezentacja spowoduje przepełnienie, zwracają **LONG_MAX** lub **LONG_MIN** .

**errno** jest ustawiona na wartość **ERANGE** , jeśli występuje przepełnienie lub nadmiar. Jest ustawiona na **EINVAL** Jeśli *ciąg* ma **wartość null**. Lub, jeśli wartość *podstawowa* jest różna od zera i mniejsza niż 2 lub większa niż 36. Aby uzyskać więcej informacji na temat **ERANGE** , **EINVAL** i innych kodów powrotnych, zobacz [_dos errno , errno , _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Uwagi

**strtol** Funkcje, **wcstol** , **_strtol_l** i **_wcstol_l** konwertują *ciąg* na **`long`** . Nie mogą oni przetrzymywać odczytywania *ciągu* przy pierwszym znaku, który nie jest rozpoznawany jako część liczby. Może to być znak kończący o wartości null lub pierwszy znak alfanumeryczny większy lub równy *Base*.

**wcstol** i **_wcstol_l** są wersjami znaków dwubajtowych **strtol** i **_strtol_l** . *Ciąg* znaków dwubajtowych jest ciągiem szerokim. Funkcje te zachowują się identycznie z **strtol** i **_strtol_l** w inny sposób. **LC_NUMERIC** Ustawienie kategorii ustawień regionalnych określa rozpoznawanie znaku podstawy (znacznik Ułamkowy lub dziesiętny) w *ciągu*. Funkcje **strtol** i **wcstol** używają bieżących ustawień regionalnych. **_strtol_l** i **_wcstol_l** zamiast tego użyj przekazaną wartość ustawienia regionalne. Aby uzyskać więcej informacji, zobacz [ setlocale ] i [Ustawienia regionalne](../../c-runtime-library/locale.md).

Gdy *end_ptr* ma **wartość null**, jest ignorowana. W przeciwnym razie wskaźnik do znaku, który zatrzymał skanowanie jest przechowywany w lokalizacji wskazywanej przez *end_ptr*. Konwersja nie jest możliwa, jeśli nie odnaleziono prawidłowych cyfr lub określono nieprawidłową podstawę. Wartość *ciągu* jest następnie przechowywana w lokalizacji wskazywanej przez *end_ptr*.

**strtol** oczekuje, że *ciąg* ma wskazywać ciąg o następującej postaci:

> [*odstęp*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*alfanumeryczne*]

Nawiasy kwadratowe ( `[ ]` ) otaczają opcjonalne elementy. Nawiasy klamrowe i pionowy pasek ( `{ | }` ) otaczają alternatywy dla pojedynczego elementu. *odstępy* mogą zawierać spacje i znaki tabulacji, które są ignorowane. *alfanumeryczne* są cyframi dziesiętnymi lub literami od "a" do "z" (lub od "a" do "z"). Pierwszy znak, który nie pasuje do tego formularza, zatrzyma skanowanie. Jeśli *baza* jest z przedziału od 2 do 36, jest używana jako podstawa liczby. Jeśli *Base* ma wartość 0, początkowe znaki ciągu wskazywane przez *ciąg* są używane do określenia podstawy. Jeśli pierwszym znakiem jest 0, a drugi znak nie jest "x" lub "X", ciąg jest interpretowany jako ósemkowa liczba całkowita. Jeśli pierwszy znak to "0", a drugi znak to "x" lub "X", ciąg jest interpretowany jako Szesnastkowa liczba całkowita. Jeśli pierwszym znakiem jest "1" do "9", ciąg jest interpretowany jako dziesiętna liczba całkowita. Litery od "a" do "z" (lub "A" do "z") mają przypisane wartości od 10 do 35. Skanowanie zezwala tylko na litery, których wartości są mniejsze niż *podstawowe*. Pierwszy znak poza zakresem podstawy powoduje zatrzymanie skanowania. Na przykład załóżmy, że *ciąg* rozpoczyna się od "01". Jeśli *Base* ma wartość 0, skaner zakłada, że jest to ósemkowa liczba całkowita. Znak "8" lub "9" uniemożliwia skanowanie.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura TCHAR.H|Nie zdefiniowano _MBCS _UNICODE &|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> lub \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|
|**_wcstol_l**|\<stdlib.h> lub \<wchar.h>|

**_strtol_l** Funkcje i **_wcstol_l** są specyficzne dla firmy Microsoft, nie jest częścią standardowej biblioteki C. Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../compatibility.md).

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [strtod](strtod-strtod-l-wcstod-wcstod-l.md) .

## <a name="see-also"></a>Zobacz też

[Konwersja danych](../data-conversion.md)\
[Ustawienie](../locale.md)\
[localeconv](localeconv.md)\
[setlocale, _wsetlocale](setlocale-wsetlocale.md)\
[Funkcje ciągu do wartości numerycznych](../string-to-numeric-value-functions.md)\
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)\
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)\
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)\
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)

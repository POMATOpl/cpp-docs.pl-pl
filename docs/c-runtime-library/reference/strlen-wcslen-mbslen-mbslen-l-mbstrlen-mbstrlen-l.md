---
description: 'Dowiedz się więcej na temat: strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen _mbstrlen_l'
title: strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l
ms.date: 4/2/2020
api_name:
- _mbslen
- _mbslen_l
- _mbstrlen
- wcslen
- _mbstrlen_l
- strlen
- _o__mbslen
- _o__mbslen_l
- _o__mbstrlen
- _o__mbstrlen_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbstrlen
- wcslen
- _tcslen
- _ftcslen
- strlen
- _mbslen
helpviewer_keywords:
- wcslen function
- string length, getting
- ftcslen function
- lengths, strings
- mbstrlen_l function
- _mbslen_l function
- _tcslen function
- mbslen_l function
- mbslen function
- _mbstrlen function
- strings [C++], getting length
- mbstrlen function
- _mbstrlen_l function
- _ftcslen function
- tcslen function
- strlen function
- _mbslen function
ms.assetid: 16462f2a-1e0f-4eb3-be55-bf1c83f374c2
ms.openlocfilehash: 54001a90003ff3a6931f43687fc08366607caf2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344838"
---
# <a name="strlen-wcslen-_mbslen-_mbslen_l-_mbstrlen-_mbstrlen_l"></a>strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l

Pobiera długość ciągu przy użyciu bieżących ustawień regionalnych lub określonych ustawień regionalnych. Bardziej bezpieczne wersje tych funkcji są dostępne; Zobacz [strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l](strnlen-strnlen-s.md)

> [!IMPORTANT]
> **_mbslen**, **_mbslen_l**, **_mbstrlen** i **_mbstrlen_l** nie mogą być używane w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows. Aby uzyskać więcej informacji, zobacz [funkcje CRT nieobsługiwane w aplikacjach platforma uniwersalna systemu Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Składnia

```C
size_t strlen(
   const char *str
);
size_t wcslen(
   const wchar_t *str
);
size_t _mbslen(
   const unsigned char *str
);
size_t _mbslen_l(
   const unsigned char *str,
   _locale_t locale
);
size_t _mbstrlen(
   const char *str
);
size_t _mbstrlen_l(
   const char *str,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametry

*str*<br/>
Ciąg zakończony znakiem null.

*locale*<br/>
Ustawienia regionalne do użycia.

## <a name="return-value"></a>Wartość zwracana

Każda z tych funkcji zwraca liczbę znaków w *str*, z wyłączeniem terminalu o wartości null. Żadna wartość zwracana nie jest zarezerwowana do wskazania błędu, z wyjątkiem **_mbstrlen** i **_mbstrlen_l**, które zwracają, `((size_t)(-1))` Jeśli ciąg zawiera nieprawidłowy znak wielobajtowy.

## <a name="remarks"></a>Uwagi

**strlen** interpretuje ciąg jako jednobajtowy ciąg znaków, więc jego wartość zwracana jest zawsze równa liczbie bajtów, nawet jeśli ciąg zawiera znaki wielobajtowe. **wcslen** to dwubajtowa wersja **strlen**; argumentem **wcslen** jest ciąg znaków dwubajtowych, a liczba znaków jest w szerokim (2-cyfrowym) znakami. **wcslen** i **strlen** zachowują się identycznie w inny sposób.

**Uwaga dotycząca zabezpieczeń** Te funkcje powodują potencjalne zagrożenie spowodowane przez problem z przepełnieniem buforu. Problemy związane z przepełnieniem buforu są częstą metodą ataku systemu, powodując nieuzasadnione podniesienie uprawnień. Aby uzyskać więcej informacji, zobacz [unikanie przekroczeń buforu](/windows/win32/SecBP/avoiding-buffer-overruns).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura TCHAR.H|Nie zdefiniowano _MBCS _UNICODE &|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcslen**|**strlen**|**strlen**|**wcslen**|
|**_tcsclen**|**strlen**|**_mbslen**|**wcslen**|
|**_tcsclen_l**|**strlen**|**_mbslen_l**|**wcslen**|

**_mbslen** i **_mbslen_l** zwracają liczbę znaków wielobajtowych w ciągu znaków wielobajtowych, ale nie sprawdzają poprawności znaku wielobajtowego. **_mbstrlen** i **_mbstrlen_l** testu pod kątem ważności znaku wielobajtowego i rozpoznawania sekwencji znaków wielobajtowych. Jeśli ciąg przeszedł do **_mbstrlen** lub **_mbstrlen_l** zawiera nieprawidłowy znak wielobajtowy dla strony kodowej, funkcja zwróci wartość-1 i ustawia **errno** na **EILSEQ**.

Wartość wyjściowa jest zależna od ustawienia ustawienia kategorii **LC_CTYPE** ustawień regionalnych; Aby uzyskać więcej informacji, zobacz [setlocals](setlocale-wsetlocale.md) . Wersje tych funkcji bez sufiksu **_l** używają bieżących ustawień regionalnych dla tego zachowania zależnego od ustawień regionalnych. wersje z sufiksem **_l** są identyczne, z tą różnicą, że korzystają z przekazaną w zamian parametru ustawień regionalnych. Aby uzyskać więcej informacji, zobacz [Ustawienia regionalne](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**strlen**|\<string.h>|
|**wcslen**|\<string.h> lub \<wchar.h>|
|**_mbslen**, **_mbslen_l**|\<mbstring.h>|
|**_mbstrlen**, **_mbstrlen_l**|\<stdlib.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_strlen.c
// Determine the length of a string. For the multi-byte character
// example to work correctly, the Japanese language support for
// non-Unicode programs must be enabled by the operating system.

#include <string.h>
#include <locale.h>

int main()
{
   char* str1 = "Count.";
   wchar_t* wstr1 = L"Count.";
   char * mbstr1;
   char * locale_string;

   // strlen gives the length of single-byte character string
   printf("Length of '%s' : %d\n", str1, strlen(str1) );

   // wstrlen gives the length of a wide character string
   wprintf(L"Length of '%s' : %d\n", wstr1, wcslen(wstr1) );

   // A multibyte string: [A] [B] [C] [katakana A] [D] [\0]
   // in Code Page 932. For this example to work correctly,
   // the Japanese language support must be enabled by the
   // operating system.
   mbstr1 = "ABC" "\x83\x40" "D";

   locale_string = setlocale(LC_CTYPE, "Japanese_Japan");

   if (locale_string == NULL)
   {
      printf("Japanese locale not enabled. Exiting.\n");
      exit(1);
   }
   else
   {
      printf("Locale set to %s\n", locale_string);
   }

   // _mbslen will recognize the Japanese multibyte character if the
   // current locale used by the operating system is Japanese
   printf("Length of '%s' : %d\n", mbstr1, _mbslen(mbstr1) );

   // _mbstrlen will recognize the Japanese multibyte character
   // since the CRT locale is set to Japanese even if the OS locale
   // isnot.
   printf("Length of '%s' : %d\n", mbstr1, _mbstrlen(mbstr1) );
   printf("Bytes in '%s' : %d\n", mbstr1, strlen(mbstr1) );

}
```

```Output
Length of 'Count.' : 6
Length of 'Count.' : 6
Length of 'ABCァD' : 5
Length of 'ABCァD' : 5
Bytes in 'ABCァD' : 6
```

## <a name="see-also"></a>Zobacz także

[Manipulowanie ciągami](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Interpretacja sekwencji Multibyte-Character](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Ustawienie](../../c-runtime-library/locale.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[Funkcje strcoll —](../../c-runtime-library/strcoll-functions.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>

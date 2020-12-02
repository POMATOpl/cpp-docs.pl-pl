---
title: '`_mbsnbcat_s`, `_mbsnbcat_s_l`'
description: Opis interfejsu API dla Microsoft Visual C++ `_mbsnbcat_s` i `_mbsnbcat_s_l` funkcje
ms.date: 12/2/2020
api_name:
- _mbsnbcat_s_l
- _mbsnbcat_s
- _o__mbsnbcat_s
- _o__mbsnbcat_s_l
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
helpviewer_keywords:
- _tcsncat function
- mbsnbcat_s function
- _mbsnbcat_s function
- _mbsnbcat_s_l function
- _tcsncat_s_l function
- tcsncat_s_l function
- mbsnbcat_s_l function
- tcsncat function
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
ms.openlocfilehash: c7198d806d8ebe077b423ff2135b5bdcf66ffac6
ms.sourcegitcommit: 9c45483572db4470fe5db5a7b596d5770303098c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2020
ms.locfileid: "96523117"
---
# <a name="_mbsnbcat_s-_mbsnbcat_s_l"></a>`_mbsnbcat_s`, `_mbsnbcat_s_l`

Dołącza do ciągu znaków wielobajtowych, co najwyżej, pierwsze **n** bajtów innego ciągu znaków wielobajtowych. Są to wersje programu [ `_mbsnbcat` , `_mbsnbcat_l` ](mbsnbcat-mbsnbcat-l.md) które mają ulepszenia zabezpieczeń, zgodnie z opisem w temacie [funkcje zabezpieczeń w CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Tego interfejsu API nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows. Aby uzyskać więcej informacji, zobacz [funkcje CRT nieobsługiwane w aplikacjach platforma uniwersalna systemu Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Składnia

```C
errno_t _mbsnbcat_s(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count
);
errno_t _mbsnbcat_s_l(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbcat_s(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbcat_s_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametry

*`dest`*\
Przerwany ciąg znaków wielobajtowych zakończony wartością null.

*`sizeInBytes`*\
Rozmiar *`dest`* buforu w bajtach.

*`src`*\
Ciąg źródłowy znaku wielobajtowego zakończony wartością null.

*`count`*\
Liczba bajtów z *`src`* do dołączenia *`dest`* .

*`locale`*\
Ustawienia regionalne do użycia.

## <a name="return-value"></a>Wartość zwracana

Zero, jeśli pomyślne; w przeciwnym razie kod błędu.

### <a name="error-conditions"></a>Warunki błędów

|**`dest`**|*`sizeInBytes`*|*`src`*|Wartość zwracana|
|------------|-------------------|-----------|------------------|
|**`NULL`**|dowolny|dowolny|**`EINVAL`**|
|Dowolny|<= 0|dowolny|**`EINVAL`**|
|Dowolny|dowolny|**`NULL`**|**`EINVAL`**|

Jeśli wystąpi którykolwiek z warunków błędów, funkcja generuje błąd nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli błąd jest obsługiwany, funkcja zwraca **`EINVAL`** i ustawia **errno** na **`EINVAL`** .

## <a name="remarks"></a>Uwagi

**`_mbsnbcat_s`** Funkcja dołącza do *`dest`* , co najwyżej, pierwsze *`count`* bajty *`src`* . Jeśli bajt, który bezpośrednio poprzedza znak null w *`dest`* , jest bajtem wiodącym, zostanie zastąpiony przez początkowy bajt *`src`* . W przeciwnym razie bajt początkowy *`src`* zastępuje kończący znak null *`dest`* . Jeśli bajt o wartości null występuje *`src`* przed *`count`* dołączeniem bajtów, **`_mbsnbcat_s`** dołącza wszystkie bajty z *`src`* , do znaku null. Jeśli *`count`* jest większa niż długość *`src`* , długość *`src`* jest używana zamiast *`count`* . Ciąg otrzymany jest zakończony znakiem null. Jeśli kopiowanie odbywa się między nakładającymi się ciągami, zachowanie jest niezdefiniowane.

Wartość wyjściowa jest zależna od ustawienia kategorii ustawień **`LC_CTYPE`** regionalnych; zobacz [setlocale _wsetlocale,](setlocale-wsetlocale.md) Aby uzyskać więcej informacji. Wersje tych funkcji są identyczne, z tą różnicą, że te, które nie mają **`_l`** sufiksu, używają bieżących ustawień regionalnych i tych, które mają **`_l`** sufiks, zamiast tego używają parametru ustawień regionalnych, który został przesłany. Aby uzyskać więcej informacji, zobacz [Ustawienia regionalne](../../c-runtime-library/locale.md).

W języku C++ korzystanie z tych funkcji jest uproszczone przez przeciążenia szablonów. Przeciążenia mogą automatycznie wywnioskować długość bufora, co eliminuje konieczność określenia argumentu rozmiaru i może automatycznie korzystać z ich nowszych, bezpieczniejszych funkcji, aby zastąpić starsze, mniej bezpieczne funkcje. Aby uzyskać więcej informacji, zobacz [bezpieczne przeciążenia szablonów](../../c-runtime-library/secure-template-overloads.md).

Wersje biblioteki debugowania tych funkcji najpierw wypełniają bufor 0xFE. Aby wyłączyć to zachowanie, użyj [`_CrtSetDebugFillThreshold`](crtsetdebugfillthreshold.md) .

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|`Tchar.h` procedury|`_UNICODE` i `_MBCS` nie zdefiniowane|`_MBCS` określonych|`_UNICODE` określonych|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**`_tcsncat_s`**|[strncat_s](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|**`_mbsnbcat_s`**|[wcsncat_s](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|
|**`_tcsncat_s_l`**|**`_strncat_s_l`**|**`_mbsnbcat_s_l`**|**`_wcsncat_s_l`**|

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**`_mbsnbcat_s`**|\<mbstring.h>|
|**`_mbsnbcat_s_l`**|\<mbstring.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Manipulowanie ciągami](../../c-runtime-library/string-manipulation-crt.md)\
[`_mbsnbcmp`, `_mbsnbcmp_l`](mbsnbcmp-mbsnbcmp-l.md)\
[`_strncnt`, `_wcsncnt`, `_mbsnbcnt`, `_mbsnbcnt_l`, `_mbsnccnt`, `_mbsnccnt_l`](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)\
[`_mbsnbcpy`, `_mbsnbcpy_l`](mbsnbcpy-mbsnbcpy-l.md)\
[`_mbsnbcpy_s`, `_mbsnbcpy_s_l`](mbsnbcpy-s-mbsnbcpy-s-l.md)\
[`_mbsnbset`, `_mbsnbset_l`](mbsnbset-mbsnbset-l.md)\
[`strncat`, `_strncat_l`, `wcsncat`, `_wcsncat_l`, `_mbsncat`, `_mbsncat_l`](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)\
[`strncat_s`, `_strncat_s_l`, `wcsncat_s`, `_wcsncat_s_l`, `_mbsncat_s`, `_mbsncat_s_l`](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)

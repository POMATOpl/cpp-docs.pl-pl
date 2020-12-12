---
description: 'Dowiedz się więcej na temat: _mbccpy, _mbccpy_l'
title: _mbccpy, _mbccpy_l
ms.date: 4/2/2020
api_name:
- _mbccpy
- _mbccpy_l
- _o__mbccpy
- _o__mbccpy_l
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
- _mbccpy
- tccpy
- ftccpy
- mbccpy
- _tccpy
- _ftccpy
helpviewer_keywords:
- _tccpy function
- _tccpy_l function
- tccpy_l function
- tccpy function
- mbccpy function
- _mbccpy_l function
- _mbccpy function
- mbccpy_l function
ms.assetid: 13f4de6e-7792-41ac-b319-dd9b135433aa
ms.openlocfilehash: a5d63a2d4ccd623d035fdc423774d6a344d107f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299595"
---
# <a name="_mbccpy-_mbccpy_l"></a>_mbccpy, _mbccpy_l

Kopiuje znak wielobajtowy z jednego ciągu do innego ciągu. Bardziej bezpieczne wersje tych funkcji są dostępne; Zobacz [_mbccpy_s, _mbccpy_s_l](mbccpy-s-mbccpy-s-l.md).

> [!IMPORTANT]
> Tego interfejsu API nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows. Aby uzyskać więcej informacji, zobacz [funkcje CRT nieobsługiwane w aplikacjach platforma uniwersalna systemu Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Składnia

```C
void _mbccpy(
   unsigned char *dest,
   const unsigned char *src
);
void _mbccpy_l(
   unsigned char *dest,
   const unsigned char *src,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametry

*dest*<br/>
Kopiuj miejsce docelowe.

*src*<br/>
Znak wielobajtowy do skopiowania.

*locale*<br/>
Ustawienia regionalne do użycia.

## <a name="remarks"></a>Uwagi

Funkcja **_mbccpy** kopiuje jeden znak wielobajtowy z *src* do miejsca *docelowego*.

Ta funkcja sprawdza poprawność swoich parametrów. Jeśli **_mbccpy** jest przekazanie wskaźnika o wartości null dla elementu *docelowego* lub *src*, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, **errno** jest ustawiona na **EINVAL**.

**_mbccpy** używa bieżących ustawień regionalnych dla wszelkich zachowań zależnych od ustawień regionalnych. **_mbccpy_l** jest taka sama jak **_mbccpy** , z tą różnicą, że **_mbccpy_l** korzysta z ustawień regionalnych przewidzianych dla wszelkich zachowań zależnych od ustawień regionalnych. Aby uzyskać więcej informacji, zobacz [Ustawienia regionalne](../../c-runtime-library/locale.md).

**Uwaga dotycząca zabezpieczeń** Użyj ciągu zakończenia o wartości null. Ciąg zakończony znakiem null nie może przekraczać rozmiaru buforu docelowego. Aby uzyskać więcej informacji, zobacz [unikanie przekroczeń buforu](/windows/win32/SecBP/avoiding-buffer-overruns). Problemy związane z przepełnieniem buforu są częstą metodą ataku systemu, powodując nieuzasadnione podniesienie uprawnień.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura tchar.h|_UNICODE i _MBCS niezdefiniowane|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy**|Mapuje na makro lub funkcję wbudowaną|**_mbccpy**|Mapuje na makro lub funkcję wbudowaną|
|**_tccpy_l**|n/d|**_mbccpy_l**|n/d|

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_mbccpy**|\<mbctype.h>|
|**_mbccpy_l**|\<mbctype.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Ustawienie](../../c-runtime-library/locale.md)<br/>
[Interpretacja sekwencji Multibyte-Character](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>

---
description: 'Dowiedz się więcej na temat: _ismbbkana, _ismbbkana_l'
title: _ismbbkana, _ismbbkana_l
ms.date: 4/2/2020
api_name:
- _ismbbkana_l
- _ismbbkana
- _o__ismbbkana
- _o__ismbbkana_l
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
- _ismbbkana_l
- ismbbkana_l
- ismbbkana
- _ismbbkana
helpviewer_keywords:
- _ismbbkana_l function
- _ismbbkana function
- ismbbkana function
- ismbbkana_l function
ms.assetid: 64d4eb4a-205a-40ef-be35-ff9d77fabbaf
ms.openlocfilehash: 3b4c005068a6a646c256d0f091e4b86e15df2acb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335649"
---
# <a name="_ismbbkana-_ismbbkana_l"></a>_ismbbkana, _ismbbkana_l

Testuje symbol katakana i jest specyficzny dla strony kodowej 932.

## <a name="syntax"></a>Składnia

```C
int _ismbbkana(
   unsigned int c
);
int _ismbbkana_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametry

*s*<br/>
Liczba całkowita do przetestowania.

*locale*<br/>
Ustawienia regionalne do użycia.

## <a name="return-value"></a>Wartość zwracana

**_ismbbkana** zwraca wartość różną od zera, jeśli liczba całkowita *c* jest symbolem katakana lub 0, jeśli nie jest. **_ismbbkana** używa bieżących ustawień regionalnych dla informacji o znakach zależnych od ustawień regionalnych. **_ismbbkana_l** jest identyczny, z tą różnicą, że używa obiektu ustawień regionalnych przekazaną. Aby uzyskać więcej informacji, zobacz [Ustawienia regionalne](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Uwagi

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_ismbbkana**|\<mbctype.h>|
|**_ismbbkana_l**|\<mbctype.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Klasyfikacja bajtów](../../c-runtime-library/byte-classification.md)<br/>
[Procedury _ismbb](../../c-runtime-library/ismbb-routines.md)<br/>

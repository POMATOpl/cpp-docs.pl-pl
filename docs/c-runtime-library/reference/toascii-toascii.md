---
description: 'Dowiedz się więcej na temat: ToAscii, __toascii'
title: toascii, __toascii
ms.date: 11/04/2016
api_name:
- __toascii
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
ms.openlocfilehash: 9f1718da5e7d701bb6cc6ea68c1e21b6fe4283f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318354"
---
# <a name="toascii-__toascii"></a>toascii, __toascii

Konwertuje znaki na 7-bitowe ASCII przez obcinanie.

## <a name="syntax"></a>Składnia

```C
int __toascii(
   int c
);
#define toascii __toascii
```

### <a name="parameters"></a>Parametry

*s*<br/>
Znak do przekonwertowania.

## <a name="return-value"></a>Wartość zwracana

**__toascii** konwertuje wartość *c* na 7-bitowy zakres ASCII i zwraca wynik. Brak wartości zwracanej zastrzeżonej do wskazania błędu.

## <a name="remarks"></a>Uwagi

Procedura **__toascii** konwertuje dany znak na znak ASCII poprzez obcinanie go do 7 bitów o niskiej kolejności. Nie są stosowane żadne inne przekształcenia.

Procedura **__toascii** jest definiowana jako makro, chyba że jest zdefiniowane _CTYPE_DISABLE_MACROS makro preprocesora. W celu zapewnienia zgodności z poprzednimi wersjami **ToAscii** jest definiowana jako makro tylko wtedy, gdy [&#95;&#95;STDC&#95;&#95;](../../preprocessor/predefined-macros.md) nie jest zdefiniowana lub jest zdefiniowana jako 0; w przeciwnym razie jest to niezdefiniowane.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**ToAscii**, **__toascii**|S \<ctype.h><br /><br /> C++: \<cctype> lub \<ctype.h>|

Makro **ToAscii** jest rozszerzeniem POSIX, a **__toascii** jest implementacją systemu POSIX przez firmę Microsoft. Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Konwersja danych](../../c-runtime-library/data-conversion.md)<br/>
[to, ISW, procedury](../../c-runtime-library/is-isw-routines.md)<br/>
[do funkcji](../../c-runtime-library/to-functions.md)<br/>

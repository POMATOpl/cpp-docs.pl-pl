---
description: 'Dowiedz się więcej na temat: btowc'
title: btowc
ms.date: 4/2/2020
api_name:
- btowc
- _o_btowc
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
- btowc
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
ms.openlocfilehash: bbd6121499e03c356e80e49cbcbe75929ca96c2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171728"
---
# <a name="btowc"></a>btowc

Określ, czy liczba całkowita reprezentuje prawidłowy znak jednobajtowy w stanie przesunięcia początkowego.

## <a name="syntax"></a>Składnia

```C
wint_t btowc(
   int character
);
```

### <a name="parameters"></a>Parametry

*Opis*<br/>
Liczba całkowita do przetestowania.

## <a name="return-value"></a>Wartość zwracana

Zwraca reprezentację znaku dwubajtowego znak, jeśli liczba całkowita reprezentuje prawidłowy znak pojedynczej części w stanie początkowym zmiany. Zwraca WEOF, jeśli liczba całkowita to EOF lub nie jest prawidłowym znakiem jednobajtowym w stanie początkowym zmiany. Na dane wyjściowe tej funkcji wpływają bieżące ustawienia regionalne **LC_TYPE** .

## <a name="remarks"></a>Uwagi

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**btowc**|\<stdio.h> lub \<wchar.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>

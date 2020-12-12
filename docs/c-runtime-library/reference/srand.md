---
description: 'Dowiedz się więcej na temat: srand'
title: srand
ms.date: 4/2/2020
api_name:
- srand
- _o_srand
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
- api-ms-win-crt-utility-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- srand
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.openlocfilehash: bea91841b549fae09faa4345767fc22cf4d6208e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292173"
---
# <a name="srand"></a>srand

Ustawia początkową wartość inicjatora dla generatora numerów pseudolosowych używanych przez funkcję **Rand** .

## <a name="syntax"></a>Składnia

```C
void srand(
   unsigned int seed
);
```

### <a name="parameters"></a>Parametry

*sadzenia*<br/>
Inicjator dla generowania numerów pseudolosowych

## <a name="remarks"></a>Uwagi

Funkcja **srand** ustawia punkt początkowy do generowania serii pseudolosowych liczb całkowitych w bieżącym wątku. Aby ponownie zainicjować generator, aby utworzyć taką samą sekwencję wyników, wywołaj funkcję **srand** i Użyj tego samego argumentu *inicjatora* . Każda inna wartość *inicjatora* ustawia generator do innego punktu początkowego w sekwencji pseudolosowych. **Rand** pobiera wygenerowane numery pseudolosowych. Wywołanie funkcji **Rand** przed wywołaniem funkcji **srand** generuje taką samą sekwencję jak wywołanie **srand** z *inicjatorem* , który przeszedł jako 1.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**srand**|\<stdlib.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

Zobacz przykład dla funkcji [Rand](rand.md).

## <a name="see-also"></a>Zobacz też

[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[Rand](rand.md)<br/>

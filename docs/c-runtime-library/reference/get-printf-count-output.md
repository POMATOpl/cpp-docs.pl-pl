---
description: 'Dowiedz się więcej na temat: _get_printf_count_output'
title: _get_printf_count_output
ms.date: 11/04/2016
api_name:
- _get_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
ms.openlocfilehash: fe5ee728b7bc8400cd93ec4e93131496d59334c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339006"
---
# <a name="_get_printf_count_output"></a>_get_printf_count_output

Wskazuje, czy funkcje rodziny [printf, _printf_l, wprintf _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)są obsługiwane w formacie **% n** .

## <a name="syntax"></a>Składnia

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>Wartość zwracana

Wartość niezerowa, jeśli **% n** jest obsługiwana, 0 Jeśli **% n** nie jest obsługiwany.

## <a name="remarks"></a>Uwagi

Jeśli parametr **% n** nie jest obsługiwany (domyślnie), napotkanie elementu **% n** w ciągu formatu dowolnej funkcji **printf** wywoła procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli jest włączona obsługa **% n** (zobacz [_set_printf_count_output](set-printf-count-output.md)), a **% n** będzie zachowywać się zgodnie z opisem w [składni specyfikacji formatowania: funkcje printf i wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [_set_printf_count_output](set-printf-count-output.md).

## <a name="see-also"></a>Zobacz też

[_set_printf_count_output](set-printf-count-output.md)<br/>

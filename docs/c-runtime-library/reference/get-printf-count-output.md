---
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
ms.openlocfilehash: 15b37ac759821ad56cc5c03c9b98719d8f0cc19a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955706"
---
# <a name="_get_printf_count_output"></a>_get_printf_count_output

Wskazuje, czy funkcja [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-Family obsługuje format **% n** .

## <a name="syntax"></a>Składnia

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>Wartość zwracana

Wartość niezerowa, jeśli **% n** jest obsługiwana, 0 Jeśli **% n** nie jest obsługiwany.

## <a name="remarks"></a>Uwagi

Jeśli parametr **% n** nie jest obsługiwany (domyślnie), napotkanie elementu **% n** w ciągu formatu dowolnej funkcji **printf** wywoła procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli włączona jest obsługa **% n** (zobacz [_set_printf_count_output](set-printf-count-output.md)), **% n** będzie zachowywać się zgodnie z opisem w [składni specyfikacji formatu: funkcje printf i wprintf](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

Zobacz przykład dla [_set_printf_count_output](set-printf-count-output.md).

## <a name="see-also"></a>Zobacz także

[_set_printf_count_output](set-printf-count-output.md)<br/>

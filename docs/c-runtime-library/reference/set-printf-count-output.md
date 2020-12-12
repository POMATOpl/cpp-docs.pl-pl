---
description: 'Dowiedz się więcej na temat: _set_printf_count_output'
title: _set_printf_count_output
ms.date: 11/04/2016
api_name:
- _set_printf_count_output
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
- set_printf_count_output
- _set_printf_count_output
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
ms.openlocfilehash: 455c4f0e49ce111853145a05d78efabcd76386fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114250"
---
# <a name="_set_printf_count_output"></a>_set_printf_count_output

Włącza lub wyłącza obsługę formatu **% n** w funkcjach [printf, _printf_l, wprintf i Family _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="syntax"></a>Składnia

```C
int _set_printf_count_output(
   int enable
);
```

### <a name="parameters"></a>Parametry

*mogły*<br/>
Wartość niezerowa, aby włączyć obsługę elementu **% n** , 0, aby wyłączyć obsługę **% n** .

## <a name="property-valuereturn-value"></a>Wartość właściwości/Zwracana wartość

Stan **% n** obsługi przed wywołaniem tej funkcji: wartość niezerowa, jeśli włączono obsługę **% n** , 0, jeśli została wyłączona.

## <a name="remarks"></a>Uwagi

Ze względów bezpieczeństwa Pomoc techniczna dla specyfikatora formatu **% n** jest domyślnie wyłączona w **printf** i wszystkich jego wariantów. Jeśli element **% n** zostanie napotkany w specyfikacji formatu **printf** , domyślnym zachowaniem jest Wywołaj procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Wywołanie **_set_printf_count_output** z niezerowym argumentem spowoduje, że funkcje rodziny **printf** będą interpretować element **% n** , zgodnie z opisem w [składni specyfikacji formatowania: printf i wprintf Functions](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_set_printf_count_output**|\<stdio.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_set_printf_count_output.c
#include <stdio.h>

int main()
{
   int e;
   int i;
   e = _set_printf_count_output( 1 );
   printf( "%%n support was %sabled.\n",
        e ? "en" : "dis" );
   printf( "%%n support is now %sabled.\n",
        _get_printf_count_output() ? "en" : "dis" );
   printf( "12345%n6789\n", &i ); // %n format should set i to 5
   printf( "i = %d\n", i );
}
```

```Output
%n support was disabled.
%n support is now enabled.
123456789
i = 5
```

## <a name="see-also"></a>Zobacz także

[_get_printf_count_output](get-printf-count-output.md)<br/>

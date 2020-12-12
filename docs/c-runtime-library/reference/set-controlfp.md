---
description: 'Dowiedz się więcej na temat: _set_controlfp'
title: _set_controlfp
ms.date: 04/05/2018
api_name:
- _set_controlfp
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_controlfp
- _set_controlfp
helpviewer_keywords:
- set_controlfp function
- floating-point functions, setting control word
- _set_controlfp function
ms.assetid: e0689d50-f68a-4028-a9c1-fb23eedee4ad
ms.openlocfilehash: 44316cb4114d06ced1b3d67a261bc8d3ceb1aee6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288870"
---
# <a name="_set_controlfp"></a>_set_controlfp

Ustawia słowo sterujące zmiennoprzecinkowe.

## <a name="syntax"></a>Składnia

```C
void __cdecl _set_controlfp(
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>Parametry

*newControl*<br/>
Nowe wartości bitowe programu Control-Word.

*maska*<br/>
Maska dla nowego tekstu kontrolki do ustawienia.

## <a name="return-value"></a>Wartość zwracana

Brak.

## <a name="remarks"></a>Uwagi

Funkcja **_set_controlfp** jest podobna do **_control87**, ale ustawia tylko słowo sterujące zmiennoprzecinkowe na *newControl*. Bity w wartości wskazują stan sterowania zmiennoprzecinkowego. Stan kontrolki zmiennoprzecinkowej umożliwia programowi zmianę precyzji, zaokrąglania i nieskończoności w pakiecie funkcji matematycznych zmiennoprzecinkowych. Można także maskować lub usunąć maskowanie wyjątków zmiennoprzecinkowych za pomocą **_set_controlfp**. Aby uzyskać więcej informacji, zobacz [_control87, _controlfp, \_ _control87_2](control87-controlfp-control87-2.md).

Ta funkcja jest przestarzała podczas kompilowania z [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md) , ponieważ środowisko uruchomieniowe języka wspólnego obsługuje tylko domyślną precyzję zmiennoprzecinkową.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|Zgodność|
|-------------|---------------------|-------------------|
|**_set_controlfp**|\<float.h>|tylko procesor x86|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>

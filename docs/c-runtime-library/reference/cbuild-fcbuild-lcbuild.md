---
description: 'Dowiedz się więcej na temat: _Cbuild, _FCbuild, _LCbuild'
title: _Cbuild, _FCbuild, _LCbuild
ms.date: 03/30/2018
api_name:
- _Cbuild
- _FCbuild
- _LCbuild
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _Cbuild
- _FCbuild
- _LCbuild
- complex/_Cbuild
- complex/_FCbuild
- complex/_LCbuild
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
ms.openlocfilehash: bbca2571a10badcfc02da3e0d2f404590a1d7eb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275233"
---
# <a name="_cbuild-_fcbuild-_lcbuild"></a>_Cbuild, _FCbuild, _LCbuild

Konstruuje liczbę zespoloną z części rzeczywistych i urojonych.

## <a name="syntax"></a>Składnia

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>Parametry

*liczba rzeczywista*<br/>
Rzeczywista część liczby zespolonej do skonstruowania.

*urojony*<br/>
Część urojona liczby zespolonej do skonstruowania.

## <a name="return-value"></a>Wartość zwracana

Struktura **_Dcomplex**, **_Fcomplex** lub **_Lcomplex** reprezentująca liczbę zespoloną (*rzeczywistą*, *urojoną* \* i) dla wartości określonego typu zmiennoprzecinkowego.

## <a name="remarks"></a>Uwagi

Funkcje **_Cbuild**, **_FCbuild** i **_LCbuild** upraszczają tworzenie typów złożonych. Użyj funkcji [Creal, crealf, creall](creal-crealf-creall.md) i [cimag, cimagf, cimagl,](cimag-cimagf-cimagl.md) aby pobrać rzeczywiste i urojone fragmenty reprezentowanej liczby zespolonej.

## <a name="requirements"></a>Wymagania

|Procedura|Nagłówek języka C|Nagłówek C++|
|-------------|--------------|------------------|
|**_Cbuild**, **_FCbuild**, **_LCbuild**|\<complex.h>|\<ccomplex>|

Te funkcje są specyficzne dla firmy Microsoft. Typy **_Dcomplex**, **_Fcomplex** i **_Lcomplex** są odpowiednikami specyficznymi dla firmy Microsoft do niezaimplementowanych natywnych typów C99 **`double _Complex`** , **`float _Complex`** i **`long double _Complex`** , odpowiednio. Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>

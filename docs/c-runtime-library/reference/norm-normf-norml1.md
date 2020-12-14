---
description: 'Dowiedz się więcej o: normie, normf, normie'
title: norm, normf, norml
ms.date: 04/05/2018
api_name:
- norm
- normf
- norml
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
- norm
- normf
- norml
- complex/norm
- complex/normf
- complex/norml
helpviewer_keywords:
- norm function
- normf function
- norml function
ms.assetid: 9786ecfe-0019-4553-b378-0af6c691e15c
ms.openlocfilehash: 175cff5f9c0e31a56a86a96c3262e2c3c546fe4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256305"
---
# <a name="norm-normf-norml"></a>norm, normf, norml

Pobiera kwadratową wartość liczby zespolonej.

## <a name="syntax"></a>Składnia

```C
double norm( _Dcomplex z );
float normf( _Fcomplex z );
long double norml( _Lcomplex z );
```

```cpp
float norm( _Fcomplex z );  // C++ only
long double norm( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Parametry

*porządku*<br/>
Liczba złożona.

## <a name="return-value"></a>Wartość zwracana

Kwadratowa wielkość *z.*

## <a name="remarks"></a>Uwagi

Ponieważ C++ pozwala na Przeciążenie, można wywoływać przeciążenia **normy** , które pobierają **_Fcomplex** lub **_Lcomplex** wartości, oraz zwracają **`float`** lub **`long double`** wartości. W programie w języku C **norma** zawsze przyjmuje wartość **_Dcomplex** i zwraca **`double`** wartość.

## <a name="requirements"></a>Wymagania

|Procedura|Nagłówek języka C|Nagłówek C++|
|-------------|--------------|------------------|
|**norma**, **normf**, **norma**|\<complex.h>|\<complex.h>|

Typy **_Fcomplex**, **_Dcomplex** i **_Lcomplex** są odpowiednikami charakterystycznymi dla niewdrożonych natywnych typów C99 **zmiennoprzecinkowych _Complex**, **Double _Complex** i **Long Double _Complex**.  Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>

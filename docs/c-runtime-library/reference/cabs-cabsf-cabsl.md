---
description: 'Dowiedz się więcej na temat: OOZ, cabsf, OOZ'
title: cabs, cabsf, cabsl
ms.date: 11/04/2016
api_name:
- cabs
- cabsf
- cabsl
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
- cabs
- cabsf
- cabsl
- complex/cabs
- complex/cabsf
- complex/cabsl
helpviewer_keywords:
- cabs function
- cabsf function
- cabsl function
ms.assetid: 6b8eb453-cc8f-4972-bebf-351cbdfdfc15
ms.openlocfilehash: 2ae24a0b7c158c2a13a595e946ee79b0760d75ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171663"
---
# <a name="cabs-cabsf-cabsl"></a>cabs, cabsf, cabsl

Pobiera wartość bezwzględną liczby zespolonej.

## <a name="syntax"></a>Składnia

```C
double cabs(
   _Dcomplex z
);
float cabs(
   _Fcomplex z
);  // C++ only
long double cabs(
   _Lcomplex z
);  // C++ only
float cabsf(
   _Fcomplex z
);
long double cabsl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Parametry

*porządku*<br/>
Liczba złożona.

## <a name="return-value"></a>Wartość zwracana

Wartość bezwzględna *z.*

## <a name="remarks"></a>Uwagi

Ponieważ C++ pozwala na Przeciążenie, można wywoływać przeciążenia **OOZ** , które pobierają **_Fcomplex** lub **_Lcomplex** wartości, oraz zwracają **`float`** lub **`long double`** wartości. W programie w języku C, **OOZ** zawsze przyjmuje wartość **_Dcomplex** i zwraca **`double`** wartość.

## <a name="requirements"></a>Wymagania

|Procedura|Nagłówek języka C|Nagłówek C++|
|-------------|--------------|------------------|
|**OOZ**,               **cabsf**, **OOZ**|\<complex.h>|\<ccomplex>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>

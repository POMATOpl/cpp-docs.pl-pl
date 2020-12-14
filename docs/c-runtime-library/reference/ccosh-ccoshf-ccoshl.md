---
description: 'Dowiedz się więcej na temat: ccosh, ccoshf, ccoshl'
title: ccosh, ccoshf, ccoshl
ms.date: 11/04/2016
api_name:
- ccosh
- ccoshf
- ccoshl
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
- ccosh
- ccoshf
- ccoshl
- complex/ccosh
- complex/ccoshf
- complex/ccoshl
helpviewer_keywords:
- ccosh function
- ccoshf function
- ccoshl function
ms.assetid: 79667449-4edf-4948-bf6b-720adf2b3f3b
ms.openlocfilehash: 11e6dc87f72753c10e62e10cfba20701fe706359
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275116"
---
# <a name="ccosh-ccoshf-ccoshl"></a>ccosh, ccoshf, ccoshl

Pobiera cosinus hiperboliczny liczby zespolonej.

## <a name="syntax"></a>Składnia

```C
_Dcomplex ccosh(
   _Dcomplex z
);
_Fcomplex ccosh(
   _Fcomplex z
);  // C++ only
_Lcomplex ccosh(
   _Lcomplex z
);  // C++ only
_Fcomplex ccoshf(
   _Fcomplex z
);
_Lcomplex ccoshl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Parametry

*porządku*<br/>
Liczba złożona, która reprezentuje kąt w radianach.

## <a name="return-value"></a>Wartość zwracana

Cosinus hiperboliczny *z z, w* radianach.

## <a name="remarks"></a>Uwagi

Ponieważ C++ pozwala na Przeciążenie, można wywoływać przeciążenia **ccosh** , które pobierają i zwracają wartości **_Fcomplex** i **_Lcomplex** . W programie C **ccosh** zawsze przyjmuje i zwraca wartość **_Dcomplex** .

## <a name="requirements"></a>Wymagania

|Procedura|Nagłówek języka C|Nagłówek C++|
|-------------|--------------|------------------|
|**ccosh**,               **ccoshf**, **ccoshl**|\<complex.h>|\<ccomplex>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh, ctanhf, ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan, catanf, catanl](catan-catanf-catanl.md)<br/>
[csinh, csinhf, csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[cacosh, cacoshf, cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos, cacosf, cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[casin, casinf, casinl](casin-casinf-casinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>

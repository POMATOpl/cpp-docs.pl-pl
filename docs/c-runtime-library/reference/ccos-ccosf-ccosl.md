---
description: 'Dowiedz się więcej na temat: ccos, ccosf, ccosl'
title: ccos, ccosf, ccosl
ms.date: 11/04/2016
api_name:
- ccos
- ccosf
- ccosl
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
- ccos
- ccosf
- ccosl
- complex/ccos
- complex/ccosf
- complex/ccosl
helpviewer_keywords:
- ccos function
- ccosf function
- ccosl function
ms.assetid: 4ab936ac-ff85-49ac-9418-2b69cf5d4696
ms.openlocfilehash: 54036a2ddd3d61bba1d11a4841eaab1bd546c0ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275142"
---
# <a name="ccos-ccosf-ccosl"></a>ccos, ccosf, ccosl

Pobiera cosinus liczby zespolonej.

## <a name="syntax"></a>Składnia

```C
_Dcomplex ccos(
   _Dcomplex z
);
_Fcomplex ccos(
   _Fcomplex z
);  // C++ only
_Lcomplex ccos(
   _Lcomplex z
);  // C++ only
_Fcomplex ccosf(
   _Fcomplex z
);
_Lcomplex ccosl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Parametry

*porządku*<br/>
Liczba złożona, która reprezentuje kąt w radianach.

## <a name="return-value"></a>Wartość zwracana

Cosinus *z z, w* radianach.

## <a name="remarks"></a>Uwagi

Ponieważ C++ pozwala na Przeciążenie, można wywoływać przeciążenia **ccos** , które pobierają i zwracają wartości **_Fcomplex** i **_Lcomplex** . W programie C **ccos** zawsze przyjmuje i zwraca wartość **_Dcomplex** .

## <a name="requirements"></a>Wymagania

|Procedura|Nagłówek języka C|Nagłówek C++|
|-------------|--------------|------------------|
|**ccos**,               **ccosf**, **ccosl**|\<complex.h>|\<ccomplex>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh, ctanhf, ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan, catanf, catanl](catan-catanf-catanl.md)<br/>
[csinh, csinhf, csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh, ccoshf, ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh, cacoshf, cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos, cacosf, cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[casin, casinf, casinl](casin-casinf-casinl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>

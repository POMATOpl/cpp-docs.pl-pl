---
description: 'Dowiedz się więcej na temat: cacosh, cacoshf, cacoshl'
title: cacosh, cacoshf, cacoshl
ms.date: 11/04/2016
api_name:
- cacosh
- cacoshf
- cacoshl
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
- cacosh
- cacoshf
- cacoshl
- complex/cacosh
- complex/cacoshf
- complex/cacoshl
helpviewer_keywords:
- cacosh function
- cacoshf function
- cacoshl function
ms.assetid: 83fd05eb-3587-4741-9be6-589a830a1703
ms.openlocfilehash: c822a63021d68c7b07768b19c55be344f258e195
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171572"
---
# <a name="cacosh-cacoshf-cacoshl"></a>cacosh, cacoshf, cacoshl

Pobiera odwrotny cosinus hiperboliczny liczby zespolonej z rozgałęzieniem o wartości mniejszej niż 1 wzdłuż osi rzeczywistej. .

## <a name="syntax"></a>Składnia

```C
_Dcomplex cacosh(
   _Dcomplex z
);
_Fcomplex cacosh(
   _Fcomplex z
);  // C++ only
_Lcomplex cacosh(
   _Lcomplex z
);  // C++ only
_Fcomplex cacoshf(
   _Fcomplex z
);
_Lcomplex cacoshl(
   _Lcomplex z
);
```

### <a name="parameters"></a>Parametry

*porządku*<br/>
Liczba zespolona, która reprezentuje kąt w radianach.

## <a name="return-value"></a>Wartość zwracana

Arcus cosinus hiperboliczny *z z, w* radianach. Wynik nie jest ograniczony i nieujemny wzdłuż rzeczywistej osi, a w interwale [-iπ, + iπ] wzdłuż osi urojonej.

## <a name="remarks"></a>Uwagi

Ponieważ C++ pozwala na Przeciążenie, można wywoływać przeciążenia **cacosh** , które pobierają i zwracają wartości **_Fcomplex** i **_Lcomplex** . W programie C **cacosh** zawsze przyjmuje i zwraca wartość **_Dcomplex** .

## <a name="requirements"></a>Wymagania

|Procedura|Nagłówek języka C|Nagłówek C++|
|-------------|--------------|------------------|
|**cacosh**,               **cacoshf**, **cacoshl**|\<complex.h>|\<ccomplex>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh, ctanhf, ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan, catanf, catanl](catan-catanf-catanl.md)<br/>
[csinh, csinhf, csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh, ccoshf, ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacos, cacosf, cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[casin, casinf, casinl](casin-casinf-casinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>

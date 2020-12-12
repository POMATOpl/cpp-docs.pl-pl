---
description: 'Dowiedz się więcej na temat: Catan, catanf, catanl'
title: catan, catanf, catanl
ms.date: 11/04/2016
api_name:
- catan
- catanf
- catanl
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
- catan
- catanf
- catanl
- complex/catan
- complex/catanf
- complex/catanl
helpviewer_keywords:
- catan function
- catanf function
- catanl function
ms.assetid: 8415ed9c-7909-4d08-b532-4630bafdc7e8
ms.openlocfilehash: c17b4344b60c9e9ba7b79edd911ac85a7ba4d5c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326327"
---
# <a name="catan-catanf-catanl"></a>catan, catanf, catanl

Pobiera arcus tangens liczby zespolonej z rozgałęzieniem rozmieszczonym poza interwałem [-1; + 1] wzdłuż osi urojonej.

## <a name="syntax"></a>Składnia

```C
_Dcomplex catan( _Dcomplex z );
_Fcomplex catanf( _Fcomplex z );
_Lcomplex catanl( _Lcomplex z );
```

```cpp
_Fcomplex catan( _Fcomplex z );  // C++ only
_Lcomplex catan( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Parametry

*porządku*<br/>
Liczba zespolona, która reprezentuje kąt w radianach.

## <a name="return-value"></a>Wartość zwracana

Arcus *tangens z z, w* radianach. Wynik nie jest powiązany wzdłuż osi urojonej, a w interwale [-π/2; + π/2] wzdłuż osi rzeczywistej.

## <a name="remarks"></a>Uwagi

Ponieważ C++ pozwala na Przeciążenie, można wywoływać przeciążenia **Catan** , które pobierają i zwracają wartości **_Fcomplex** i **_Lcomplex** . W programie C **Catan** zawsze przyjmuje i zwraca wartość **_Dcomplex** .

## <a name="requirements"></a>Wymagania

|Procedura|Nagłówek języka C|Nagłówek C++|
|-------------|--------------|------------------|
|**Catan**,               **catanf**, **catanl**|\<complex.h>|\<ccomplex>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Alfabetyczne zestawienie funkcji](crt-alphabetical-function-reference.md)<br/>
[catanh, catanhf, catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh, ctanhf, ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[csinh, csinhf, csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh, casinhf, casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh, ccoshf, ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh, cacoshf, cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos, cacosf, cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan, ctanf, ctanl](ctan-ctanf-ctanl.md)<br/>
[csin, csinf, csinl](csin-csinf-csinl.md)<br/>
[casin, casinf, casinl](casin-casinf-casinl.md)<br/>
[ccos, ccosf, ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt, csqrtf, csqrtl](csqrt-csqrtf-csqrtl.md)<br/>

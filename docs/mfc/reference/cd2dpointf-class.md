---
description: 'Dowiedz się więcej na temat: Klasa CD2DPointF'
title: Klasa CD2DPointF
ms.date: 11/04/2016
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
ms.openlocfilehash: 0f63aa35acb33504c96316b67ecc4f885f4f0247
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193360"
---
# <a name="cd2dpointf-class"></a>Klasa CD2DPointF

Otoka dla `D2D1_POINT_2F` .

## <a name="syntax"></a>Składnia

```
class CD2DPointF : public D2D1_POINT_2F;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DPointF::CD2DPointF](#cd2dpointf)|Przeciążone. Konstruuje `CD2DPointF` obiekt z `D2D1_POINT_2F` obiektu.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DPointF:: operator CPoint](#operator_cpoint)|Konwertuje `CD2DPointF` na `CPoint` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`D2D1_POINT_2F`

`CD2DPointF`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dpointfcd2dpointf"></a><a name="cd2dpointf"></a> CD2DPointF::CD2DPointF

Konstruuje obiekt CD2DPointF z obiektu CPoint.

```
CD2DPointF(const CPoint& pt);
CD2DPointF(const D2D1_POINT_2F& pt);
CD2DPointF(const D2D1_POINT_2F* pt);
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```

### <a name="parameters"></a>Parametry

*zmiennoprzecinkow*<br/>
punkt źródłowy

*niezr*<br/>
Źródło X

*Kreśl*<br/>
Źródło Y

## <a name="cd2dpointfoperator-cpoint"></a><a name="operator_cpoint"></a> CD2DPointF:: operator CPoint

Konwertuje CD2DPointF na obiekt CPoint.

```
operator CPoint();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość punktu D2D.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

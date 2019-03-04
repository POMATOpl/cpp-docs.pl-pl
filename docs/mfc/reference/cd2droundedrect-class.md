---
title: Klasa CD2DRoundedRect
ms.date: 11/04/2016
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
ms.openlocfilehash: 51913a0d261a0bc91aef8f8504547a10c3e1cf36
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285844"
---
# <a name="cd2droundedrect-class"></a>Klasa CD2DRoundedRect

Otoka dla `D2D1_ROUNDED_RECT`.

## <a name="syntax"></a>Składnia

```
class CD2DRoundedRect : public D2D1_ROUNDED_RECT;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DRoundedRect::CD2DRoundedRect](#cd2droundedrect)|Przeciążone. Konstruuje `CD2DRoundedRect` obiektu z `D2D1_ROUNDED_RECT` obiektu.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`D2D1_ROUNDED_RECT`

[CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget.h

##  <a name="cd2droundedrect"></a>  CD2DRoundedRect::CD2DRoundedRect

Tworzy obiekt CD2DRoundedRect z CD2DRectF obiektu.

```
CD2DRoundedRect(
    const CD2DRectF& rectIn,
    const CD2DSizeF& sizeRadius);

CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```

### <a name="parameters"></a>Parametry

*rectIn*<br/>
prostokąta źródłowego

*sizeRadius*<br/>
rozmiar serwera RADIUS

## <a name="see-also"></a>Zobacz także

[Klasy](../../mfc/reference/mfc-classes.md)

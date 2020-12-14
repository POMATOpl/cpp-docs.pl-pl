---
description: 'Dowiedz się więcej na temat: Klasa CD2DRoundedRect'
title: Klasa CD2DRoundedRect
ms.date: 11/04/2016
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
ms.openlocfilehash: 13c1b0910c9d78f615d64e3eecba8bb813916413
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240666"
---
# <a name="cd2droundedrect-class"></a>Klasa CD2DRoundedRect

Otoka dla `D2D1_ROUNDED_RECT` .

## <a name="syntax"></a>Składnia

```
class CD2DRoundedRect : public D2D1_ROUNDED_RECT;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DRoundedRect::CD2DRoundedRect](#cd2droundedrect)|Przeciążone. Konstruuje `CD2DRoundedRect` obiekt z `D2D1_ROUNDED_RECT` obiektu.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`D2D1_ROUNDED_RECT`

[CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2droundedrectcd2droundedrect"></a><a name="cd2droundedrect"></a> CD2DRoundedRect::CD2DRoundedRect

Konstruuje obiekt CD2DRoundedRect z obiektu CD2DRectF.

```
CD2DRoundedRect(
    const CD2DRectF& rectIn,
    const CD2DSizeF& sizeRadius);

CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```

### <a name="parameters"></a>Parametry

*prostokąt w*<br/>
prostokąt źródłowy

*sizeRadius*<br/>
rozmiar usługi RADIUS

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

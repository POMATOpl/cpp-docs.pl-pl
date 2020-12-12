---
description: 'Dowiedz się więcej na temat: Klasa CD2DRectU'
title: Klasa CD2DRectU
ms.date: 11/04/2016
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
ms.openlocfilehash: dadbaf37f1ed11f96f29c7e4cf78eebf8095590d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301623"
---
# <a name="cd2drectu-class"></a>Klasa CD2DRectU

Otoka dla `D2D1_RECT_U` .

## <a name="syntax"></a>Składnia

```
class CD2DRectU : public D2D1_RECT_U;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DRectU::CD2DRectU](#cd2drectu)|Przeciążone. Konstruuje `CD2DRectU` obiekt z `D2D1_RECT_U` obiektu.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DRectU:: IsNull](#isnull)|Zwraca wartość **logiczną** wskazującą, czy wyrażenie nie zawiera prawidłowych danych (null).|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DRectU:: operator CRect](#operator_crect)|Konwertuje `CD2DRectU` na `CRect` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`D2D1_RECT_U`

`CD2DRectU`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2drectucd2drectu"></a><a name="cd2drectu"></a> CD2DRectU::CD2DRectU

Konstruuje obiekt CD2DRectU z obiektu CRect.

```
CD2DRectU(const CRect& rect);
CD2DRectU(const D2D1_RECT_U& rect);
CD2DRectU(const D2D1_RECT_U* rect);

CD2DRectU(
    UINT32 uLeft = 0,
    UINT32 uTop = 0,
    UINT32 uRight = 0,
    UINT32 uBottom = 0);
```

### <a name="parameters"></a>Parametry

*cinania*<br/>
prostokąt źródłowy

*uLeft*<br/>
lewa Współrzędna źródła

*uTop*<br/>
Górna Współrzędna źródła

*uRight*<br/>
Współrzędna prawej strony źródłowej

*uBottom*<br/>
Dolna współrzędna źródła

## <a name="cd2drectuisnull"></a><a name="isnull"></a> CD2DRectU:: IsNull

Zwraca wartość logiczną wskazującą, czy wyrażenie nie zawiera prawidłowych danych (null).

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli górny, lewy, dolny i prawy wartości są równe 0; w przeciwnym razie FALSE.

## <a name="cd2drectuoperator-crect"></a><a name="operator_crect"></a> CD2DRectU:: operator CRect

Konwertuje CD2DRectU na obiekt CRect.

```
operator CRect();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość prostokąta D2D.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

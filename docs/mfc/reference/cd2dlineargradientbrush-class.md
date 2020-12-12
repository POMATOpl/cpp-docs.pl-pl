---
description: 'Dowiedz się więcej na temat: Klasa CD2DLinearGradientBrush'
title: Klasa CD2DLinearGradientBrush
ms.date: 11/04/2016
f1_keywords:
- CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::Attach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Create
- AFXRENDERTARGET/CD2DLinearGradientBrush::Destroy
- AFXRENDERTARGET/CD2DLinearGradientBrush::Detach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Get
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_LinearGradientBrushProperties
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_pLinearGradientBrush
helpviewer_keywords:
- CD2DLinearGradientBrush [MFC], CD2DLinearGradientBrush
- CD2DLinearGradientBrush [MFC], Attach
- CD2DLinearGradientBrush [MFC], Create
- CD2DLinearGradientBrush [MFC], Destroy
- CD2DLinearGradientBrush [MFC], Detach
- CD2DLinearGradientBrush [MFC], Get
- CD2DLinearGradientBrush [MFC], GetEndPoint
- CD2DLinearGradientBrush [MFC], GetStartPoint
- CD2DLinearGradientBrush [MFC], SetEndPoint
- CD2DLinearGradientBrush [MFC], SetStartPoint
- CD2DLinearGradientBrush [MFC], m_LinearGradientBrushProperties
- CD2DLinearGradientBrush [MFC], m_pLinearGradientBrush
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
ms.openlocfilehash: b133abe796e609a44d1ebe35a6e6e969c8ee2a68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180334"
---
# <a name="cd2dlineargradientbrush-class"></a>Klasa CD2DLinearGradientBrush

Otoka dla ID2D1LinearGradientBrush.

## <a name="syntax"></a>Składnia

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|Konstruuje obiekt CD2DLinearGradientBrush.|
|[CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Destruktor. Wywołuje się, gdy obiekt pędzla gradientu liniowego D2D jest niszczony.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DLinearGradientBrush:: Attach](#attach)|Dołącza istniejący interfejs zasobów do obiektu|
|[CD2DLinearGradientBrush:: Create](#create)|Tworzy element CD2DLinearGradientBrush. (Przesłania [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLinearGradientBrush::D Estroy](#destroy)|Niszczy obiekt CD2DLinearGradientBrush. (Przesłania [CD2DGradientBrush::D Estroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DLinearGradientBrush::D etach](#detach)|Odłącza interfejs zasobów od obiektu|
|[CD2DLinearGradientBrush:: Get](#get)|Zwraca interfejs ID2D1LinearGradientBrush|
|[CD2DLinearGradientBrush:: GetEndPoint](#getendpoint)|Pobiera współrzędne końcowe gradientu liniowego|
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|Pobiera współrzędne początkowe gradientu liniowego|
|[CD2DLinearGradientBrush:: setendpoint](#setendpoint)|Ustawia końcowe współrzędne gradientu liniowego w przestrzeni współrzędnych pędzla|
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|Ustawia współrzędne początkowe gradientu liniowego w przestrzeni współrzędnych pędzla|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DLinearGradientBrush:: operator ID2D1LinearGradientBrush *](#operator_id2d1lineargradientbrush_star)|Zwraca interfejs ID2D1LinearGradientBrush|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DLinearGradientBrush:: m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|Punkty początkowe i końcowe gradientu.|
|[CD2DLinearGradientBrush:: m_pLinearGradientBrush](#m_plineargradientbrush)|Wskaźnik do elementu ID2D1LinearGradientBrush.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="_dtorcd2dlineargradientbrush"></a> CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush

Destruktor. Wywołuje się, gdy obiekt pędzla gradientu liniowego D2D jest niszczony.

```
virtual ~CD2DLinearGradientBrush();
```

## <a name="cd2dlineargradientbrushattach"></a><a name="attach"></a> CD2DLinearGradientBrush:: Attach

Dołącza istniejący interfejs zasobów do obiektu

```cpp
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>Parametry

*Źródło*<br/>
Istniejący interfejs zasobów. Nie może mieć wartości NULL

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="cd2dlineargradientbrush"></a> CD2DLinearGradientBrush::CD2DLinearGradientBrush

Konstruuje obiekt CD2DLinearGradientBrush.

```
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*gradientStops*<br/>
Wskaźnik do tablicy struktur D2D1_GRADIENT_STOP.

*gradientStopsCount*<br/>
Wartość większa lub równa 1, która określa liczbę zatrzymań gradientu w tablicy gradientStops.

*LinearGradientBrushProperties*<br/>
Punkty początkowe i końcowe gradientu.

*colorInterpolationGamma*<br/>
Miejsce, w którym jest wykonywane Interpolacja koloru między zatrzymami gradientu.

*rozszerzona*<br/>
Zachowanie gradientu poza znormalizowanym zakresem [0, 1].

*pBrushProperties*<br/>
Wskaźnik do nieprzejrzystości i transformacji pędzla.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

## <a name="cd2dlineargradientbrushcreate"></a><a name="create"></a> CD2DLinearGradientBrush:: Create

Tworzy element CD2DLinearGradientBrush.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametry

*pRenderTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dlineargradientbrushdestroy"></a><a name="destroy"></a> CD2DLinearGradientBrush::D Estroy

Niszczy obiekt CD2DLinearGradientBrush.

```
virtual void Destroy();
```

## <a name="cd2dlineargradientbrushdetach"></a><a name="detach"></a> CD2DLinearGradientBrush::D etach

Odłącza interfejs zasobów od obiektu

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu zasobu.

## <a name="cd2dlineargradientbrushget"></a><a name="get"></a> CD2DLinearGradientBrush:: Get

Zwraca interfejs ID2D1LinearGradientBrush

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1LinearGradientBrush lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dlineargradientbrushgetendpoint"></a><a name="getendpoint"></a> CD2DLinearGradientBrush:: GetEndPoint

Pobiera współrzędne końcowe gradientu liniowego

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>Wartość zwracana

Kończące się dwuwymiarowe współrzędne gradientu liniowego, w przestrzeni współrzędnych pędzla

## <a name="cd2dlineargradientbrushgetstartpoint"></a><a name="getstartpoint"></a> CD2DLinearGradientBrush::GetStartPoint

Pobiera współrzędne początkowe gradientu liniowego

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>Wartość zwracana

Początkowe współrzędne dwuwymiarowe gradientu liniowego, w przestrzeni współrzędnych pędzla

## <a name="cd2dlineargradientbrushm_lineargradientbrushproperties"></a><a name="m_lineargradientbrushproperties"></a> CD2DLinearGradientBrush:: m_LinearGradientBrushProperties

Punkty początkowe i końcowe gradientu.

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

## <a name="cd2dlineargradientbrushm_plineargradientbrush"></a><a name="m_plineargradientbrush"></a> CD2DLinearGradientBrush:: m_pLinearGradientBrush

Wskaźnik do elementu ID2D1LinearGradientBrush.

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

## <a name="cd2dlineargradientbrushoperator-id2d1lineargradientbrush"></a><a name="operator_id2d1lineargradientbrush_star"></a> CD2DLinearGradientBrush:: operator ID2D1LinearGradientBrush *

Zwraca interfejs ID2D1LinearGradientBrush

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1LinearGradientBrush lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dlineargradientbrushsetendpoint"></a><a name="setendpoint"></a> CD2DLinearGradientBrush:: setendpoint

Ustawia końcowe współrzędne gradientu liniowego w przestrzeni współrzędnych pędzla

```cpp
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>Parametry

*moment*<br/>
Kończące się dwuwymiarowe współrzędne gradientu liniowego, w przestrzeni współrzędnych pędzla

## <a name="cd2dlineargradientbrushsetstartpoint"></a><a name="setstartpoint"></a> CD2DLinearGradientBrush::SetStartPoint

Ustawia współrzędne początkowe gradientu liniowego w przestrzeni współrzędnych pędzla

```cpp
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>Parametry

*moment*<br/>
Początkowe współrzędne dwuwymiarowe gradientu liniowego, w przestrzeni współrzędnych pędzla

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

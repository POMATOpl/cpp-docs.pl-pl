---
description: 'Dowiedz się więcej na temat: Klasa CD2DRadialGradientBrush'
title: Klasa CD2DRadialGradientBrush
ms.date: 11/04/2016
f1_keywords:
- CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::Attach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Create
- AFXRENDERTARGET/CD2DRadialGradientBrush::Destroy
- AFXRENDERTARGET/CD2DRadialGradientBrush::Detach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Get
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_pRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_RadialGradientBrushProperties
helpviewer_keywords:
- CD2DRadialGradientBrush [MFC], CD2DRadialGradientBrush
- CD2DRadialGradientBrush [MFC], Attach
- CD2DRadialGradientBrush [MFC], Create
- CD2DRadialGradientBrush [MFC], Destroy
- CD2DRadialGradientBrush [MFC], Detach
- CD2DRadialGradientBrush [MFC], Get
- CD2DRadialGradientBrush [MFC], GetCenter
- CD2DRadialGradientBrush [MFC], GetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], GetRadiusX
- CD2DRadialGradientBrush [MFC], GetRadiusY
- CD2DRadialGradientBrush [MFC], SetCenter
- CD2DRadialGradientBrush [MFC], SetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], SetRadiusX
- CD2DRadialGradientBrush [MFC], SetRadiusY
- CD2DRadialGradientBrush [MFC], m_pRadialGradientBrush
- CD2DRadialGradientBrush [MFC], m_RadialGradientBrushProperties
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
ms.openlocfilehash: c5e169a5d608edd246d5c7269c94e3b225fdd491
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118748"
---
# <a name="cd2dradialgradientbrush-class"></a>Klasa CD2DRadialGradientBrush

Otoka dla ID2D1RadialGradientBrush.

## <a name="syntax"></a>Składnia

```
class CD2DRadialGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#cd2dradialgradientbrush)|Konstruuje obiekt CD2DLinearGradientBrush.|
|[CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|Destruktor. Wywołuje się, gdy obiekt pędzla gradientu promieniowego D2D jest niszczony.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DRadialGradientBrush:: Attach](#attach)|Dołącza istniejący interfejs zasobów do obiektu|
|[CD2DRadialGradientBrush:: Create](#create)|Tworzy element CD2DRadialGradientBrush. (Przesłania [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DRadialGradientBrush::D Estroy](#destroy)|Niszczy obiekt CD2DRadialGradientBrush. (Przesłania [CD2DGradientBrush::D Estroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DRadialGradientBrush::D etach](#detach)|Odłącza interfejs zasobów od obiektu|
|[CD2DRadialGradientBrush:: Get](#get)|Zwraca interfejs ID2D1RadialGradientBrush|
|[CD2DRadialGradientBrush:: getcenter](#getcenter)|Pobiera środek wielokropka gradientu|
|[CD2DRadialGradientBrush::GetGradientOriginOffset](#getgradientoriginoffset)|Pobiera przesunięcie pochodzenia gradientu względem środka elipsy gradientu|
|[CD2DRadialGradientBrush::GetRadiusX](#getradiusx)|Pobiera wartość x-RADIUS elipsy gradientowej|
|[CD2DRadialGradientBrush:: getradius](#getradiusy)|Pobiera y-promień elipsy gradientowej|
|[CD2DRadialGradientBrush:: setcenter](#setcenter)|Określa środek elipsy gradientowej w przestrzeni współrzędnych pędzla|
|[CD2DRadialGradientBrush::SetGradientOriginOffset](#setgradientoriginoffset)|Określa przesunięcie pochodzenia gradientu względem środka elipsy gradientu.|
|[CD2DRadialGradientBrush::SetRadiusX](#setradiusx)|Określa znak x-promienia elipsy gradientowej w obszarze współrzędnych pędzla.|
|[CD2DRadialGradientBrush:: setradius](#setradiusy)|Określa wartość y-promień elipsy gradientowej w obszarze współrzędnych pędzla.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DRadialGradientBrush:: operator ID2D1RadialGradientBrush *](#operator_id2d1radialgradientbrush_star)|Zwraca interfejs ID2D1RadialGradientBrush|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DRadialGradientBrush:: m_pRadialGradientBrush](#m_pradialgradientbrush)|Wskaźnik do elementu ID2D1RadialGradientBrush.|
|[CD2DRadialGradientBrush:: m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|Środek, przesunięcie źródła gradientu oraz x-RADIUS i y-promień gradientu pędzla.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DRadialGradientBrush`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="_dtorcd2dradialgradientbrush"></a> CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush

Destruktor. Wywołuje się, gdy obiekt pędzla gradientu promieniowego D2D jest niszczony.

```
virtual ~CD2DRadialGradientBrush();
```

## <a name="cd2dradialgradientbrushattach"></a><a name="attach"></a> CD2DRadialGradientBrush:: Attach

Dołącza istniejący interfejs zasobów do obiektu

```cpp
void Attach(ID2D1RadialGradientBrush* pResource);
```

### <a name="parameters"></a>Parametry

*Źródło*<br/>
Istniejący interfejs zasobów. Nie może mieć wartości NULL

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="cd2dradialgradientbrush"></a> CD2DRadialGradientBrush::CD2DRadialGradientBrush

Konstruuje obiekt CD2DLinearGradientBrush.

```
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,
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

*RadialGradientBrushProperties*<br/>
Środek, przesunięcie źródła gradientu oraz x-RADIUS i y-promień gradientu pędzla.

*colorInterpolationGamma*<br/>
Miejsce, w którym jest wykonywane Interpolacja koloru między zatrzymami gradientu.

*rozszerzona*<br/>
Zachowanie gradientu poza znormalizowanym zakresem [0, 1].

*pBrushProperties*<br/>
Wskaźnik do nieprzejrzystości i transformacji pędzla.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

## <a name="cd2dradialgradientbrushcreate"></a><a name="create"></a> CD2DRadialGradientBrush:: Create

Tworzy element CD2DRadialGradientBrush.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametry

*pRenderTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dradialgradientbrushdestroy"></a><a name="destroy"></a> CD2DRadialGradientBrush::D Estroy

Niszczy obiekt CD2DRadialGradientBrush.

```
virtual void Destroy();
```

## <a name="cd2dradialgradientbrushdetach"></a><a name="detach"></a> CD2DRadialGradientBrush::D etach

Odłącza interfejs zasobów od obiektu

```
ID2D1RadialGradientBrush* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu zasobu.

## <a name="cd2dradialgradientbrushget"></a><a name="get"></a> CD2DRadialGradientBrush:: Get

Zwraca interfejs ID2D1RadialGradientBrush

```
ID2D1RadialGradientBrush* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1RadialGradientBrush lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dradialgradientbrushgetcenter"></a><a name="getcenter"></a> CD2DRadialGradientBrush:: getcenter

Pobiera środek wielokropka gradientu

```
CD2DPointF GetCenter() const;
```

### <a name="return-value"></a>Wartość zwracana

Środek wielokropka gradientu. Ta wartość jest wyrażona w przestrzeni współrzędnych pędzla.

## <a name="cd2dradialgradientbrushgetgradientoriginoffset"></a><a name="getgradientoriginoffset"></a> CD2DRadialGradientBrush::GetGradientOriginOffset

Pobiera przesunięcie pochodzenia gradientu względem środka elipsy gradientu

```
CD2DPointF GetGradientOriginOffset() const;
```

### <a name="return-value"></a>Wartość zwracana

Przesunięcie początku gradientu od środka elipsy gradientowej. Ta wartość jest wyrażona w przestrzeni współrzędnych pędzla.

## <a name="cd2dradialgradientbrushgetradiusx"></a><a name="getradiusx"></a> CD2DRadialGradientBrush::GetRadiusX

Pobiera wartość x-RADIUS elipsy gradientowej

```
FLOAT GetRadiusX() const;
```

### <a name="return-value"></a>Wartość zwracana

X-promień elipsy gradientowej. Ta wartość jest wyrażona w przestrzeni współrzędnych pędzla.

## <a name="cd2dradialgradientbrushgetradiusy"></a><a name="getradiusy"></a> CD2DRadialGradientBrush:: getradius

Pobiera y-promień elipsy gradientowej

```
FLOAT GetRadiusY() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość y dla wielokropka gradientu. Ta wartość jest wyrażona w przestrzeni współrzędnych pędzla.

## <a name="cd2dradialgradientbrushm_pradialgradientbrush"></a><a name="m_pradialgradientbrush"></a> CD2DRadialGradientBrush:: m_pRadialGradientBrush

Wskaźnik do elementu ID2D1RadialGradientBrush.

```
ID2D1RadialGradientBrush* m_pRadialGradientBrush;
```

## <a name="cd2dradialgradientbrushm_radialgradientbrushproperties"></a><a name="m_radialgradientbrushproperties"></a> CD2DRadialGradientBrush:: m_RadialGradientBrushProperties

Środek, przesunięcie źródła gradientu oraz x-RADIUS i y-promień gradientu pędzla.

```
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;
```

## <a name="cd2dradialgradientbrushoperator-id2d1radialgradientbrush"></a><a name="operator_id2d1radialgradientbrush_star"></a> CD2DRadialGradientBrush:: operator ID2D1RadialGradientBrush *

Zwraca interfejs ID2D1RadialGradientBrush

```
operator ID2D1RadialGradientBrush*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1RadialGradientBrush lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dradialgradientbrushsetcenter"></a><a name="setcenter"></a> CD2DRadialGradientBrush:: setcenter

Określa środek elipsy gradientowej w przestrzeni współrzędnych pędzla

```cpp
void SetCenter(CD2DPointF point);
```

### <a name="parameters"></a>Parametry

*moment*<br/>
Środek elipsy gradientowej w obszarze współrzędnych pędzla.

## <a name="cd2dradialgradientbrushsetgradientoriginoffset"></a><a name="setgradientoriginoffset"></a> CD2DRadialGradientBrush::SetGradientOriginOffset

Określa przesunięcie pochodzenia gradientu względem środka elipsy gradientu.

```cpp
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```

### <a name="parameters"></a>Parametry

*gradientOriginOffset*<br/>
Przesunięcie początku gradientu od środka elipsy gradientowej.

## <a name="cd2dradialgradientbrushsetradiusx"></a><a name="setradiusx"></a> CD2DRadialGradientBrush::SetRadiusX

Określa znak x-promienia elipsy gradientowej w obszarze współrzędnych pędzla.

```cpp
void SetRadiusX(FLOAT radiusX);
```

### <a name="parameters"></a>Parametry

*radiusX*<br/>
X-promień elipsy gradientowej. Ta wartość znajduje się w przestrzeni współrzędnych pędzla

## <a name="cd2dradialgradientbrushsetradiusy"></a><a name="setradiusy"></a> CD2DRadialGradientBrush:: setradius

Określa wartość y-promień elipsy gradientowej w obszarze współrzędnych pędzla.

```cpp
void SetRadiusY(FLOAT radiusY);
```

### <a name="parameters"></a>Parametry

*promień*<br/>
Wartość y dla wielokropka gradientu. Ta wartość znajduje się w przestrzeni współrzędnych pędzla

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

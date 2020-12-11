---
description: 'Dowiedz się więcej na temat: Klasa CD2DSolidColorBrush'
title: Klasa CD2DSolidColorBrush
ms.date: 03/27/2019
f1_keywords:
- CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::Attach
- AFXRENDERTARGET/CD2DSolidColorBrush::Create
- AFXRENDERTARGET/CD2DSolidColorBrush::Destroy
- AFXRENDERTARGET/CD2DSolidColorBrush::Detach
- AFXRENDERTARGET/CD2DSolidColorBrush::Get
- AFXRENDERTARGET/CD2DSolidColorBrush::GetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::SetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::m_colorSolid
- AFXRENDERTARGET/CD2DSolidColorBrush::m_pSolidColorBrush
helpviewer_keywords:
- CD2DSolidColorBrush [MFC], CD2DSolidColorBrush
- CD2DSolidColorBrush [MFC], Attach
- CD2DSolidColorBrush [MFC], Create
- CD2DSolidColorBrush [MFC], Destroy
- CD2DSolidColorBrush [MFC], Detach
- CD2DSolidColorBrush [MFC], Get
- CD2DSolidColorBrush [MFC], GetColor
- CD2DSolidColorBrush [MFC], SetColor
- CD2DSolidColorBrush [MFC], m_colorSolid
- CD2DSolidColorBrush [MFC], m_pSolidColorBrush
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
ms.openlocfilehash: 57df3732a3c4239af6d9121426aa272c6f58417d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154607"
---
# <a name="cd2dsolidcolorbrush-class"></a>Klasa CD2DSolidColorBrush

Otoka dla ID2D1SolidColorBrush.

## <a name="syntax"></a>Składnia

```
class CD2DSolidColorBrush : public CD2DBrush;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|Przeciążone. Konstruuje obiekt CD2DSolidColorBrush.|
|[CD2DSolidColorBrush:: ~ CD2DSolidColorBrush](#_dtorcd2dsolidcolorbrush)|Destruktor. Wywołuje się, gdy obiekt D2D Solid Pędzel jest niszczony.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DSolidColorBrush:: Attach](#attach)|Dołącza istniejący interfejs zasobów do obiektu|
|[CD2DSolidColorBrush:: Create](#create)|Tworzy element CD2DSolidColorBrush. (Przesłania [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DSolidColorBrush::D Estroy](#destroy)|Niszczy obiekt CD2DSolidColorBrush. (Przesłania [CD2DBrush::D Estroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DSolidColorBrush::D etach](#detach)|Odłącza interfejs zasobów od obiektu|
|[CD2DSolidColorBrush:: Get](#get)|Zwraca interfejs ID2D1SolidColorBrush|
|[CD2DSolidColorBrush:: GetColor](#getcolor)|Pobiera kolor pełnego pędzla kolorów|
|[CD2DSolidColorBrush:: SetColor](#setcolor)|Określa kolor tego pełnego pędzla kolorów|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DSolidColorBrush:: operator ID2D1SolidColorBrush *](#operator_id2d1solidcolorbrush_star)|Zwraca interfejs ID2D1SolidColorBrush|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DSolidColorBrush:: m_colorSolid](#m_colorsolid)|Pełny kolor pędzla.|
|[CD2DSolidColorBrush:: m_pSolidColorBrush](#m_psolidcolorbrush)|Przechowuje wskaźnik do obiektu ID2D1SolidColorBrush.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="_dtorcd2dsolidcolorbrush"></a> CD2DSolidColorBrush:: ~ CD2DSolidColorBrush

Destruktor. Wywołuje się, gdy obiekt D2D Solid Pędzel jest niszczony.

```
virtual ~CD2DSolidColorBrush();
```

## <a name="cd2dsolidcolorbrushattach"></a><a name="attach"></a> CD2DSolidColorBrush:: Attach

Dołącza istniejący interfejs zasobów do obiektu

```cpp
void Attach(ID2D1SolidColorBrush* pResource);
```

### <a name="parameters"></a>Parametry

*Źródło*<br/>
Istniejący interfejs zasobów. Nie może mieć wartości NULL

## <a name="cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="cd2dsolidcolorbrush"></a> CD2DSolidColorBrush::CD2DSolidColorBrush

Konstruuje obiekt CD2DSolidColorBrush.

```
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    D2D1_COLOR_F color,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    COLORREF color,
    int nAlpha = 255,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*Kolor*<br/>
Wartości czerwony, zielony, niebieski i alfa koloru pędzla.

*pBrushProperties*<br/>
Wskaźnik do nieprzejrzystości i transformacji pędzla.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

*nAlpha*<br/>
Nieprzezroczystość koloru pędzla.

## <a name="cd2dsolidcolorbrushcreate"></a><a name="create"></a> CD2DSolidColorBrush:: Create

Tworzy element CD2DSolidColorBrush.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametry

*pRenderTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dsolidcolorbrushdestroy"></a><a name="destroy"></a> CD2DSolidColorBrush::D Estroy

Niszczy obiekt CD2DSolidColorBrush.

```
virtual void Destroy();
```

## <a name="cd2dsolidcolorbrushdetach"></a><a name="detach"></a> CD2DSolidColorBrush::D etach

Odłącza interfejs zasobów od obiektu

```
ID2D1SolidColorBrush* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu zasobu.

## <a name="cd2dsolidcolorbrushget"></a><a name="get"></a> CD2DSolidColorBrush:: Get

Zwraca interfejs ID2D1SolidColorBrush

```
ID2D1SolidColorBrush* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1SolidColorBrush lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dsolidcolorbrushgetcolor"></a><a name="getcolor"></a> CD2DSolidColorBrush:: GetColor

Pobiera kolor pełnego pędzla kolorów

```
D2D1_COLOR_F GetColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Kolor tego pełnego pędzla kolorów

## <a name="cd2dsolidcolorbrushm_colorsolid"></a><a name="m_colorsolid"></a> CD2DSolidColorBrush:: m_colorSolid

Pełny kolor pędzla.

```
D2D1_COLOR_F m_colorSolid;
```

## <a name="cd2dsolidcolorbrushm_psolidcolorbrush"></a><a name="m_psolidcolorbrush"></a> CD2DSolidColorBrush:: m_pSolidColorBrush

Przechowuje wskaźnik do obiektu ID2D1SolidColorBrush.

```
ID2D1SolidColorBrush* m_pSolidColorBrush;
```

## <a name="cd2dsolidcolorbrushoperator-id2d1solidcolorbrush"></a><a name="operator_id2d1solidcolorbrush_star"></a> CD2DSolidColorBrush:: operator ID2D1SolidColorBrush *

Zwraca interfejs ID2D1SolidColorBrush

```
operator ID2D1SolidColorBrush*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1SolidColorBrush lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dsolidcolorbrushsetcolor"></a><a name="setcolor"></a> CD2DSolidColorBrush:: SetColor

Określa kolor tego pełnego pędzla kolorów

```cpp
void SetColor(D2D1_COLOR_F color);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
Kolor tego pełnego pędzla kolorów

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

---
description: 'Dowiedz się więcej na temat: Klasa CD2DBrush'
title: Klasa CD2DBrush
ms.date: 11/04/2016
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
helpviewer_keywords:
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
ms.openlocfilehash: 6d19601258951a297a734aa304e2a22c98baf5c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227575"
---
# <a name="cd2dbrush-class"></a>Klasa CD2DBrush

Otoka dla ID2D1Brush.

## <a name="syntax"></a>Składnia

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>Elementy członkowskie

### <a name="protected-constructors"></a>Konstruktory chronione

|Nazwa|Opis|
|----------|-----------------|
|[CD2DBrush::CD2DBrush](#cd2dbrush)|Konstruuje obiekt CD2DBrush.|
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|Destruktor. Wywoływana, gdy trwa niszczenie obiektu pędzla D2D.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DBrush:: Attach](#attach)|Dołącza istniejący interfejs zasobów do obiektu|
|[CD2DBrush::D Estroy](#destroy)|Niszczy obiekt CD2DBrush. (Przesłania [CD2DResource::D Estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DBrush::D etach](#detach)|Odłącza interfejs zasobów od obiektu|
|[CD2DBrush:: Get](#get)|Zwraca interfejs ID2D1Brush|
|[CD2DBrush:: getzmętnienie](#getopacity)|Pobiera stopień przejrzystości tego pędzla|
|[CD2DBrush:: gettransform](#gettransform)|Pobiera bieżącą transformację elementu docelowego renderowania|
|[CD2DBrush:: IsValid](#isvalid)|Sprawdza poprawność zasobów (Przesłania [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)).|
|[CD2DBrush:: setzmętnienie](#setopacity)|Ustawia stopień przejrzystości tego pędzla|
|[CD2DBrush:: setTransform](#settransform)|Stosuje określone przekształcenie do elementu docelowego renderowania, zastępując istniejące przekształcenie. Wszystkie kolejne operacje rysowania są wykonywane w przekształconej przestrzeni|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DBrush:: operator ID2D1Brush *](#operator_id2d1brush_star)|Zwraca interfejs ID2D1Brush|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DBrush:: m_pBrush](#m_pbrush)|Przechowuje wskaźnik do obiektu ID2D1Brush.|
|[CD2DBrush:: m_pBrushProperties](#m_pbrushproperties)|Właściwości pędzla.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBrush`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dbrushcd2dbrush"></a><a name="_dtorcd2dbrush"></a> CD2DBrush:: ~ CD2DBrush

Destruktor. Wywoływana, gdy trwa niszczenie obiektu pędzla D2D.

```
virtual ~CD2DBrush();
```

## <a name="cd2dbrushattach"></a><a name="attach"></a> CD2DBrush:: Attach

Dołącza istniejący interfejs zasobów do obiektu.

```cpp
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>Parametry

*Źródło*<br/>
Istniejący interfejs zasobów. Nie może mieć wartości NULL.

## <a name="cd2dbrushcd2dbrush"></a><a name="cd2dbrush"></a> CD2DBrush::CD2DBrush

Konstruuje obiekt CD2DBrush.

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*pBrushProperties*<br/>
Wskaźnik do nieprzejrzystości i transformacji pędzla.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

## <a name="cd2dbrushdestroy"></a><a name="destroy"></a> CD2DBrush::D Estroy

Niszczy obiekt CD2DBrush.

```
virtual void Destroy();
```

## <a name="cd2dbrushdetach"></a><a name="detach"></a> CD2DBrush::D etach

Odłącza interfejs zasobów od obiektu.

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu zasobu.

## <a name="cd2dbrushget"></a><a name="get"></a> CD2DBrush:: Get

Zwraca interfejs ID2D1Brush

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1Brush lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dbrushgetopacity"></a><a name="getopacity"></a> CD2DBrush:: getzmętnienie

Pobiera stopień przejrzystości tego pędzla

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość z zakresu od 0 do 1, która wskazuje nieprzezroczystość pędzla. Ta wartość to stały mnożnik, który liniowo skaluje wartość alfa wszystkich pikseli wypełnionych przez pędzel. Wartości nieprzezroczystości są zamocowane w zakresie od 0 do 1, zanim zostaną pomnożone ze sobą.

## <a name="cd2dbrushgettransform"></a><a name="gettransform"></a> CD2DBrush:: gettransform

Pobiera bieżącą transformację elementu docelowego renderowania

```cpp
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>Parametry

*przekształcania*<br/>
Gdy to zwraca, zawiera bieżące przekształcenie elementu docelowego renderowania. Ten parametr jest przekazywany jako niezainicjowany.

## <a name="cd2dbrushisvalid"></a><a name="isvalid"></a> CD2DBrush:: IsValid

Sprawdza poprawność zasobów

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli zasób jest prawidłowy; w przeciwnym razie FALSE.

## <a name="cd2dbrushm_pbrush"></a><a name="m_pbrush"></a> CD2DBrush:: m_pBrush

Przechowuje wskaźnik do obiektu ID2D1Brush.

```
ID2D1Brush* m_pBrush;
```

## <a name="cd2dbrushm_pbrushproperties"></a><a name="m_pbrushproperties"></a> CD2DBrush:: m_pBrushProperties

Właściwości pędzla.

```
CD2DBrushProperties* m_pBrushProperties;
```

## <a name="cd2dbrushoperator-id2d1brush"></a><a name="operator_id2d1brush_star"></a> CD2DBrush:: operator ID2D1Brush *

Zwraca interfejs ID2D1Brush

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1Brush lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dbrushsetopacity"></a><a name="setopacity"></a> CD2DBrush:: setzmętnienie

Ustawia stopień przejrzystości tego pędzla

```cpp
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>Parametry

*spalin*<br/>
Wartość z zakresu od 0 do 1, która wskazuje nieprzezroczystość pędzla. Ta wartość to stały mnożnik, który liniowo skaluje wartość alfa wszystkich pikseli wypełnionych przez pędzel. Wartości nieprzezroczystości są zamocowane w zakresie od 0 do 1, zanim zostaną pomnożone ze sobą.

## <a name="cd2dbrushsettransform"></a><a name="settransform"></a> CD2DBrush:: setTransform

Stosuje określone przekształcenie do elementu docelowego renderowania, zastępując istniejące przekształcenie. Wszystkie kolejne operacje rysowania są wykonywane w przekształconej przestrzeni.

```cpp
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>Parametry

*przekształcania*<br/>
Transformacja, która ma zostać zastosowana do elementu docelowego renderowania

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

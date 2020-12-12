---
description: 'Dowiedz się więcej na temat: Klasa CD2DLayer'
title: Klasa CD2DLayer
ms.date: 11/04/2016
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
helpviewer_keywords:
- CD2DLayer [MFC], CD2DLayer
- CD2DLayer [MFC], Attach
- CD2DLayer [MFC], Create
- CD2DLayer [MFC], Destroy
- CD2DLayer [MFC], Detach
- CD2DLayer [MFC], Get
- CD2DLayer [MFC], GetSize
- CD2DLayer [MFC], IsValid
- CD2DLayer [MFC], m_pLayer
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
ms.openlocfilehash: bd41cd591e6422c9434cd84d20cb6e5d778410bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306953"
---
# <a name="cd2dlayer-class"></a>Klasa CD2DLayer

Otoka dla ID2D1Layer.

## <a name="syntax"></a>Składnia

```
class CD2DLayer : public CD2DResource;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DLayer::CD2DLayer](#cd2dlayer)|Konstruuje obiekt CD2DLayer.|
|[CD2DLayer:: ~ CD2DLayer](#_dtorcd2dlayer)|Destruktor. Wywołuje się, gdy obiekt warstwy D2D jest niszczony.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DLayer:: Attach](#attach)|Dołącza istniejący interfejs zasobów do obiektu|
|[CD2DLayer:: Create](#create)|Tworzy element CD2DLayer. (Przesłania [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLayer::D Estroy](#destroy)|Niszczy obiekt CD2DLayer. (Przesłania [CD2DResource::D Estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DLayer::D etach](#detach)|Odłącza interfejs zasobów od obiektu|
|[CD2DLayer:: Get](#get)|Zwraca interfejs ID2D1Layer|
|[CD2DLayer:: GetSize](#getsize)|Zwraca rozmiar elementu docelowego renderowania w pikselach niezależnych od urządzenia|
|[CD2DLayer:: IsValid](#isvalid)|Sprawdza poprawność zasobów (Przesłania [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)).|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DLayer:: operator ID2D1Layer *](#operator_id2d1layer_star)|Zwraca interfejs ID2D1Layer|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DLayer:: m_pLayer](#m_player)|Przechowuje wskaźnik do obiektu ID2D1Layer.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DLayer`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dlayercd2dlayer"></a><a name="_dtorcd2dlayer"></a> CD2DLayer:: ~ CD2DLayer

Destruktor. Wywołuje się, gdy obiekt warstwy D2D jest niszczony.

```
virtual ~CD2DLayer();
```

## <a name="cd2dlayerattach"></a><a name="attach"></a> CD2DLayer:: Attach

Dołącza istniejący interfejs zasobów do obiektu

```cpp
void Attach(ID2D1Layer* pResource);
```

### <a name="parameters"></a>Parametry

*Źródło*<br/>
Istniejący interfejs zasobów. Nie może mieć wartości NULL

## <a name="cd2dlayercd2dlayer"></a><a name="cd2dlayer"></a> CD2DLayer::CD2DLayer

Konstruuje obiekt CD2DLayer.

```
CD2DLayer(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

## <a name="cd2dlayercreate"></a><a name="create"></a> CD2DLayer:: Create

Tworzy element CD2DLayer.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametry

*pRenderTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dlayerdestroy"></a><a name="destroy"></a> CD2DLayer::D Estroy

Niszczy obiekt CD2DLayer.

```
virtual void Destroy();
```

## <a name="cd2dlayerdetach"></a><a name="detach"></a> CD2DLayer::D etach

Odłącza interfejs zasobów od obiektu

```
ID2D1Layer* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu zasobu.

## <a name="cd2dlayerget"></a><a name="get"></a> CD2DLayer:: Get

Zwraca interfejs ID2D1Layer

```
ID2D1Layer* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1Layer lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dlayergetsize"></a><a name="getsize"></a> CD2DLayer:: GetSize

Zwraca rozmiar elementu docelowego renderowania w pikselach niezależnych od urządzenia

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Bieżący rozmiar elementu docelowego renderowania w pikselach niezależnych od urządzenia

## <a name="cd2dlayerisvalid"></a><a name="isvalid"></a> CD2DLayer:: IsValid

Sprawdza poprawność zasobów

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli zasób jest prawidłowy; w przeciwnym razie FALSE.

## <a name="cd2dlayerm_player"></a><a name="m_player"></a> CD2DLayer:: m_pLayer

Przechowuje wskaźnik do obiektu ID2D1Layer.

```
ID2D1Layer* m_pLayer;
```

## <a name="cd2dlayeroperator-id2d1layer"></a><a name="operator_id2d1layer_star"></a> CD2DLayer:: operator ID2D1Layer *

Zwraca interfejs ID2D1Layer

```
operator ID2D1Layer* ();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1Layer lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

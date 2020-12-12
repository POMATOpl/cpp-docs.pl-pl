---
description: 'Dowiedz się więcej na temat: Klasa CBitmapRenderTarget'
title: Klasa CBitmapRenderTarget
ms.date: 11/04/2016
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
ms.openlocfilehash: a7987651c988dcf7fcd4c4decf4a2bd474ab8619
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122684"
---
# <a name="cbitmaprendertarget-class"></a>Klasa CBitmapRenderTarget

Otoka dla ID2D1BitmapRenderTarget.

## <a name="syntax"></a>Składnia

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|Konstruuje obiekt CBitmapRenderTarget.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CBitmapRenderTarget:: Attach](#attach)|Dołącza istniejący interfejs obiektu docelowego renderowania do obiektu|
|[CBitmapRenderTarget::D etach](#detach)|Odłącza interfejs docelowy renderowania z obiektu|
|[CBitmapRenderTarget:: getmap](#getbitmap)|Pobiera mapę bitową dla tego obiektu docelowego renderowania. Zwracana Mapa bitowa może służyć do rysowania operacji.|
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|Zwraca interfejs ID2D1BitmapRenderTarget|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CBitmapRenderTarget:: operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|Zwraca interfejs ID2D1BitmapRenderTarget|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CBitmapRenderTarget:: m_pBitmapRenderTarget](#m_pbitmaprendertarget)|Wskaźnik do obiektu ID2D1BitmapRenderTarget.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cbitmaprendertargetattach"></a><a name="attach"></a> CBitmapRenderTarget:: Attach

Dołącza istniejący interfejs obiektu docelowego renderowania do obiektu

```cpp
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametry

*pTarget*<br/>
Istniejący interfejs elementu docelowego renderowania. Nie może mieć wartości NULL

## <a name="cbitmaprendertargetcbitmaprendertarget"></a><a name="cbitmaprendertarget"></a> CBitmapRenderTarget::CBitmapRenderTarget

Konstruuje obiekt CBitmapRenderTarget.

```
CBitmapRenderTarget();
```

## <a name="cbitmaprendertargetdetach"></a><a name="detach"></a> CBitmapRenderTarget::D etach

Odłącza interfejs docelowy renderowania z obiektu

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu docelowego renderowania.

## <a name="cbitmaprendertargetgetbitmap"></a><a name="getbitmap"></a> CBitmapRenderTarget:: getmap

Pobiera mapę bitową dla tego obiektu docelowego renderowania. Zwracana Mapa bitowa może służyć do rysowania operacji.

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>Parametry

*mapy*<br/>
Gdy ta metoda zwraca, zawiera prawidłową mapę bitową dla tego obiektu docelowego renderowania. Ta mapa bitowa może służyć do rysowania operacji.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cbitmaprendertargetgetbitmaprendertarget"></a><a name="getbitmaprendertarget"></a> CBitmapRenderTarget::GetBitmapRenderTarget

Zwraca interfejs ID2D1BitmapRenderTarget

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1BitmapRenderTarget lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cbitmaprendertargetm_pbitmaprendertarget"></a><a name="m_pbitmaprendertarget"></a> CBitmapRenderTarget:: m_pBitmapRenderTarget

Wskaźnik do obiektu ID2D1BitmapRenderTarget.

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

## <a name="cbitmaprendertargetoperator-id2d1bitmaprendertarget"></a><a name="operator_id2d1bitmaprendertarget_star"></a> CBitmapRenderTarget:: operator ID2D1BitmapRenderTarget *

Zwraca interfejs ID2D1BitmapRenderTarget

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1BitmapRenderTarget lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

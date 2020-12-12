---
description: 'Dowiedz się więcej na temat: Klasa CDCRenderTarget'
title: Klasa CDCRenderTarget
ms.date: 11/04/2016
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
helpviewer_keywords:
- CDCRenderTarget [MFC], CDCRenderTarget
- CDCRenderTarget [MFC], Attach
- CDCRenderTarget [MFC], BindDC
- CDCRenderTarget [MFC], Create
- CDCRenderTarget [MFC], Detach
- CDCRenderTarget [MFC], GetDCRenderTarget
- CDCRenderTarget [MFC], m_pDCRenderTarget
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
ms.openlocfilehash: 3959321bbd6274c821b1f02be5962b23ec9dbc95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185326"
---
# <a name="cdcrendertarget-class"></a>Klasa CDCRenderTarget

Otoka dla ID2D1DCRenderTarget.

## <a name="syntax"></a>Składnia

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|Konstruuje obiekt CDCRenderTarget.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDCRenderTarget:: Attach](#attach)|Dołącza istniejący interfejs obiektu docelowego renderowania do obiektu|
|[CDCRenderTarget::BindDC](#binddc)|Tworzy powiązanie obiektu docelowego renderowania z kontekstem urządzenia, do którego wystawia polecenia rysowania|
|[CDCRenderTarget:: Create](#create)|Tworzy element CDCRenderTarget.|
|[CDCRenderTarget::D etach](#detach)|Odłącza interfejs docelowy renderowania z obiektu|
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|Zwraca interfejs ID2D1DCRenderTarget|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDCRenderTarget:: operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|Zwraca interfejs ID2D1DCRenderTarget|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CDCRenderTarget:: m_pDCRenderTarget](#m_pdcrendertarget)|Wskaźnik do obiektu ID2D1DCRenderTarget.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cdcrendertargetattach"></a><a name="attach"></a> CDCRenderTarget:: Attach

Dołącza istniejący interfejs obiektu docelowego renderowania do obiektu

```cpp
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametry

*pTarget*<br/>
Istniejący interfejs elementu docelowego renderowania. Nie może mieć wartości NULL

## <a name="cdcrendertargetbinddc"></a><a name="binddc"></a> CDCRenderTarget::BindDC

Tworzy powiązanie obiektu docelowego renderowania z kontekstem urządzenia, do którego wystawia polecenia rysowania

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>Parametry

*DC*<br/>
Kontekst urządzenia, do którego mają problemy obiekty docelowe renderowania.

*cinania*<br/>
Wymiary uchwytu do kontekstu urządzenia (używający HDC), do którego jest powiązany obiekt docelowy renderowania

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cdcrendertargetcdcrendertarget"></a><a name="cdcrendertarget"></a> CDCRenderTarget::CDCRenderTarget

Konstruuje obiekt CDCRenderTarget.

```
CDCRenderTarget();
```

## <a name="cdcrendertargetcreate"></a><a name="create"></a> CDCRenderTarget:: Create

Tworzy element CDCRenderTarget.

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>Parametry

*props*<br/>
Tryb renderowania, format pikseli, opcje komunikacji zdalnej, informacje o rozdzielczości DPI i minimalna obsługa DirectX wymagane do renderowania sprzętowego.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cdcrendertargetdetach"></a><a name="detach"></a> CDCRenderTarget::D etach

Odłącza interfejs docelowy renderowania z obiektu

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu docelowego renderowania.

## <a name="cdcrendertargetgetdcrendertarget"></a><a name="getdcrendertarget"></a> CDCRenderTarget::GetDCRenderTarget

Zwraca interfejs ID2D1DCRenderTarget

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1DCRenderTarget lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cdcrendertargetm_pdcrendertarget"></a><a name="m_pdcrendertarget"></a> CDCRenderTarget:: m_pDCRenderTarget

Wskaźnik do obiektu ID2D1DCRenderTarget.

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

## <a name="cdcrendertargetoperator-id2d1dcrendertarget"></a><a name="operator_id2d1dcrendertarget_star"></a> CDCRenderTarget:: operator ID2D1DCRenderTarget *

Zwraca interfejs ID2D1DCRenderTarget

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1DCRenderTarget lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

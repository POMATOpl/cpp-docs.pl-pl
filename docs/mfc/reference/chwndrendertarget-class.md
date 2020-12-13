---
description: 'Dowiedz się więcej na temat: Klasa CHwndRenderTarget'
title: Klasa CHwndRenderTarget
ms.date: 11/04/2016
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
helpviewer_keywords:
- CHwndRenderTarget [MFC], CHwndRenderTarget
- CHwndRenderTarget [MFC], Attach
- CHwndRenderTarget [MFC], CheckWindowState
- CHwndRenderTarget [MFC], Create
- CHwndRenderTarget [MFC], Detach
- CHwndRenderTarget [MFC], GetHwnd
- CHwndRenderTarget [MFC], GetHwndRenderTarget
- CHwndRenderTarget [MFC], ReCreate
- CHwndRenderTarget [MFC], Resize
- CHwndRenderTarget [MFC], m_pHwndRenderTarget
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
ms.openlocfilehash: 3a3058105fff5e5ac304f2cc980cd93f2bac70a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143640"
---
# <a name="chwndrendertarget-class"></a>Klasa CHwndRenderTarget

Otoka dla ID2D1HwndRenderTarget.

## <a name="syntax"></a>Składnia

```
class CHwndRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|Konstruuje obiekt CHwndRenderTarget z elementu HWND.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHwndRenderTarget:: Attach](#attach)|Dołącza istniejący interfejs obiektu docelowego renderowania do obiektu|
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Wskazuje, czy właściwość HWND skojarzona z tym obiektem docelowym renderowania to zamknięte.|
|[CHwndRenderTarget:: Create](#create)|Tworzy obiekt docelowy renderowania skojarzony z oknem|
|[CHwndRenderTarget::D etach](#detach)|Odłącza interfejs docelowy renderowania z obiektu|
|[CHwndRenderTarget:: GetHwnd](#gethwnd)|Zwraca wartość parametru HWND skojarzoną z tym obiektem docelowym renderowania.|
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|Zwraca interfejs ID2D1HwndRenderTarget.|
|[CHwndRenderTarget:: Recreate](#recreate)|Ponownie tworzy obiekt docelowy renderowania skojarzony z oknem|
|[CHwndRenderTarget:: Resize](#resize)|Zmienia rozmiar obiektu docelowego renderowania na określony rozmiar pikseli|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHwndRenderTarget:: operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|Zwraca interfejs ID2D1HwndRenderTarget.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CHwndRenderTarget:: m_pHwndRenderTarget](#m_phwndrendertarget)|Wskaźnik do obiektu ID2D1HwndRenderTarget.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="chwndrendertargetattach"></a><a name="attach"></a> CHwndRenderTarget:: Attach

Dołącza istniejący interfejs obiektu docelowego renderowania do obiektu

```cpp
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>Parametry

*pTarget*<br/>
Istniejący interfejs elementu docelowego renderowania. Nie może mieć wartości NULL

## <a name="chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a> CHwndRenderTarget::CheckWindowState

Wskazuje, czy właściwość HWND skojarzona z tym obiektem docelowym renderowania to zamknięte.

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość wskazująca, czy właściwość HWND skojarzona z tym obiektem docelowym renderowania to zamknięte.

## <a name="chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a> CHwndRenderTarget::CHwndRenderTarget

Konstruuje obiekt CHwndRenderTarget z elementu HWND.

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>Parametry

*Właściwość*<br/>
Właściwość HWND skojarzona z tym obiektem docelowym renderowania

## <a name="chwndrendertargetcreate"></a><a name="create"></a> CHwndRenderTarget:: Create

Tworzy obiekt docelowy renderowania skojarzony z oknem

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>Parametry

*Właściwość*<br/>
Właściwość HWND skojarzona z tym obiektem docelowym renderowania

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE

## <a name="chwndrendertargetdetach"></a><a name="detach"></a> CHwndRenderTarget::D etach

Odłącza interfejs docelowy renderowania z obiektu

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu docelowego renderowania.

## <a name="chwndrendertargetgethwnd"></a><a name="gethwnd"></a> CHwndRenderTarget:: GetHwnd

Zwraca wartość parametru HWND skojarzoną z tym obiektem docelowym renderowania.

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>Wartość zwracana

Właściwość HWND skojarzona z tym obiektem docelowym renderowania.

## <a name="chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a> CHwndRenderTarget::GetHwndRenderTarget

Zwraca interfejs ID2D1HwndRenderTarget.

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1HwndRenderTarget lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="chwndrendertargetm_phwndrendertarget"></a><a name="m_phwndrendertarget"></a> CHwndRenderTarget:: m_pHwndRenderTarget

Wskaźnik do obiektu ID2D1HwndRenderTarget.

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

## <a name="chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a> CHwndRenderTarget:: operator ID2D1HwndRenderTarget *

Zwraca interfejs ID2D1HwndRenderTarget.

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1HwndRenderTarget lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="chwndrendertargetrecreate"></a><a name="recreate"></a> CHwndRenderTarget:: Recreate

Ponownie tworzy obiekt docelowy renderowania skojarzony z oknem

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>Parametry

*Właściwość*<br/>
Właściwość HWND skojarzona z tym obiektem docelowym renderowania

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="chwndrendertargetresize"></a><a name="resize"></a> CHwndRenderTarget:: Resize

Zmienia rozmiar obiektu docelowego renderowania na określony rozmiar pikseli

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>Parametry

*zmienia*<br/>
Nowy rozmiar elementu docelowego renderowania w pikselach urządzenia

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

---
description: 'Dowiedz się więcej na temat: Klasa CAnimationTimerEventHandler'
title: Klasa CAnimationTimerEventHandler
ms.date: 11/04/2016
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationTimerEventHandler [MFC], CreateInstance
- CAnimationTimerEventHandler [MFC], OnPostUpdate
- CAnimationTimerEventHandler [MFC], OnPreUpdate
- CAnimationTimerEventHandler [MFC], OnRenderingTooSlow
- CAnimationTimerEventHandler [MFC], SetAnimationController
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
ms.openlocfilehash: 5d5f3e07eeb7ffe3f3bb226afd566330808303ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336758"
---
# <a name="canimationtimereventhandler-class"></a>Klasa CAnimationTimerEventHandler

Implementuje wywołanie zwrotne, które jest wywoływane przez interfejs API animacji, gdy wystąpią zdarzenia chronometrażu.

## <a name="syntax"></a>Składnia

```
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationTimerEventHandler:: CreateInstance](#createinstance)|Tworzy wystąpienie `CAnimationTimerEventHandler` wywołania zwrotnego.|
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|Obsługuje zdarzenia, które wystąpiły po zakończeniu aktualizacji animacji. (Przesłania `CUIAnimationTimerEventHandlerBase::OnPostUpdate`).|
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|Obsługuje zdarzenia, które wystąpiły przed rozpoczęciem aktualizacji animacji. (Przesłania `CUIAnimationTimerEventHandlerBase::OnPreUpdate`).|
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|Obsługuje zdarzenia, które występują, gdy szybkość renderowania klatek dla animacji spadnie poniżej minimalnej pożądanej szybkości klatek. (Przesłania `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`).|
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|Przechowuje wskaźnik do kontrolera animacji, aby skierować zdarzenia.|

## <a name="remarks"></a>Uwagi

Ta procedura obsługi zdarzeń jest tworzona i przenoszona do IUIAnimationTimer:: SetTimerEventHandler podczas wywoływania CAnimationController:: EnableAnimationTimerEventHandler.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CUIAnimationCallbackBase`

`CUIAnimationTimerEventHandlerBase`

`CAnimationTimerEventHandler`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationtimereventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationTimerEventHandler:: CreateInstance

Tworzy wystąpienie wywołania zwrotnego CAnimationTimerEventHandler.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```

### <a name="parameters"></a>Parametry

*pAnimationController*<br/>
Wskaźnik do kontrolera animacji, który będzie otrzymywał zdarzenia.

*ppTimerEventHandler*

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="canimationtimereventhandleronpostupdate"></a><a name="onpostupdate"></a> CAnimationTimerEventHandler::OnPostUpdate

Obsługuje zdarzenia, które wystąpiły po zakończeniu aktualizacji animacji.

```
IFACEMETHOD(OnPostUpdate)();
```

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL.

## <a name="canimationtimereventhandleronpreupdate"></a><a name="onpreupdate"></a> CAnimationTimerEventHandler::OnPreUpdate

Obsługuje zdarzenia, które wystąpiły przed rozpoczęciem aktualizacji animacji.

```
IFACEMETHOD(OnPreUpdate)();
```

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL.

## <a name="canimationtimereventhandleronrenderingtooslow"></a><a name="onrenderingtooslow"></a> CAnimationTimerEventHandler::OnRenderingTooSlow

Obsługuje zdarzenia, które występują, gdy szybkość renderowania klatek dla animacji spadnie poniżej minimalnej pożądanej szybkości klatek.

```
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```

### <a name="parameters"></a>Parametry

*składnika*

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL.

## <a name="canimationtimereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationTimerEventHandler::SetAnimationController

Przechowuje wskaźnik do kontrolera animacji, aby skierować zdarzenia.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametry

*pAnimationController*<br/>
Wskaźnik do kontrolera animacji, który będzie otrzymywał zdarzenia.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

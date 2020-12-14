---
description: 'Dowiedz się więcej na temat: Klasa CAnimationStoryboardEventHandler'
title: Klasa CAnimationStoryboardEventHandler
ms.date: 11/04/2016
f1_keywords:
- CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationStoryboardEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationStoryboardEventHandler [MFC], CAnimationStoryboardEventHandler
- CAnimationStoryboardEventHandler [MFC], CreateInstance
- CAnimationStoryboardEventHandler [MFC], OnStoryboardStatusChanged
- CAnimationStoryboardEventHandler [MFC], OnStoryboardUpdated
- CAnimationStoryboardEventHandler [MFC], SetAnimationController
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
ms.openlocfilehash: 7208ba91ec78a6de688699183b55a691b8e3d28d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254745"
---
# <a name="canimationstoryboardeventhandler-class"></a>Klasa CAnimationStoryboardEventHandler

Implementuje wywołanie zwrotne, które jest wywoływane przez interfejs API animacji, gdy zmieniany jest stan scenorysu lub zostanie zaktualizowany scenorys.

## <a name="syntax"></a>Składnia

```
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](#canimationstoryboardeventhandler)|Konstruuje `CAnimationStoryboardEventHandler` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationStoryboardEventHandler:: CreateInstance](#createinstance)|Tworzy wystąpienie `CAnimationStoryboardEventHandler` wywołania zwrotnego.|
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|Obsługuje `OnStoryboardStatusChanged` zdarzenia, które występują, gdy zmieni się stan scenorysu (zastąpień `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged` ).|
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](#onstoryboardupdated)|Obsługuje `OnStoryboardUpdated` zdarzenia, które pojawiają się po aktualizacji scenorysu (zastąpienia `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated` ).|
|[CAnimationStoryboardEventHandler::SetAnimationController](#setanimationcontroller)|Przechowuje wskaźnik do kontrolera animacji, aby skierować zdarzenia.|

## <a name="remarks"></a>Uwagi

Ta procedura obsługi zdarzeń jest tworzona i przenoszona do `IUIAnimationStoryboard::SetStoryboardEventHandler` metody, gdy jest wywoływana `CAnimationController::EnableStoryboardEventHandler` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CUIAnimationCallbackBase`

`CUIAnimationStoryboardEventHandlerBase`

`CAnimationStoryboardEventHandler`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationstoryboardeventhandlercanimationstoryboardeventhandler"></a><a name="canimationstoryboardeventhandler"></a> CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler

Konstruuje obiekt CAnimationStoryboardEventHandler.

```
CAnimationStoryboardEventHandler();
```

## <a name="canimationstoryboardeventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationStoryboardEventHandler:: CreateInstance

Tworzy wystąpienie wywołania zwrotnego CAnimationStoryboardEventHandler.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationStoryboardEventHandler** ppHandler);
```

### <a name="parameters"></a>Parametry

*pAnimationController*<br/>
Wskaźnik do kontrolera animacji, który będzie otrzymywał zdarzenia.

*ppHandler*

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="canimationstoryboardeventhandleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a> CAnimationStoryboardEventHandler::OnStoryboardStatusChanged

Obsługuje zdarzenia OnStoryboardStatusChanged, które występują, gdy zmienia się stan scenorysu

```
IFACEMETHOD(OnStoryboardStatusChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in UI_ANIMATION_STORYBOARD_STATUS newStatus,
    __in UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>Parametry

*scenorysu*<br/>
Wskaźnik do scenorysu, którego stan został zmieniony.

*newStatus*<br/>
Określa nowy stan scenorysu.

*previousStatus*<br/>
Określa poprzedni stan scenorysu.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL.

## <a name="canimationstoryboardeventhandleronstoryboardupdated"></a><a name="onstoryboardupdated"></a> CAnimationStoryboardEventHandler::OnStoryboardUpdated

Obsługuje zdarzenia OnStoryboardUpdated, które występują podczas aktualizowania scenorysu

```
IFACEMETHOD(OnStoryboardUpdated) (__in IUIAnimationStoryboard* storyboard);
```

### <a name="parameters"></a>Parametry

*scenorysu*<br/>
Wskaźnik do scenorysu, który został zaktualizowany.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL.

## <a name="canimationstoryboardeventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationStoryboardEventHandler::SetAnimationController

Przechowuje wskaźnik do kontrolera animacji, aby skierować zdarzenia.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametry

*pAnimationController*<br/>
Wskaźnik do kontrolera animacji, który będzie otrzymywał zdarzenia.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

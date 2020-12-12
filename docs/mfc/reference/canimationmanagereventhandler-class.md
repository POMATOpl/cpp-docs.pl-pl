---
description: 'Dowiedz się więcej na temat: Klasa CAnimationManagerEventHandler'
title: Klasa CAnimationManagerEventHandler
ms.date: 11/04/2016
f1_keywords:
- CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CAnimationManagerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::OnManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationManagerEventHandler::SetAnimationController
helpviewer_keywords:
- CAnimationManagerEventHandler [MFC], CAnimationManagerEventHandler
- CAnimationManagerEventHandler [MFC], CreateInstance
- CAnimationManagerEventHandler [MFC], OnManagerStatusChanged
- CAnimationManagerEventHandler [MFC], SetAnimationController
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
ms.openlocfilehash: aab944c23822486bbc04bb7710d257dd8c42beed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207949"
---
# <a name="canimationmanagereventhandler-class"></a>Klasa CAnimationManagerEventHandler

Implementuje wywołanie zwrotne, które jest wywoływane przez interfejs API animacji, gdy zmieni się stan Menedżera animacji.

## <a name="syntax"></a>Składnia

```
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationManagerEventHandler::CAnimationManagerEventHandler](#canimationmanagereventhandler)|Konstruuje `CAnimationManagerEventHandler` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationManagerEventHandler:: CreateInstance](#createinstance)|Tworzy wystąpienie `CAnimationManagerEventHandler` obiektu.|
|[CAnimationManagerEventHandler::OnManagerStatusChanged](#onmanagerstatuschanged)|Wywoływana, gdy zmieniono stan Menedżera animacji. (Przesłania `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`).|
|[CAnimationManagerEventHandler::SetAnimationController](#setanimationcontroller)|Przechowuje wskaźnik do kontrolera animacji, aby skierować zdarzenia.|

## <a name="remarks"></a>Uwagi

Ta procedura obsługi zdarzeń jest tworzona i przenoszona do metody IUIAnimationManager:: SetManagerEventHandler, gdy zostanie wywołana CAnimationController:: EnableAnimationManagerEvent.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CUIAnimationCallbackBase`

`CUIAnimationManagerEventHandlerBase`

`CAnimationManagerEventHandler`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationmanagereventhandlercanimationmanagereventhandler"></a><a name="canimationmanagereventhandler"></a> CAnimationManagerEventHandler::CAnimationManagerEventHandler

Wymagany jest dodatek SP1 dla programu Visual Studio 2010.

Konstruuje obiekt CAnimationManagerEventHandler.

```
CAnimationManagerEventHandler();
```

## <a name="canimationmanagereventhandlercreateinstance"></a><a name="createinstance"></a> CAnimationManagerEventHandler:: CreateInstance

Wymagany jest dodatek SP1 dla programu Visual Studio 2010.

Tworzy wystąpienie obiektu CAnimationManagerEventHandler.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationManagerEventHandler** ppManagerEventHandler);
```

### <a name="parameters"></a>Parametry

*pAnimationController*<br/>
Wskaźnik do kontrolera animacji, który będzie otrzymywał zdarzenia.

*ppManagerEventHandler*<br/>
Rozdzielczości. Jeśli metoda zakończy się pomyślnie, zawiera wskaźnik do obiektu COM, który będzie obsługiwał aktualizacje stanu do Menedżera animacji.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="canimationmanagereventhandleronmanagerstatuschanged"></a><a name="onmanagerstatuschanged"></a> CAnimationManagerEventHandler::OnManagerStatusChanged

Wymagany jest dodatek SP1 dla programu Visual Studio 2010.

Wywoływana, gdy zmieniono stan Menedżera animacji.

```
IFACEMETHOD(OnManagerStatusChanged)(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>Parametry

*newStatus*<br/>
Nowy stan.

*previousStatus*<br/>
Poprzedni stan.

### <a name="return-value"></a>Wartość zwracana

Bieżąca implementacja zawsze zwraca S_OK;

## <a name="canimationmanagereventhandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationManagerEventHandler::SetAnimationController

Wymagany jest dodatek SP1 dla programu Visual Studio 2010.

Przechowuje wskaźnik do kontrolera animacji, aby skierować zdarzenia.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametry

*pAnimationController*<br/>
Wskaźnik do kontrolera animacji, który będzie otrzymywał zdarzenia.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

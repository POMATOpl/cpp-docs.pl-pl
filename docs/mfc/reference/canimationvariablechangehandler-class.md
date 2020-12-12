---
description: 'Dowiedz się więcej na temat: Klasa CAnimationVariableChangeHandler'
title: Klasa CAnimationVariableChangeHandler
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::OnValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableChangeHandler [MFC], OnValueChanged
- CAnimationVariableChangeHandler [MFC], SetAnimationController
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
ms.openlocfilehash: 1c97bc908a29bfb7edf2222f6df117fefdaf4091
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207881"
---
# <a name="canimationvariablechangehandler-class"></a>Klasa CAnimationVariableChangeHandler

Implementuje wywołanie zwrotne, które jest wywoływane przez interfejs API animacji, gdy zmienia się wartość zmiennej animacji.

## <a name="syntax"></a>Składnia

```
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Konstruuje `CAnimationVariableChangeHandler` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CAnimationVariableChangeHandler::CreateInstance`|Tworzy wystąpienie `CAnimationVariableChangeHandler` obiektu.|
|[CAnimationVariableChangeHandler::OnValueChanged](#onvaluechanged)|Wywołuje się, gdy zmieniono wartość zmiennej animacji. (Przesłania `CUIAnimationVariableChangeHandlerBase::OnValueChanged`).|
|[CAnimationVariableChangeHandler::SetAnimationController](#setanimationcontroller)|Przechowuje wskaźnik do kontrolera animacji, aby skierować zdarzenia.|

## <a name="remarks"></a>Uwagi

Ta procedura obsługi zdarzeń jest tworzona i przenoszona do `IUIAnimationVariable::SetVariableChangeHandler` metody, gdy jest wywoływana `CAnimationVariable::EnableValueChangedEvent` lub `CAnimationBaseObject::EnableValueChangedEvent` (która włącza to zdarzenie dla wszystkich zmiennych animacji, które są hermetyzowane w obiekcie animacji).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CUIAnimationCallbackBase`

`CUIAnimationVariableChangeHandlerBase`

`CAnimationVariableChangeHandler`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationvariablechangehandleronvaluechanged"></a><a name="onvaluechanged"></a> CAnimationVariableChangeHandler::OnValueChanged

Wywołuje się, gdy zmieniono wartość zmiennej animacji.

```
IFACEMETHOD(OnValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in DOUBLE newValue,
    __in DOUBLE previousValue);
```

### <a name="parameters"></a>Parametry

*scenorysu*<br/>
Scenorys, który jest animowany dla zmiennej.

*zmiennej*<br/>
Zaktualizowana zmienna animacji.

*newValue*<br/>
Nowa wartość.

*previousValue*<br/>
Poprzednia wartość.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="canimationvariablechangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationVariableChangeHandler::SetAnimationController

Przechowuje wskaźnik do kontrolera animacji, aby skierować zdarzenia.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametry

*pAnimationController*<br/>
Wskaźnik do kontrolera animacji, który będzie otrzymywał zdarzenia.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

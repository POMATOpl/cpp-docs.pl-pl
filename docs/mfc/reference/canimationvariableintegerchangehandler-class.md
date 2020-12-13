---
description: 'Dowiedz się więcej na temat: Klasa CAnimationVariableIntegerChangeHandler'
title: Klasa CAnimationVariableIntegerChangeHandler
ms.date: 11/04/2016
f1_keywords:
- CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationVariableIntegerChangeHandler::SetAnimationController
helpviewer_keywords:
- CAnimationVariableIntegerChangeHandler [MFC], CAnimationVariableIntegerChangeHandler
- CAnimationVariableIntegerChangeHandler [MFC], CreateInstance
- CAnimationVariableIntegerChangeHandler [MFC], OnIntegerValueChanged
- CAnimationVariableIntegerChangeHandler [MFC], SetAnimationController
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
ms.openlocfilehash: 53a0a1838e021294b4ccc870e6f01b873233a0c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336727"
---
# <a name="canimationvariableintegerchangehandler-class"></a>Klasa CAnimationVariableIntegerChangeHandler

Implementuje wywołanie zwrotne, które jest wywoływane przez interfejs API animacji, gdy zmienia się wartość zmiennej animacji.

## <a name="syntax"></a>Składnia

```
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler](#canimationvariableintegerchangehandler)|Konstruuje `CAnimationVariableIntegerChangeHandler` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationVariableIntegerChangeHandler:: CreateInstance](#createinstance)|Tworzy wystąpienie `CAnimationVariableIntegerChangeHandler` wywołania zwrotnego.|
|[CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged](#onintegervaluechanged)|Wywołuje się, gdy zmieniono wartość zmiennej animacji. (Przesłania `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`).|
|[CAnimationVariableIntegerChangeHandler::SetAnimationController](#setanimationcontroller)|Przechowuje wskaźnik do kontrolera animacji, aby skierować zdarzenia.|

## <a name="remarks"></a>Uwagi

Ta procedura obsługi zdarzeń jest tworzona i przenoszona do metody IUIAnimationVariable:: SetVariableIntegerChangeHandler, gdy jest wywoływana CAnimationVariable:: EnableIntegerValueChangedEvent lub CAnimationBaseObject:: EnableIntegerValueChangedEvent (która umożliwia to zdarzenie dla wszystkich zmiennych animacji hermetyzowanych w obiekcie animacji).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[Klasy MFC](../../mfc/reference/mfc-classes.md)

`CUIAnimationCallbackBase`

`CUIAnimationVariableIntegerChangeHandlerBase`

`CAnimationVariableIntegerChangeHandler`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationvariableintegerchangehandlercanimationvariableintegerchangehandler"></a><a name="canimationvariableintegerchangehandler"></a> CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler

Konstruuje obiekt CAnimationVariableIntegerChangeHandler.

```
CAnimationVariableIntegerChangeHandler ();
```

## <a name="canimationvariableintegerchangehandlercreateinstance"></a><a name="createinstance"></a> CAnimationVariableIntegerChangeHandler:: CreateInstance

Tworzy wystąpienie wywołania zwrotnego CAnimationVariableIntegerChangeHandler.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,
    IUIAnimationVariableIntegerChangeHandler** ppHandler);
```

### <a name="parameters"></a>Parametry

*pAnimationController*<br/>
Wskaźnik do kontrolera animacji, który będzie otrzymywał zdarzenia.

*ppHandler*

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="canimationvariableintegerchangehandleronintegervaluechanged"></a><a name="onintegervaluechanged"></a> CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged

Wywołuje się, gdy zmieniono wartość zmiennej animacji.

```
IFACEMETHOD(OnIntegerValueChanged) (
    __in IUIAnimationStoryboard* storyboard,
    __in IUIAnimationVariable* variable,
    __in INT32 newValue,
    __in INT32 previousValue);
```

### <a name="parameters"></a>Parametry

*scenorysu*<br/>
Scenorys, który jest animowany dla zmiennej.

*zmiennej*<br/>
Zaktualizowana zmienna animacji.

*newValue*<br/>
Nowa wartość zaokrąglona.

*previousValue*<br/>
Poprzednia wartość zaokrąglona.

### <a name="return-value"></a>Wartość zwracana

S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL.

## <a name="canimationvariableintegerchangehandlersetanimationcontroller"></a><a name="setanimationcontroller"></a> CAnimationVariableIntegerChangeHandler::SetAnimationController

Przechowuje wskaźnik do kontrolera animacji, aby skierować zdarzenia.

```cpp
void SetAnimationController(CAnimationController* pAnimationController);
```

### <a name="parameters"></a>Parametry

*pAnimationController*<br/>
Wskaźnik do kontrolera animacji, który będzie otrzymywał zdarzenia.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

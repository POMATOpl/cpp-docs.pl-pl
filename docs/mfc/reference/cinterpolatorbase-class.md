---
description: 'Dowiedz się więcej na temat: Klasa CInterpolatorBase'
title: Klasa CInterpolatorBase
ms.date: 11/04/2016
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
helpviewer_keywords:
- CInterpolatorBase [MFC], CInterpolatorBase
- CInterpolatorBase [MFC], CreateInstance
- CInterpolatorBase [MFC], GetDependencies
- CInterpolatorBase [MFC], GetDuration
- CInterpolatorBase [MFC], GetFinalValue
- CInterpolatorBase [MFC], InterpolateValue
- CInterpolatorBase [MFC], InterpolateVelocity
- CInterpolatorBase [MFC], SetCustomInterpolator
- CInterpolatorBase [MFC], SetDuration
- CInterpolatorBase [MFC], SetInitialValueAndVelocity
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
ms.openlocfilehash: 73204e8b81db862fe30058d1b2451ea468d332e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340960"
---
# <a name="cinterpolatorbase-class"></a>Klasa CInterpolatorBase

Implementuje wywołanie zwrotne, które jest wywoływane przez interfejs API animacji, gdy musi obliczyć nową wartość zmiennej animacji.

## <a name="syntax"></a>Składnia

```
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|Konstruuje `CInterpolatorBase` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CInterpolatorBase:: CreateInstance](#createinstance)|Tworzy wystąpienie programu `CInterpolatorBase` i zapisuje wskaźnik do niestandardowego interpolowania, który będzie obsługiwał zdarzenia.|
|[CInterpolatorBase:: getzależności](#getdependencies)|Pobiera zależności interpolacji. (Przesłania `CUIAnimationInterpolatorBase::GetDependencies`).|
|[CInterpolatorBase:: GetDuration](#getduration)|Pobiera czas trwania interpolacji. (Przesłania `CUIAnimationInterpolatorBase::GetDuration`).|
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Pobiera końcową wartość, do której prowadzi ten Interpolacja. (Przesłania `CUIAnimationInterpolatorBase::GetFinalValue`).|
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Interpoluje wartość w danym przesunięciu (przesłonięcia `CUIAnimationInterpolatorBase::InterpolateValue` ).|
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Interpoluje szybkość dla danego przesunięcia (przesłonięcia `CUIAnimationInterpolatorBase::InterpolateVelocity` ).|
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|Przechowuje wskaźnik do niestandardowego interpolowania, który będzie obsługiwał zdarzenia.|
|[CInterpolatorBase:: SetDuration](#setduration)|Ustawia czas trwania interpolacji (przesłonięcia `CUIAnimationInterpolatorBase::SetDuration` ).|
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Ustawia wartość początkową i prędkość dla interpolacji. (Przesłania `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`).|

## <a name="remarks"></a>Uwagi

Ta procedura obsługi jest tworzona i przenoszona do `IUIAnimationTransitionFactory::CreateTransition` momentu `CCustomTransition` utworzenia obiektu w ramach procesu inicjowania animacji (rozpoczętego przez `CAnimationController::AnimateGroup` ). Zazwyczaj nie trzeba używać tej klasy bezpośrednio, a jedynie routs wszystkie zdarzenia do `CCustomInterpolator` klasy pochodnej, której wskaźnik jest przekazywać do konstruktora `CCustomTransition` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="cinterpolatorbasecinterpolatorbase"></a><a name="cinterpolatorbase"></a> CInterpolatorBase::CInterpolatorBase

Konstruuje obiekt CInterpolatorBase.

```
CInterpolatorBase();
```

## <a name="cinterpolatorbasecreateinstance"></a><a name="createinstance"></a> CInterpolatorBase:: CreateInstance

Tworzy wystąpienie elementu CInterpolatorBase i zapisuje wskaźnik do niestandardowego interpolowania, który będzie obsługiwał zdarzenia.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>Parametry

*pInterpolator*<br/>
Wskaźnik do niestandardowego interpolka.

*ppHandler*<br/>
Rozdzielczości. Zawiera wskaźnik do wystąpienia elementu CInterpolatorBase, gdy funkcja zwraca wartość.

### <a name="return-value"></a>Wartość zwracana

## <a name="cinterpolatorbasegetdependencies"></a><a name="getdependencies"></a> CInterpolatorBase:: getzależności

Pobiera zależności interpolacji.

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Parametry

*initialValueDependencies*<br/>
Rozdzielczości. Aspekty interpolacji, które są zależne od wartości początkowej przesłanej do SetInitialValueAndVelocity.

*initialVelocityDependencies*<br/>
Rozdzielczości. Aspekty interpolacji, które zależą od początkowej prędkości przekazaną do SetInitialValueAndVelocity.

*durationDependencies*<br/>
Rozdzielczości. Aspekty interpolacji, które zależą od czasu trwania przesłanego do SetDuration.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. Zwraca E_FAIL, Jeśli CCustomInterpolator nie jest ustawiona, lub implementacja niestandardowa zwróci wartość FALSE z metody getzależności.

## <a name="cinterpolatorbasegetduration"></a><a name="getduration"></a> CInterpolatorBase:: GetDuration

Pobiera czas trwania interpolacji.

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Parametry

*czas trwania*<br/>
Rozdzielczości. Czas trwania przejścia (w sekundach).

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. Zwraca E_FAIL, Jeśli CCustomInterpolator nie jest ustawiona, lub implementacja niestandardowa zwraca wartość FALSE z metody GetDuration.

## <a name="cinterpolatorbasegetfinalvalue"></a><a name="getfinalvalue"></a> CInterpolatorBase::GetFinalValue

Pobiera końcową wartość, do której prowadzi ten Interpolacja.

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>Parametry

*wartość*<br/>
Rozdzielczości. Końcowa wartość zmiennej na końcu przejścia.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. Zwraca E_FAIL, Jeśli CCustomInterpolator nie jest ustawiona, lub implementacja niestandardowa zwróci wartość FALSE z metody GetFinalValue.

## <a name="cinterpolatorbaseinterpolatevalue"></a><a name="interpolatevalue"></a> CInterpolatorBase::InterpolateValue

Interpoluje wartość w danym przesunięciu

```
IFACEMETHOD(InterpolateValue)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* value);
```

### <a name="parameters"></a>Parametry

*Przesunięcie*<br/>
Przesunięcie od początku przejścia. Przesunięcie jest zawsze większe lub równe zero i mniejsze niż czas trwania przejścia. Ta metoda nie jest wywoływana, jeśli czas trwania przejścia wynosi zero.

*wartość*<br/>
Rozdzielczości. Wartość interpolowana.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. Zwraca E_FAIL, Jeśli CCustomInterpolator nie jest ustawiona, lub implementacja niestandardowa zwróci wartość FALSE z metody InterpolateValue.

## <a name="cinterpolatorbaseinterpolatevelocity"></a><a name="interpolatevelocity"></a> CInterpolatorBase::InterpolateVelocity

Interpoluje szybkość dla danego przesunięcia

```
IFACEMETHOD(InterpolateVelocity)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* velocity);
```

### <a name="parameters"></a>Parametry

*Przesunięcie*<br/>
Przesunięcie od początku przejścia. Przesunięcie jest zawsze większe lub równe zeru i mniejsze lub równe czasowi trwania przejścia. Ta metoda nie jest wywoływana, jeśli czas trwania przejścia wynosi zero.

*prędkość*<br/>
Rozdzielczości. Szybkość zmiennej w przesunięciu.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. Zwraca E_FAIL, Jeśli CCustomInterpolator nie jest ustawiona, lub implementacja niestandardowa zwróci wartość FALSE z metody InterpolateVelocity.

## <a name="cinterpolatorbasesetcustominterpolator"></a><a name="setcustominterpolator"></a> CInterpolatorBase::SetCustomInterpolator

Przechowuje wskaźnik do niestandardowego interpolowania, który będzie obsługiwał zdarzenia.

```cpp
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Parametry

*pInterpolator*<br/>
Wskaźnik do niestandardowego interpolka.

## <a name="cinterpolatorbasesetduration"></a><a name="setduration"></a> CInterpolatorBase:: SetDuration

Ustawia czas trwania interpolacji

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parametry

*czas trwania*<br/>
Czas trwania przejścia.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. Zwraca E_FAIL, Jeśli CCustomInterpolator nie jest ustawiona, lub implementacja niestandardowa zwraca wartość FALSE z metody SetDuration.

## <a name="cinterpolatorbasesetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a> CInterpolatorBase::SetInitialValueAndVelocity

Ustawia wartość początkową i prędkość dla interpolacji.

```
IFACEMETHOD(SetInitialValueAndVelocity)(
    __in DOUBLE initialValue,
    __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametry

*initialValue*<br/>
Wartość zmiennej na początku przejścia.

*initialVelocity*<br/>
Szybkość zmiennej na początku przejścia.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. Zwraca E_FAIL, Jeśli CCustomInterpolator nie jest ustawiona, lub implementacja niestandardowa zwróci wartość FALSE z metody SetInitialValueAndVelocity.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

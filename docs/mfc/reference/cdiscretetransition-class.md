---
description: 'Dowiedz się więcej na temat: Klasa CDiscreteTransition'
title: Klasa CDiscreteTransition
ms.date: 11/04/2016
f1_keywords:
- CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::Create
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_delay
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_hold
helpviewer_keywords:
- CDiscreteTransition [MFC], CDiscreteTransition
- CDiscreteTransition [MFC], Create
- CDiscreteTransition [MFC], m_dblFinalValue
- CDiscreteTransition [MFC], m_delay
- CDiscreteTransition [MFC], m_hold
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
ms.openlocfilehash: 5ab2e2aa8a56236ac0354be088bc72afe5042a76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185183"
---
# <a name="cdiscretetransition-class"></a>Klasa CDiscreteTransition

Hermetyzuje dyskretne przejście.

## <a name="syntax"></a>Składnia

```
class CDiscreteTransition : public CBaseTransition;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDiscreteTransition::CDiscreteTransition](#cdiscretetransition)|Konstruuje dyskretny obiekt przejścia i inicjuje jego parametry.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDiscreteTransition:: Create](#create)|Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia. (Przesłania [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CDiscreteTransition:: m_dblFinalValue](#m_dblfinalvalue)|Wartość zmiennej animacji na końcu przejścia.|
|[CDiscreteTransition:: m_delay](#m_delay)|Czas, przez który należy opóźnić natychmiastowe przełączenie do wartości końcowej.|
|[CDiscreteTransition:: m_hold](#m_hold)|Czas przechowywania zmiennej w wartości końcowej.|

## <a name="remarks"></a>Uwagi

Podczas przejścia dyskretnego zmienna animacji pozostaje w początkowej wartości przez określony czas opóźnienia, a następnie natychmiast przełącza się do określonej wartości końcowej i pozostaje w tej wartości dla danego czasu wstrzymania. Ponieważ wszystkie przejścia są automatycznie wyczyszczone, zaleca się ich przydzielenie przy użyciu operatora new. Obiekt hermetyzowanych IUIAnimationTransition COM jest tworzony przez CAnimationController:: Animuj, do momentu, aż będzie miał wartość NULL. Zmiana zmiennych Członkowskich po utworzeniu tego obiektu COM nie ma żadnego skutku.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="cdiscretetransitioncdiscretetransition"></a><a name="cdiscretetransition"></a> CDiscreteTransition::CDiscreteTransition

Konstruuje dyskretny obiekt przejścia i inicjuje jego parametry.

```
CDiscreteTransition(
    UI_ANIMATION_SECONDS delay,
    DOUBLE dblFinalValue,
    UI_ANIMATION_SECONDS hold);
```

### <a name="parameters"></a>Parametry

*opóźnienie*<br/>
Czas, przez który należy opóźnić natychmiastowe przełączenie do wartości końcowej.

*dblFinalValue*<br/>
Wartość zmiennej animacji na końcu przejścia.

*i*<br/>
Czas przechowywania zmiennej w wartości końcowej.

## <a name="cdiscretetransitioncreate"></a><a name="create"></a> CDiscreteTransition:: Create

Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

*pLibrary*<br/>
Wskaźnik do [interfejsu IUIAnimationTransitionLibrary](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), który definiuje bibliotekę przejść standardowych.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli przejście zostało utworzone pomyślnie; w przeciwnym razie FALSE.

## <a name="cdiscretetransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a> CDiscreteTransition:: m_dblFinalValue

Wartość zmiennej animacji na końcu przejścia.

```
DOUBLE m_dblFinalValue;
```

## <a name="cdiscretetransitionm_delay"></a><a name="m_delay"></a> CDiscreteTransition:: m_delay

Czas, przez który należy opóźnić natychmiastowe przełączenie do wartości końcowej.

```
UI_ANIMATION_SECONDS m_delay;
```

## <a name="cdiscretetransitionm_hold"></a><a name="m_hold"></a> CDiscreteTransition:: m_hold

Czas przechowywania zmiennej w wartości końcowej.

```
UI_ANIMATION_SECONDS m_hold;
```

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

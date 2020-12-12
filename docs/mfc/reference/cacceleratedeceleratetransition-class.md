---
description: 'Dowiedz się więcej na temat: Klasa CAccelerateDecelerateTransition'
title: Klasa CAccelerateDecelerateTransition
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: 5981c6f57acaf2507410acbb6c792f77b96f75c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322762"
---
# <a name="cacceleratedeceleratetransition-class"></a>Klasa CAccelerateDecelerateTransition

Implementuje przejście Przyspiesz-spowalniania.

## <a name="syntax"></a>Składnia

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Konstruuje obiekt przejścia.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAccelerateDecelerateTransition:: Create](#create)|Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia. (Przesłania [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CAccelerateDecelerateTransition:: m_accelerationRatio](#m_accelerationratio)|Stosunek czasu poświęcanego na skrócenie czasu trwania.|
|[CAccelerateDecelerateTransition:: m_decelerationRatio](#m_decelerationratio)|Stosunek czasu poświęcanego na spowolnienie czasu trwania.|
|[CAccelerateDecelerateTransition:: m_duration](#m_duration)|Czas trwania przejścia.|
|[CAccelerateDecelerateTransition:: m_finalValue](#m_finalvalue)|Wartość zmiennej animacji na końcu przejścia.|

## <a name="remarks"></a>Uwagi

Podczas przejścia przyspieszenie spowalniania zmienna animacji przyspiesza działanie, a następnie spowalnia pracę w czasie trwania przejścia, kończąc na określonej wartości. Można kontrolować, jak szybko zmienna przyspiesza i chwyci niezależnie, określając różne proporcje przyspieszenia i zmniejszania. Gdy początkowa prędkość jest równa zero, współczynnik przyspieszenia jest częścią czasu, jaką zmienna będzie poświęcać na przyspieszanie; Podobnie jak współczynnik opóźnienia. Jeśli początkowa szybkość jest różna od zera, jest to ułamek czasu między prędkość osiąganą zero a końcem przejścia. Współczynnik przyspieszenia i współczynnik opóźnienia powinny być sumowane do maksymalnie 1,0. Ponieważ wszystkie przejścia są automatycznie wyczyszczone, zaleca się ich przydzielenie przy użyciu operatora new. Obiekt hermetyzowanych IUIAnimationTransition COM jest tworzony przez CAnimationController:: Animuj, do momentu, aż będzie miał wartość NULL. Zmiana zmiennych Członkowskich po utworzeniu tego obiektu COM nie ma żadnego skutku.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="cacceleratedeceleratetransitioncacceleratedeceleratetransition"></a><a name="cacceleratedeceleratetransition"></a> CAccelerateDecelerateTransition::CAccelerateDecelerateTransition

Konstruuje obiekt przejścia.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>Parametry

*czas trwania*<br/>
Czas trwania przejścia.

*finalValue*<br/>
Wartość zmiennej animacji na końcu przejścia.

*accelerationRatio*<br/>
Stosunek czasu poświęcanego na skrócenie czasu trwania.

*decelerationRatio*<br/>
Stosunek czasu poświęcanego na spowolnienie czasu trwania.

## <a name="cacceleratedeceleratetransitioncreate"></a><a name="create"></a> CAccelerateDecelerateTransition:: Create

Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>Parametry

*pLibrary*<br/>
Wskaźnik do [interfejsu IUIAnimationTransitionLibrary](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), który definiuje bibliotekę przejść standardowych.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli przejście zostało utworzone pomyślnie; w przeciwnym razie FALSE.

## <a name="cacceleratedeceleratetransitionm_accelerationratio"></a><a name="m_accelerationratio"></a> CAccelerateDecelerateTransition:: m_accelerationRatio

Stosunek czasu poświęcanego na skrócenie czasu trwania.

```
DOUBLE m_accelerationRatio;
```

## <a name="cacceleratedeceleratetransitionm_decelerationratio"></a><a name="m_decelerationratio"></a> CAccelerateDecelerateTransition:: m_decelerationRatio

Stosunek czasu poświęcanego na spowolnienie czasu trwania.

```
DOUBLE m_decelerationRatio;
```

## <a name="cacceleratedeceleratetransitionm_duration"></a><a name="m_duration"></a> CAccelerateDecelerateTransition:: m_duration

Czas trwania przejścia.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="cacceleratedeceleratetransitionm_finalvalue"></a><a name="m_finalvalue"></a> CAccelerateDecelerateTransition:: m_finalValue

Wartość zmiennej animacji na końcu przejścia.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

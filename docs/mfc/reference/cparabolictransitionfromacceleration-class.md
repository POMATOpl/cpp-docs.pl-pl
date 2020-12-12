---
description: 'Dowiedz się więcej na temat: Klasa CParabolicTransitionFromAcceleration'
title: Klasa CParabolicTransitionFromAcceleration
ms.date: 11/04/2016
f1_keywords:
- CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::Create
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalVelocity
helpviewer_keywords:
- CParabolicTransitionFromAcceleration [MFC], CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration [MFC], Create
- CParabolicTransitionFromAcceleration [MFC], m_dblAcceleration
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalValue
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalVelocity
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
ms.openlocfilehash: 037c2ff8391b655c556339547966b14ee094fee0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301493"
---
# <a name="cparabolictransitionfromacceleration-class"></a>Klasa CParabolicTransitionFromAcceleration

Hermetyzuje przejście Parabolic-Acceleration.

## <a name="syntax"></a>Składnia

```
class CParabolicTransitionFromAcceleration : public CBaseTransition;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](#cparabolictransitionfromacceleration)|Tworzy przejście Parabolic-Acceleration i inicjuje je z określonymi parametrami.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration:: Create](#create)|Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia. (Przesłania [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration:: m_dblAcceleration](#m_dblacceleration)|Przyspieszenie zmiennej animacji podczas przejścia.|
|[CParabolicTransitionFromAcceleration:: m_dblFinalValue](#m_dblfinalvalue)|Wartość zmiennej animacji na końcu przejścia.|
|[CParabolicTransitionFromAcceleration:: m_dblFinalVelocity](#m_dblfinalvelocity)|Szybkość zmiennej animacji na końcu przejścia.|

## <a name="remarks"></a>Uwagi

Podczas przejścia Parabolic-Acceleration wartość zmiennej animacji zmienia się z wartości początkowej na końcową wartość kończącą się określoną szybkością. Można kontrolować, jak szybko zmienna osiągnie wartość końcową, określając częstotliwość przyspieszenia. Ponieważ wszystkie przejścia są automatycznie wyczyszczone, zaleca się ich przydzielenie przy użyciu operatora new. Obiekt hermetyzowanych IUIAnimationTransition COM jest tworzony przez CAnimationController:: Animuj, do momentu, aż będzie miał wartość NULL. Zmiana zmiennych Członkowskich po utworzeniu tego obiektu COM nie ma żadnego skutku.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="cparabolictransitionfromaccelerationcparabolictransitionfromacceleration"></a><a name="cparabolictransitionfromacceleration"></a> CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration

Tworzy przejście Parabolic-Acceleration i inicjuje je z określonymi parametrami.

```
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,
    DOUBLE dblFinalVelocity,
    DOUBLE dblAcceleration);
```

### <a name="parameters"></a>Parametry

*dblFinalValue*<br/>
Wartość zmiennej animacji na końcu przejścia.

*dblFinalVelocity*<br/>
Szybkość zmiennej animacji na końcu przejścia.

*dblAcceleration*<br/>
Przyspieszenie zmiennej animacji podczas przejścia.

## <a name="cparabolictransitionfromaccelerationcreate"></a><a name="create"></a> CParabolicTransitionFromAcceleration:: Create

Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* /* not used */);
```

### <a name="parameters"></a>Parametry

*pLibrary*<br/>
Wskaźnik do biblioteki przejściowej, który jest odpowiedzialny za tworzenie standardowych przejść.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli przejście zostało utworzone pomyślnie; w przeciwnym razie FALSE.

## <a name="cparabolictransitionfromaccelerationm_dblacceleration"></a><a name="m_dblacceleration"></a> CParabolicTransitionFromAcceleration:: m_dblAcceleration

Przyspieszenie zmiennej animacji podczas przejścia.

```
DOUBLE m_dblAcceleration;
```

## <a name="cparabolictransitionfromaccelerationm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a> CParabolicTransitionFromAcceleration:: m_dblFinalValue

Wartość zmiennej animacji na końcu przejścia.

```
DOUBLE m_dblFinalValue;
```

## <a name="cparabolictransitionfromaccelerationm_dblfinalvelocity"></a><a name="m_dblfinalvelocity"></a> CParabolicTransitionFromAcceleration:: m_dblFinalVelocity

Szybkość zmiennej animacji na końcu przejścia.

```
DOUBLE m_dblFinalVelocity;
```

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

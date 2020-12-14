---
description: 'Dowiedz się więcej na temat: Klasa CConstantTransition'
title: Klasa CConstantTransition
ms.date: 11/04/2016
f1_keywords:
- CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::Create
- AFXANIMATIONCONTROLLER/CConstantTransition::m_duration
helpviewer_keywords:
- CConstantTransition [MFC], CConstantTransition
- CConstantTransition [MFC], Create
- CConstantTransition [MFC], m_duration
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
ms.openlocfilehash: cc4cdb6492134de3d76dcca8770636eb964281c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227835"
---
# <a name="cconstanttransition-class"></a>Klasa CConstantTransition

Hermetyzuje stałe przejście.

## <a name="syntax"></a>Składnia

```
class CConstantTransition : public CBaseTransition;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CConstantTransition::CConstantTransition](#cconstanttransition)|Konstruuje obiekt przejścia i inicjuje jego czas trwania.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CConstantTransition:: Create](#create)|Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia. (Przesłania [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CConstantTransition:: m_duration](#m_duration)|Czas trwania przejścia.|

## <a name="remarks"></a>Uwagi

Podczas stałego przejścia wartość zmiennej animacji pozostaje przy wartości początkowej w czasie trwania przejścia. Ponieważ wszystkie przejścia są automatycznie wyczyszczone, zaleca się ich przydzielenie przy użyciu operatora new. Obiekt hermetyzowanych IUIAnimationTransition COM jest tworzony przez CAnimationController:: Animuj, do momentu, aż będzie miał wartość NULL. Zmiana zmiennych Członkowskich po utworzeniu tego obiektu COM nie ma żadnego skutku.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CConstantTransition`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="cconstanttransitioncconstanttransition"></a><a name="cconstanttransition"></a> CConstantTransition::CConstantTransition

Konstruuje obiekt przejścia i inicjuje jego czas trwania.

```
CConstantTransition (UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parametry

*czas trwania*<br/>
Czas trwania przejścia.

## <a name="cconstanttransitioncreate"></a><a name="create"></a> CConstantTransition:: Create

Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametry

*pLibrary*<br/>
Wskaźnik do [interfejsu IUIAnimationTransitionLibrary](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary), który definiuje bibliotekę przejść standardowych.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli przejście zostało utworzone pomyślnie; w przeciwnym razie FALSE.

## <a name="cconstanttransitionm_duration"></a><a name="m_duration"></a> CConstantTransition:: m_duration

Czas trwania przejścia.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

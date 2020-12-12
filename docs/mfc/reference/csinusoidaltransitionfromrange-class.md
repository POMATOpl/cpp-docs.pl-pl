---
description: 'Dowiedz się więcej na temat: Klasa CSinusoidalTransitionFromRange'
title: Klasa CSinusoidalTransitionFromRange
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
helpviewer_keywords:
- CSinusoidalTransitionFromRange [MFC], CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange [MFC], Create
- CSinusoidalTransitionFromRange [MFC], m_dblMaximumValue
- CSinusoidalTransitionFromRange [MFC], m_dblMinimumValue
- CSinusoidalTransitionFromRange [MFC], m_duration
- CSinusoidalTransitionFromRange [MFC], m_period
- CSinusoidalTransitionFromRange [MFC], m_slope
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
ms.openlocfilehash: 5d00b1cbfb8fe9b76a5a69bd1c9f10316ddf8141
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264573"
---
# <a name="csinusoidaltransitionfromrange-class"></a>Klasa CSinusoidalTransitionFromRange

Hermetyzuje przejście zakresu sinusoidalną, które ma dany zakres drgań.

## <a name="syntax"></a>Składnia

```
class CSinusoidalTransitionFromRange : public CBaseTransition;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|Konstruuje obiekt przejścia.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSinusoidalTransitionFromRange:: Create](#create)|Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia. (Przesłania [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CSinusoidalTransitionFromRange:: m_dblMaximumValue](#m_dblmaximumvalue)|Wartość zmiennej animacji w szczycie sinusoidalną Wave.|
|[CSinusoidalTransitionFromRange:: m_dblMinimumValue](#m_dblminimumvalue)|Wartość zmiennej animacji w trough sinusoidalną Wave.|
|[CSinusoidalTransitionFromRange:: m_duration](#m_duration)|Czas trwania przejścia.|
|[CSinusoidalTransitionFromRange:: m_period](#m_period)|Okres drgań sinusoidalną Wave (w sekundach).|
|[CSinusoidalTransitionFromRange:: m_slope](#m_slope)|Nachylenie na początku przejścia.|

## <a name="remarks"></a>Uwagi

Wartość zmiennej animacji zmienia się między określonymi wartościami minimalnymi i maksymalnymi w całym czasie trwania przejścia zakresu sinusoidalną. Parametr nachylenie służy do rozróżniania między dwoma możliwymi Falemi sinusów określonymi przez inne parametry. Ponieważ wszystkie przejścia są automatycznie wyczyszczone, zaleca się ich przydzielenie przy użyciu operatora new. Obiekt hermetyzowanych IUIAnimationTransition COM jest tworzony przez CAnimationController:: Animuj, do momentu, aż będzie miał wartość NULL. Zmiana zmiennych Członkowskich po utworzeniu tego obiektu COM nie ma żadnego skutku.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="csinusoidaltransitionfromrangecreate"></a><a name="create"></a> CSinusoidalTransitionFromRange:: Create

Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Parametry

*pLibrary*<br/>
Wskaźnik do biblioteki przejściowej, który jest odpowiedzialny za tworzenie standardowych przejść.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli przejście zostało utworzone pomyślnie; w przeciwnym razie FALSE.

## <a name="csinusoidaltransitionfromrangecsinusoidaltransitionfromrange"></a><a name="csinusoidaltransitionfromrange"></a> CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange

Konstruuje obiekt przejścia.

```
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblMinimumValue,
    DOUBLE dblMaximumValue,
    UI_ANIMATION_SECONDS period,
    UI_ANIMATION_SLOPE slope);
```

### <a name="parameters"></a>Parametry

*czas trwania*<br/>
Czas trwania przejścia.

*dblMinimumValue*<br/>
Wartość zmiennej animacji w trough sinusoidalną Wave.

*dblMaximumValue*<br/>
Wartość zmiennej animacji w szczycie sinusoidalną Wave.

*period*<br/>
Okres drgań sinusoidalną Wave (w sekundach).

*widm*<br/>
Nachylenie na początku przejścia.

## <a name="csinusoidaltransitionfromrangem_dblmaximumvalue"></a><a name="m_dblmaximumvalue"></a> CSinusoidalTransitionFromRange:: m_dblMaximumValue

Wartość zmiennej animacji w szczycie sinusoidalną Wave.

```
DOUBLE m_dblMaximumValue;
```

## <a name="csinusoidaltransitionfromrangem_dblminimumvalue"></a><a name="m_dblminimumvalue"></a> CSinusoidalTransitionFromRange:: m_dblMinimumValue

Wartość zmiennej animacji w trough sinusoidalną Wave.

```
DOUBLE m_dblMinimumValue;
```

## <a name="csinusoidaltransitionfromrangem_duration"></a><a name="m_duration"></a> CSinusoidalTransitionFromRange:: m_duration

Czas trwania przejścia.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromrangem_period"></a><a name="m_period"></a> CSinusoidalTransitionFromRange:: m_period

Okres drgań sinusoidalną Wave (w sekundach).

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="csinusoidaltransitionfromrangem_slope"></a><a name="m_slope"></a> CSinusoidalTransitionFromRange:: m_slope

Nachylenie na początku przejścia.

```
UI_ANIMATION_SLOPE m_slope;
```

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

---
description: 'Dowiedz się więcej na temat: Klasa CCustomInterpolator'
title: Klasa CCustomInterpolator
ms.date: 11/04/2016
f1_keywords:
- CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDependencies
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetFinalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::Init
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetInitialValueAndVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_duration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_finalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialVelocity
helpviewer_keywords:
- CCustomInterpolator [MFC], CCustomInterpolator
- CCustomInterpolator [MFC], GetDependencies
- CCustomInterpolator [MFC], GetDuration
- CCustomInterpolator [MFC], GetFinalValue
- CCustomInterpolator [MFC], Init
- CCustomInterpolator [MFC], InterpolateValue
- CCustomInterpolator [MFC], InterpolateVelocity
- CCustomInterpolator [MFC], SetDuration
- CCustomInterpolator [MFC], SetInitialValueAndVelocity
- CCustomInterpolator [MFC], m_currentValue
- CCustomInterpolator [MFC], m_currentVelocity
- CCustomInterpolator [MFC], m_duration
- CCustomInterpolator [MFC], m_finalValue
- CCustomInterpolator [MFC], m_initialValue
- CCustomInterpolator [MFC], m_initialVelocity
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
ms.openlocfilehash: 84fcdc20ce1a90441a508f1469d498095980af83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227757"
---
# <a name="ccustominterpolator-class"></a>Klasa CCustomInterpolator

Implementuje podstawową interpolację.

## <a name="syntax"></a>Składnia

```
class CCustomInterpolator;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCustomInterpolator::CCustomInterpolator](#ccustominterpolator)|Przeciążone. Konstruuje niestandardowy obiekt interpolacji i inicjuje czas trwania i szybkość do określonych wartości.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCustomInterpolator:: getzależności](#getdependencies)|Pobiera zależności interpolacji.|
|[CCustomInterpolator:: GetDuration](#getduration)|Pobiera czas trwania interpolacji.|
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|Pobiera końcową wartość, do której prowadzi ten Interpolacja.|
|[CCustomInterpolator:: init](#init)|Inicjuje czas trwania i końcową wartość.|
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|Interpoluje wartość w danym przesunięciu.|
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|Interpoluje szybkość dla danego przesunięcia|
|[CCustomInterpolator:: SetDuration](#setduration)|Ustawia czas trwania interpolacji.|
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Ustawia wartość początkową i prędkość dla interpolacji.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CCustomInterpolator:: m_currentValue](#m_currentvalue)|Wartość interpolowana.|
|[CCustomInterpolator:: m_currentVelocity](#m_currentvelocity)|Prędkość interpolowana.|
|[CCustomInterpolator:: m_duration](#m_duration)|Czas trwania przejścia.|
|[CCustomInterpolator:: m_finalValue](#m_finalvalue)|Końcowa wartość zmiennej na końcu przejścia.|
|[CCustomInterpolator:: m_initialValue](#m_initialvalue)|Wartość zmiennej na początku przejścia.|
|[CCustomInterpolator:: m_initialVelocity](#m_initialvelocity)|Szybkość zmiennej na początku przejścia.|

## <a name="remarks"></a>Uwagi

Utwórz klasę z CCustomInterpolator i Zastąp wszystkie niezbędne metody w celu zaimplementowania niestandardowego algorytmu interpolacji. Wskaźnik do tej klasy powinien być przesłany jako parametr do CCustomTransition.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CCustomInterpolator`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="ccustominterpolatorccustominterpolator"></a><a name="ccustominterpolator"></a> CCustomInterpolator::CCustomInterpolator

Konstruuje niestandardowy obiekt interpolacji i ustawia wszystkie wartości domyślne 0.

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Parametry

*czas trwania*<br/>
Czas trwania przejścia.

*finalValue*

### <a name="remarks"></a>Uwagi

Użyj CCustomInterpolator:: init, aby zainicjować czas trwania i wartość końcową później w kodzie.

## <a name="ccustominterpolatorgetdependencies"></a><a name="getdependencies"></a> CCustomInterpolator:: getzależności

Pobiera zależności interpolacji.

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Parametry

*initialValueDependencies*<br/>
Rozdzielczości. Aspekty interpolacji, które są zależne od wartości początkowej przesłanej do SetInitialValueAndVelocity.

*initialVelocityDependencies*<br/>
Rozdzielczości. Aspekty interpolacji, które zależą od początkowej prędkości przekazaną do SetInitialValueAndVelocity.

*durationDependencies*<br/>
Rozdzielczości. Aspekty interpolacji, które zależą od czasu trwania przesłanego do SetDuration.

### <a name="return-value"></a>Wartość zwracana

Implementacja podstawowa zawsze zwraca wartość TRUE. Zwróć wartość FALSE z przesłoniętej implementacji, jeśli chcesz, aby zdarzenie zostało zakończone niepowodzeniem.

## <a name="ccustominterpolatorgetduration"></a><a name="getduration"></a> CCustomInterpolator:: GetDuration

Pobiera czas trwania interpolacji.

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Parametry

*czas trwania*<br/>
Rozdzielczości. Czas trwania przejścia (w sekundach).

### <a name="return-value"></a>Wartość zwracana

Implementacja podstawowa zawsze zwraca wartość TRUE. Zwróć wartość FALSE z przesłoniętej implementacji, jeśli chcesz, aby zdarzenie zostało zakończone niepowodzeniem.

## <a name="ccustominterpolatorgetfinalvalue"></a><a name="getfinalvalue"></a> CCustomInterpolator::GetFinalValue

Pobiera końcową wartość, do której prowadzi ten Interpolacja.

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>Parametry

*wartość*<br/>
Rozdzielczości. Końcowa wartość zmiennej na końcu przejścia.

### <a name="return-value"></a>Wartość zwracana

Implementacja podstawowa zawsze zwraca wartość TRUE. Zwróć wartość FALSE z przesłoniętej implementacji, jeśli chcesz, aby zdarzenie zostało zakończone niepowodzeniem.

## <a name="ccustominterpolatorinit"></a><a name="init"></a> CCustomInterpolator:: init

Inicjuje czas trwania i końcową wartość.

```cpp
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Parametry

*czas trwania*<br/>
Czas trwania przejścia.

*finalValue*<br/>
Końcowa wartość zmiennej na końcu przejścia.

## <a name="ccustominterpolatorinterpolatevalue"></a><a name="interpolatevalue"></a> CCustomInterpolator::InterpolateValue

Interpoluje wartość w danym przesunięciu.

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>Parametry

*wartość*<br/>
Rozdzielczości. Wartość interpolowana.

### <a name="return-value"></a>Wartość zwracana

Implementacja podstawowa zawsze zwraca wartość TRUE. Zwróć wartość FALSE z przesłoniętej implementacji, jeśli chcesz, aby zdarzenie zostało zakończone niepowodzeniem.

## <a name="ccustominterpolatorinterpolatevelocity"></a><a name="interpolatevelocity"></a> CCustomInterpolator::InterpolateVelocity

Interpoluje szybkość dla danego przesunięcia

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>Parametry

*prędkość*<br/>
Rozdzielczości. Szybkość zmiennej w przesunięciu.

### <a name="return-value"></a>Wartość zwracana

Implementacja podstawowa zawsze zwraca wartość TRUE. Zwróć wartość FALSE z przesłoniętej implementacji, jeśli chcesz, aby zdarzenie zostało zakończone niepowodzeniem.

## <a name="ccustominterpolatorm_currentvalue"></a><a name="m_currentvalue"></a> CCustomInterpolator:: m_currentValue

Wartość interpolowana.

```
DOUBLE m_currentValue;
```

## <a name="ccustominterpolatorm_currentvelocity"></a><a name="m_currentvelocity"></a> CCustomInterpolator:: m_currentVelocity

Prędkość interpolowana.

```
DOUBLE m_currentVelocity;
```

## <a name="ccustominterpolatorm_duration"></a><a name="m_duration"></a> CCustomInterpolator:: m_duration

Czas trwania przejścia.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="ccustominterpolatorm_finalvalue"></a><a name="m_finalvalue"></a> CCustomInterpolator:: m_finalValue

Końcowa wartość zmiennej na końcu przejścia.

```
DOUBLE m_finalValue;
```

## <a name="ccustominterpolatorm_initialvalue"></a><a name="m_initialvalue"></a> CCustomInterpolator:: m_initialValue

Wartość zmiennej na początku przejścia.

```
DOUBLE m_initialValue;
```

## <a name="ccustominterpolatorm_initialvelocity"></a><a name="m_initialvelocity"></a> CCustomInterpolator:: m_initialVelocity

Szybkość zmiennej na początku przejścia.

```
DOUBLE m_initialVelocity;
```

## <a name="ccustominterpolatorsetduration"></a><a name="setduration"></a> CCustomInterpolator:: SetDuration

Ustawia czas trwania interpolacji.

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parametry

*czas trwania*<br/>
Czas trwania przejścia.

### <a name="return-value"></a>Wartość zwracana

Implementacja podstawowa zawsze zwraca wartość TRUE. Zwróć wartość FALSE z przesłoniętej implementacji, jeśli chcesz, aby zdarzenie zostało zakończone niepowodzeniem.

## <a name="ccustominterpolatorsetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a> CCustomInterpolator::SetInitialValueAndVelocity

Ustawia wartość początkową i prędkość dla interpolacji.

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametry

*initialValue*<br/>
Wartość zmiennej na początku przejścia.

*initialVelocity*<br/>
Szybkość zmiennej na początku przejścia.

### <a name="return-value"></a>Wartość zwracana

Podstawowa implementacja zawsze zwraca wartość TRUE. Zwróć wartość FALSE z przesłoniętej implementacji, jeśli chcesz, aby zdarzenie zostało zakończone niepowodzeniem.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

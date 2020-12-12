---
description: 'Dowiedz się więcej na temat: Klasa CCustomTransition'
title: Klasa CCustomTransition
ms.date: 11/04/2016
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
helpviewer_keywords:
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
ms.openlocfilehash: 22c08cdcedc3a7cbdbe824ac1d98d62cfe810772
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227666"
---
# <a name="ccustomtransition-class"></a>Klasa CCustomTransition

Implementuje niestandardowe przejście.

## <a name="syntax"></a>Składnia

```
class CCustomTransition : public CBaseTransition;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCustomTransition::CCustomTransition](#ccustomtransition)|Konstruuje obiekt niestandardowego przejścia.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCustomTransition:: Create](#create)|Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia. (Przesłania [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|
|[CCustomTransition::SetInitialValue](#setinitialvalue)|Ustawia wartość początkową, która zostanie zastosowana do zmiennej animacji skojarzonej z tym przejściem.|
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|Ustawia początkową prędkość, która zostanie zastosowana do zmiennej animacji skojarzonej z tym przejściem.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CCustomTransition:: m_bInitialValueSpecified](#m_binitialvaluespecified)|Określa, czy wartość początkowa została określona za pomocą SetInitialValue.|
|[CCustomTransition:: m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|Określa, czy początkowa prędkość została określona za pomocą SetInitialVelocity.|
|[CCustomTransition:: m_initialValue](#m_initialvalue)|Przechowuje wartość początkową.|
|[CCustomTransition:: m_initialVelocity](#m_initialvelocity)|Przechowuje początkową szybkość.|
|[CCustomTransition:: m_pInterpolator](#m_pinterpolator)|Przechowuje wskaźnik do niestandardowego Interpolu.|

## <a name="remarks"></a>Uwagi

Klasa CCustomTransitions umożliwia deweloperom implementowanie niestandardowych przejść. Jest on tworzony i używany jako przechodzenie standardowe, ale jego Konstruktor akceptuje jako wskaźnik do niestandardowego interpolka. Wykonaj następujące kroki, aby użyć przejść niestandardowych: 1. Utwórz klasę z CCustomInterpolator i Implementuj co najmniej InterpolateValue metodę. 2. Upewnij się, że okres istnienia niestandardowego obiektu interpolacji musi być dłuższy niż czas trwania animacji, w którym jest używana. 3. Utworzenie wystąpienia (użycie operatora new) obiektu CCustomTransition i przekazanie wskaźnika do interpolacji niestandardowej w konstruktorze. 4. Call CCustomTransition:: SetInitialValue i CCustomTransition:: SetInitialVelocity, jeśli te parametry są wymagane do interpolacji niestandardowej. 5. Przekaż wskaźnik do przejścia niestandardowego do metody AddTransition obiektu animacji, której wartość powinna być animowana przy użyciu algorytmu niestandardowego. 6. Gdy wartość obiektu animacji powinna zmienić interfejs API animacji systemu Windows, wywoła InterpolateValue (i inne odpowiednie metody) w CCustomInterpolator.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="ccustomtransitionccustomtransition"></a><a name="ccustomtransition"></a> CCustomTransition::CCustomTransition

Konstruuje obiekt niestandardowego przejścia.

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Parametry

*pInterpolator*<br/>
Wskaźnik do niestandardowego interpolka.

## <a name="ccustomtransitioncreate"></a><a name="create"></a> CCustomTransition:: Create

Wywołuje bibliotekę przejściową w celu utworzenia hermetyzowanego obiektu COM przejścia.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,
    IUIAnimationTransitionFactory* pFactory);
```

### <a name="parameters"></a>Parametry

*pFactory*<br/>
Wskaźnik do fabryki przejścia, który jest odpowiedzialny za tworzenie niestandardowych przejść.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Ta metoda może również ustawiać wartość początkową i prędkość początkową, która ma zostać zastosowana do zmiennej animacji, która jest skojarzona z tym przejściem. W tym celu należy wywołać SetInitialValue i SetInitialVelocity przed utworzeniem hermetyzowanego obiektu COM przejścia (w przypadku wywołania CAnimationController:: Animuj model).

## <a name="ccustomtransitionm_binitialvaluespecified"></a><a name="m_binitialvaluespecified"></a> CCustomTransition:: m_bInitialValueSpecified

Określa, czy wartość początkowa została określona za pomocą SetInitialValue.

```
BOOL m_bInitialValueSpecified;
```

## <a name="ccustomtransitionm_binitialvelocityspecified"></a><a name="m_binitialvelocityspecified"></a> CCustomTransition:: m_bInitialVelocitySpecified

Określa, czy początkowa prędkość została określona za pomocą SetInitialVelocity.

```
BOOL m_bInitialVelocitySpecified;
```

## <a name="ccustomtransitionm_initialvalue"></a><a name="m_initialvalue"></a> CCustomTransition:: m_initialValue

Przechowuje wartość początkową.

```
DOUBLE m_initialValue;
```

## <a name="ccustomtransitionm_initialvelocity"></a><a name="m_initialvelocity"></a> CCustomTransition:: m_initialVelocity

Przechowuje początkową szybkość.

```
DOUBLE m_initialVelocity;
```

## <a name="ccustomtransitionm_pinterpolator"></a><a name="m_pinterpolator"></a> CCustomTransition:: m_pInterpolator

Przechowuje wskaźnik do niestandardowego Interpolu.

```
CCustomInterpolator* m_pInterpolator;
```

## <a name="ccustomtransitionsetinitialvalue"></a><a name="setinitialvalue"></a> CCustomTransition::SetInitialValue

Ustawia wartość początkową, która zostanie zastosowana do zmiennej animacji skojarzonej z tym przejściem.

```cpp
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>Parametry

*initialValue*

## <a name="ccustomtransitionsetinitialvelocity"></a><a name="setinitialvelocity"></a> CCustomTransition::SetInitialVelocity

Ustawia początkową prędkość, która zostanie zastosowana do zmiennej animacji skojarzonej z tym przejściem.

```cpp
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parametry

*initialVelocity*

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

---
description: 'Dowiedz się więcej na temat: Klasa CBaseTransition'
title: Klasa CBaseTransition
ms.date: 03/27/2019
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
helpviewer_keywords:
- CBaseTransition [MFC], CBaseTransition
- CBaseTransition [MFC], AddToStoryboard
- CBaseTransition [MFC], AddToStoryboardAtKeyframes
- CBaseTransition [MFC], Clear
- CBaseTransition [MFC], Create
- CBaseTransition [MFC], GetEndKeyframe
- CBaseTransition [MFC], GetRelatedVariable
- CBaseTransition [MFC], GetStartKeyframe
- CBaseTransition [MFC], GetTransition
- CBaseTransition [MFC], GetType
- CBaseTransition [MFC], IsAdded
- CBaseTransition [MFC], SetKeyframes
- CBaseTransition [MFC], SetRelatedVariable
- CBaseTransition [MFC], m_bAdded
- CBaseTransition [MFC], m_pEndKeyframe
- CBaseTransition [MFC], m_pRelatedVariable
- CBaseTransition [MFC], m_pStartKeyframe
- CBaseTransition [MFC], m_transition
- CBaseTransition [MFC], m_type
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
ms.openlocfilehash: 16a7b5e7f88e292fd2b771c627f7169c70fec2c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122827"
---
# <a name="cbasetransition-class"></a>Klasa CBaseTransition

Reprezentuje przejście podstawowe.

## <a name="syntax"></a>Składnia

```
class CBaseTransition : public CObject;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-enumerations"></a>Wyliczenia publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CBaseTransition:: TRANSITION_TYPE, Wyliczenie](#transition_type_enumeration)|Definiuje typy przejść aktualnie obsługiwane przez implementację MFC interfejsu API animacji systemu Windows.|

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CBaseTransition::CBaseTransition](#cbasetransition)|Tworzy obiekt przejścia podstawowego.|
|[CBaseTransition:: ~ CBaseTransition](#_dtorcbasetransition)|Destruktor. Wywoływana, gdy trwa niszczenie obiektu przejścia.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|Dodaje przejście do scenorysu.|
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Dodaje przejście do scenorysu.|
|[CBaseTransition:: Clear](#clear)|Wydawanie obiektu COM IUIAnimationTransition hermetyzowane.|
|[CBaseTransition:: Create](#create)|Tworzy przejście COM.|
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|Zwraca początkową klatkę kluczową.|
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|Zwraca wskaźnik do pokrewnej zmiennej.|
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|Zwraca początkową klatkę kluczową.|
|[CBaseTransition:: gettransition](#gettransition)|Przeciążone. Zwraca wskaźnik do bazowego obiektu przejścia COM.|
|[CBaseTransition:: GetType](#gettype)|Zwraca typ przejścia.|
|[CBaseTransition:: isdodał](#isadded)|Wskazuje, czy przejście zostało dodane do scenorysu.|
|[CBaseTransition:: setklatek kluczowych](#setkeyframes)|Ustawia klatki kluczowe dla przejścia.|
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|Ustanawia relację między zmienną animacji i przejściem.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CBaseTransition:: m_bAdded](#m_badded)|Określa, czy przejście zostało dodane do scenorysu.|
|[CBaseTransition:: m_pEndKeyframe](#m_pendkeyframe)|Przechowuje wskaźnik do klatki kluczowej, która określa koniec przejścia.|
|[CBaseTransition:: m_pRelatedVariable](#m_prelatedvariable)|Wskaźnik do zmiennej animacji, animowany przy użyciu przejścia przechowywanego w m_transition.|
|[CBaseTransition:: m_pStartKeyframe](#m_pstartkeyframe)|Przechowuje wskaźnik do klatki kluczowej, która określa początek przejścia.|
|[CBaseTransition:: m_transition](#m_transition)|Przechowuje wskaźnik do IUIAnimationTransition. Wartość NULL, jeśli obiekt przejścia COM nie został utworzony.|
|[CBaseTransition:: m_type](#m_type)|Przechowuje typ przejścia.|

## <a name="remarks"></a>Uwagi

Ta klasa hermetyzuje interfejs IUIAnimationTransition i służy jako klasa bazowa dla wszystkich przejść.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="cbasetransitioncbasetransition"></a><a name="_dtorcbasetransition"></a> CBaseTransition:: ~ CBaseTransition

Destruktor. Wywoływana, gdy trwa niszczenie obiektu przejścia.

```
virtual ~CBaseTransition();
```

## <a name="cbasetransitionaddtostoryboard"></a><a name="addtostoryboard"></a> CBaseTransition::AddToStoryboard

Dodaje przejście do scenorysu.

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parametry

*pStoryboard*<br/>
Wskaźnik do scenorysu, który będzie animować powiązaną zmienną.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli przejście zostało pomyślnie dodane do scenorysu.

### <a name="remarks"></a>Uwagi

Stosuje przejście do powiązanej zmiennej w scenorysie. Jeśli jest to pierwsze przejście zastosowane do tej zmiennej w tym scenorysie, przejście rozpocznie się na początku scenorysu. W przeciwnym razie przejście jest dołączane do dodawanego ostatnio przejścia do zmiennej.

## <a name="cbasetransitionaddtostoryboardatkeyframes"></a><a name="addtostoryboardatkeyframes"></a> CBaseTransition::AddToStoryboardAtKeyframes

Dodaje przejście do scenorysu.

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Parametry

*pStoryboard*<br/>
Wskaźnik do scenorysu, który będzie animować powiązaną zmienną.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli przejście zostało pomyślnie dodane do scenorysu.

### <a name="remarks"></a>Uwagi

Stosuje przejście do powiązanej zmiennej w scenorysie. Jeśli początkowa klatka kluczowa została określona, przejście rozpoczyna się od tej klatki kluczowej. Jeśli została określona końcowa klatka kluczowa, przejście rozpoczyna się od początkowej klatki kluczowej i zatrzyma się w końcowej klatce kluczowej. Jeśli przejście zostało utworzone z określonym parametrem Duration, ten czas jest zastępowany przez czas między klatkami początkowymi i końcowymi. Jeśli żadna klatka kluczowa nie została określona, przejście jest dołączane do dodanego ostatniego przejścia do zmiennej.

## <a name="cbasetransitioncbasetransition"></a><a name="cbasetransition"></a> CBaseTransition::CBaseTransition

Tworzy obiekt przejścia podstawowego.

```
CBaseTransition();
```

## <a name="cbasetransitionclear"></a><a name="clear"></a> CBaseTransition:: Clear

Wydawanie obiektu COM IUIAnimationTransition hermetyzowane.

```cpp
void Clear();
```

### <a name="remarks"></a>Uwagi

Ta metoda powinna być wywoływana z metody tworzenia klasy pochodnej, aby zapobiec wyciekowi interfejsu IUITransition.

## <a name="cbasetransitioncreate"></a><a name="create"></a> CBaseTransition:: Create

Tworzy przejście COM.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>Parametry

*pLibrary*<br/>
Wskaźnik do biblioteki przejściowej, który tworzy standardowe przejścia. W przypadku przejść niestandardowych może ona mieć wartość NULL.

*pFactory*<br/>
Wskaźnik do fabryki przejścia, która tworzy przejścia niestandardowe. Dla przejść standardowych może być wartością NULL.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli obiekt obiektu COM przejścia został pomyślnie utworzony; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Jest to czysta funkcja wirtualna, która musi zostać przesłonięta w klasie pochodnej. Jest on wywoływany przez platformę w celu utworzenia wystąpienia bazowego obiektu przejścia COM.

## <a name="cbasetransitiongetendkeyframe"></a><a name="getendkeyframe"></a> CBaseTransition::GetEndKeyframe

Zwraca początkową klatkę kluczową.

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>Wartość zwracana

Prawidłowy wskaźnik do klatki kluczowej lub wartość NULL, jeśli nie należy wstawiać przejścia między ramkami.

### <a name="remarks"></a>Uwagi

Ta metoda może służyć do uzyskiwania dostępu do obiektu klatki kluczowej, który został wcześniej ustawiony przez setklatek kluczowych. Jest on wywoływany przez kod najwyższego poziomu, gdy przejścia są dodawane do scenorysu.

## <a name="cbasetransitiongetrelatedvariable"></a><a name="getrelatedvariable"></a> CBaseTransition::GetRelatedVariable

Zwraca wskaźnik do pokrewnej zmiennej.

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>Wartość zwracana

Prawidłowy wskaźnik do zmiennej animacji lub wartość NULL, jeśli zmienna animacji nie została ustawiona przez SetRelatedVariable.

### <a name="remarks"></a>Uwagi

Jest to metoda dostępu do powiązanej zmiennej animacji.

## <a name="cbasetransitiongetstartkeyframe"></a><a name="getstartkeyframe"></a> CBaseTransition::GetStartKeyframe

Zwraca początkową klatkę kluczową.

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>Wartość zwracana

Prawidłowy wskaźnik do klatki kluczowej lub wartość NULL, jeśli przejście nie powinno się rozpoczynać po klatce kluczowej.

### <a name="remarks"></a>Uwagi

Ta metoda może służyć do uzyskiwania dostępu do obiektu klatki kluczowej, który został wcześniej ustawiony przez setklatek kluczowych. Jest on wywoływany przez kod najwyższego poziomu, gdy przejścia są dodawane do scenorysu.

## <a name="cbasetransitiongettransition"></a><a name="gettransition"></a> CBaseTransition:: gettransition

Zwraca wskaźnik do bazowego obiektu przejścia COM.

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>Parametry

*pLibrary*<br/>
Wskaźnik do biblioteki przejściowej, który tworzy standardowe przejścia. W przypadku przejść niestandardowych może ona mieć wartość NULL.

*pFactory*<br/>
Wskaźnik do fabryki przejścia, która tworzy przejścia niestandardowe. Dla przejść standardowych może być wartością NULL.

### <a name="return-value"></a>Wartość zwracana

Prawidłowy wskaźnik do IUIAnimationTransition lub NULL, jeśli nie można utworzyć podstawowego przejścia.

### <a name="remarks"></a>Uwagi

Ta metoda zwraca wskaźnik do bazowego obiektu przejścia COM i tworzy go w razie potrzeby.

## <a name="cbasetransitiongettype"></a><a name="gettype"></a> CBaseTransition:: GetType

Zwraca typ przejścia.

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>Wartość zwracana

Jedną z TRANSITION_TYPE wyliczonych wartości.

### <a name="remarks"></a>Uwagi

Ta metoda może służyć do identyfikowania obiektu przejścia według jego typu. Typ jest ustawiany w konstruktorze w klasie pochodnej.

## <a name="cbasetransitionisadded"></a><a name="isadded"></a> CBaseTransition:: isdodał

Wskazuje, czy przejście zostało dodane do scenorysu.

```
BOOL IsAdded();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli przejście zostało dodane do scenorysu, w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta flaga jest ustawiana wewnętrznie, gdy kod najwyższego poziomu dodaje przejścia do scenorysu.

## <a name="cbasetransitionm_badded"></a><a name="m_badded"></a> CBaseTransition:: m_bAdded

Określa, czy przejście zostało dodane do scenorysu.

```
BOOL m_bAdded;
```

## <a name="cbasetransitionm_pendkeyframe"></a><a name="m_pendkeyframe"></a> CBaseTransition:: m_pEndKeyframe

Przechowuje wskaźnik do klatki kluczowej, która określa koniec przejścia.

```
CBaseKeyFrame* m_pEndKeyframe;
```

## <a name="cbasetransitionm_prelatedvariable"></a><a name="m_prelatedvariable"></a> CBaseTransition:: m_pRelatedVariable

Wskaźnik do zmiennej animacji, animowany przy użyciu przejścia przechowywanego w m_transition.

```
CAnimationVariable* m_pRelatedVariable;
```

## <a name="cbasetransitionm_pstartkeyframe"></a><a name="m_pstartkeyframe"></a> CBaseTransition:: m_pStartKeyframe

Przechowuje wskaźnik do klatki kluczowej, która określa początek przejścia.

```
CBaseKeyFrame* m_pStartKeyframe;
```

## <a name="cbasetransitionm_transition"></a><a name="m_transition"></a> CBaseTransition:: m_transition

Przechowuje wskaźnik do IUIAnimationTransition. Wartość NULL, jeśli obiekt przejścia COM nie został utworzony.

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

## <a name="cbasetransitionm_type"></a><a name="m_type"></a> CBaseTransition:: m_type

Przechowuje typ przejścia.

```
TRANSITION_TYPE m_type;
```

## <a name="cbasetransitionsetkeyframes"></a><a name="setkeyframes"></a> CBaseTransition:: setklatek kluczowych

Ustawia klatki kluczowe dla przejścia.

```cpp
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>Parametry

*pStart*<br/>
Klatka kluczowa, która określa początek przejścia.

*Ustawić*<br/>
Klatka kluczowa, która określa koniec przejścia.

### <a name="remarks"></a>Uwagi

Ta metoda określa, że przejście ma zostać rozpoczęte po określonej klatce kluczowej i, opcjonalnie, jeśli wartość oczekująca nie ma wartości NULL, kończy się przed określoną klatką kluczową. Jeśli przejście zostało utworzone z określonym parametrem Duration, ten czas jest zastępowany przez czas między klatkami początkowymi i końcowymi.

## <a name="cbasetransitionsetrelatedvariable"></a><a name="setrelatedvariable"></a> CBaseTransition::SetRelatedVariable

Ustanawia relację między zmienną animacji i przejściem.

```cpp
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametry

*pVariable*<br/>
Wskaźnik do powiązanej zmiennej animacji.

### <a name="remarks"></a>Uwagi

Ustanawia relację między zmienną animacji i przejściem. Przejście można zastosować tylko do jednej zmiennej.

## <a name="cbasetransitiontransition_type-enumeration"></a><a name="transition_type_enumeration"></a> CBaseTransition:: TRANSITION_TYPE, Wyliczenie

Definiuje typy przejść aktualnie obsługiwane przez implementację MFC interfejsu API animacji systemu Windows.

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>Uwagi

Typ przejścia jest ustawiany w konstruktorze określonego przejścia. Na przykład CSinusoidalTransitionFromRange ustawia swój typ na SINUSOIDAL_FROM_RANGE.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

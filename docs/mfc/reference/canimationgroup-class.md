---
description: 'Dowiedz się więcej na temat: Klasa CAnimationGroup'
title: Klasa CAnimationGroup
ms.date: 03/27/2019
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
helpviewer_keywords:
- CAnimationGroup [MFC], CAnimationGroup
- CAnimationGroup [MFC], Animate
- CAnimationGroup [MFC], ApplyTransitions
- CAnimationGroup [MFC], FindAnimationObject
- CAnimationGroup [MFC], GetGroupID
- CAnimationGroup [MFC], RemoveKeyframes
- CAnimationGroup [MFC], RemoveTransitions
- CAnimationGroup [MFC], Schedule
- CAnimationGroup [MFC], SetAutodestroyTransitions
- CAnimationGroup [MFC], AddKeyframes
- CAnimationGroup [MFC], AddTransitions
- CAnimationGroup [MFC], CreateTransitions
- CAnimationGroup [MFC], m_bAutoclearTransitions
- CAnimationGroup [MFC], m_bAutodestroyAnimationObjects
- CAnimationGroup [MFC], m_bAutodestroyKeyframes
- CAnimationGroup [MFC], m_lstAnimationObjects
- CAnimationGroup [MFC], m_lstKeyFrames
- CAnimationGroup [MFC], m_pStoryboard
- CAnimationGroup [MFC], m_nGroupID
- CAnimationGroup [MFC], m_pParentController
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
ms.openlocfilehash: 45fd49b95f73811f52795b87bf3de2dd004fa5ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336798"
---
# <a name="canimationgroup-class"></a>Klasa CAnimationGroup

Implementuje grupę animacji, która łączy scenorys animacji, obiekty animacji i przejścia w celu zdefiniowania animacji.

## <a name="syntax"></a>Składnia

```
class CAnimationGroup;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationGroup::CAnimationGroup](#canimationgroup)|Tworzy grupę animacji.|
|[CAnimationGroup:: ~ CAnimationGroup](#_dtorcanimationgroup)|Destruktor. Wywoływana, gdy trwa niszczenie grupy animacji.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationGroup:: Animuj](#animate)|Animuj grupę.|
|[CAnimationGroup::ApplyTransitions](#applytransitions)|Stosuje przejścia do obiektów animacji.|
|[CAnimationGroup::FindAnimationObject](#findanimationobject)|Znajduje obiekt animacji zawierający określoną zmienną animacji.|
|[CAnimationGroup::GetGroupID](#getgroupid)|Zwraca identyfikator grupy.|
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|Usuwa i opcjonalnie niszczy wszystkie ramki kluczowe należące do grupy animacji.|
|[CAnimationGroup::RemoveTransitions](#removetransitions)|Usuwa przejścia z obiektów animacji należących do grupy animacji.|
|[CAnimationGroup:: Schedule](#schedule)|Planuje animację w określonym czasie.|
|[CAnimationGroup::SetAutodestroyTransitions](#setautodestroytransitions)|Kieruje wszystkie obiekty animacji należące do grupy automatycznie niszczy przejścia.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationGroup:: Add— klatki kluczowe](#addkeyframes)|Pomocnik, który dodaje klatki kluczowe do scenorysu.|
|[CAnimationGroup:: addtransitions](#addtransitions)|Pomocnik, który dodaje przejścia do scenorysu.|
|[CAnimationGroup:: settransitions](#createtransitions)|Pomocnik, który tworzy obiekty przejścia COM.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationGroup:: m_bAutoclearTransitions](#m_bautocleartransitions)|Określa, jak wyczyścić przejścia z obiektów animacji należących do grupy. Jeśli ten element członkowski ma wartość TRUE, przejścia są usuwane automatycznie po zaplanowaniu animacji. W przeciwnym razie musisz ręcznie usunąć przejścia.|
|[CAnimationGroup:: m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|Określa sposób niszczenia obiektów animacji. Jeśli ten parametr ma wartość TRUE, obiekty animacji zostaną zniszczone automatycznie, gdy grupa zostanie zniszczona. Obiekty animacji w przeciwnym razie muszą zostać zniszczone ręcznie. Wartość domyślna to FALSE. Ustaw tę wartość na TRUE tylko wtedy, gdy wszystkie obiekty animacji należące do grupy są przydzielane dynamicznie z operatorem new.|
|[CAnimationGroup:: m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Określa sposób niszczenia klatek kluczowych. Jeśli ta wartość jest RÓWNa TRUE, wszystkie ramki kluczowe są usuwane i niszczone. w przeciwnym razie są one usuwane tylko z listy. Wartość domyślna to TRUE.|
|[CAnimationGroup:: m_lstAnimationObjects](#m_lstanimationobjects)|Zawiera listę obiektów animacji.|
|[CAnimationGroup:: m_lstKeyFrames](#m_lstkeyframes)|Zawiera listę klatek kluczowych.|
|[CAnimationGroup:: m_pStoryboard](#m_pstoryboard)|Wskazuje scenorys animacji. Ten wskaźnik jest prawidłowy tylko po wywołaniu animacji.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationGroup:: m_nGroupID](#m_ngroupid)|Unikatowy identyfikator grupy animacji.|
|[CAnimationGroup:: m_pParentController](#m_pparentcontroller)|Wskaźnik do kontrolera animacji, do którego należy ta grupa.|

## <a name="remarks"></a>Uwagi

Grupy animacji są tworzone automatycznie przez kontroler animacji (CAnimationController) podczas dodawania obiektów animacji przy użyciu CAnimationController:: AddAnimationObject. Grupa animacji jest identyfikowana przez identyfikator GroupID, który zazwyczaj jest traktowany jako parametr do manipulowania grupami animacji. Identyfikator GroupID jest pobierany z pierwszego obiektu animacji dodawanego do nowej grupy animacji. W przypadku wywołania elementu CAnimationController:: animować i dostępu do niego można uzyskać dostęp za pośrednictwem publicznej m_pStoryboard członkowskich.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CAnimationGroup`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationgroupcanimationgroup"></a><a name="_dtorcanimationgroup"></a> CAnimationGroup:: ~ CAnimationGroup

Destruktor. Wywoływana, gdy trwa niszczenie grupy animacji.

```
~CAnimationGroup();
```

## <a name="canimationgroupaddkeyframes"></a><a name="addkeyframes"></a> CAnimationGroup:: Add— klatki kluczowe

Pomocnik, który dodaje klatki kluczowe do scenorysu.

```cpp
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>Parametry

*pStoryboard*<br/>
Wskaźnik do obiektu COM scenorysu.

*bAddDeep*<br/>
Określa, czy ta metoda powinna zostać dodana do klatek kluczowych scenorysu, które są zależne od innych klatek kluczowych.

## <a name="canimationgroupaddtransitions"></a><a name="addtransitions"></a> CAnimationGroup:: addtransitions

Pomocnik, który dodaje przejścia do scenorysu.

```cpp
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametry

*pStoryboard*<br/>
Wskaźnik do obiektu COM scenorysu.

*bDependOnKeyframes*

## <a name="canimationgroupanimate"></a><a name="animate"></a> CAnimationGroup:: Animuj

Animuj grupę.

```
BOOL Animate(
    IUIAnimationManager* pManager,
    IUIAnimationTimer* pTimer,
    BOOL bScheduleNow);
```

### <a name="parameters"></a>Parametry

*pManager*<br/>
*pTimer* 
 *bScheduleNow*

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli metoda się powiedzie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda tworzy wewnętrzny scenorys, tworzy i stosuje przejścia i planuje animację, jeśli bScheduleNow ma wartość TRUE. Jeśli bScheduleNow ma wartość FALSE, należy wywołać harmonogram, aby rozpocząć animację o określonej godzinie.

## <a name="canimationgroupapplytransitions"></a><a name="applytransitions"></a> CAnimationGroup::ApplyTransitions

Stosuje przejścia do obiektów animacji.

```cpp
void ApplyTransitions();
```

### <a name="remarks"></a>Uwagi

Ta metoda potwierdza tryb debugowania, jeśli scenorys nie został utworzony. Najpierw tworzy wszystkie przejścia, a następnie dodaje "static" klatek kluczowych (klatek kluczowych, które są zależne od przesunięć), dodaje przejścia, które nie zależą od klatek kluczowych, dodaje ramki kluczowe w zależności od przejść i innych klatek kluczowych, a przy ostatnim dodaje przejścia, które są zależne od klatek kluczowych.

## <a name="canimationgroupcanimationgroup"></a><a name="canimationgroup"></a> CAnimationGroup::CAnimationGroup

Tworzy grupę animacji.

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>Parametry

*pParentController*<br/>
Wskaźnik do kontrolera animacji, który tworzy grupę.

*nGroupID*<br/>
Określa identyfikator grupy.

## <a name="canimationgroupcreatetransitions"></a><a name="createtransitions"></a> CAnimationGroup:: settransitions

Pomocnik, który tworzy obiekty przejścia COM.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE oznacza, że metoda się powiedzie, w przeciwnym razie FALSE.

## <a name="canimationgroupfindanimationobject"></a><a name="findanimationobject"></a> CAnimationGroup::FindAnimationObject

Znajduje obiekt animacji zawierający określoną zmienną animacji.

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametry

*pVariable*<br/>
Wskaźnik do zmiennej animacji.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu animacji lub wartość NULL, jeśli obiekt animacji nie zostanie znaleziony.

## <a name="canimationgroupgetgroupid"></a><a name="getgroupid"></a> CAnimationGroup::GetGroupID

Zwraca identyfikator grupy.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator grupy.

## <a name="canimationgroupm_bautocleartransitions"></a><a name="m_bautocleartransitions"></a> CAnimationGroup:: m_bAutoclearTransitions

Określa, jak wyczyścić przejścia z obiektów animacji należących do grupy. Jeśli ten element członkowski ma wartość TRUE, przejścia są usuwane automatycznie po zaplanowaniu animacji. W przeciwnym razie musisz ręcznie usunąć przejścia.

```
BOOL m_bAutoclearTransitions;
```

## <a name="canimationgroupm_bautodestroyanimationobjects"></a><a name="m_bautodestroyanimationobjects"></a> CAnimationGroup:: m_bAutodestroyAnimationObjects

Określa sposób niszczenia obiektów animacji. Jeśli ten parametr ma wartość TRUE, obiekty animacji zostaną zniszczone automatycznie, gdy grupa zostanie zniszczona. Obiekty animacji w przeciwnym razie muszą zostać zniszczone ręcznie. Wartość domyślna to FALSE. Ustaw tę wartość na TRUE tylko wtedy, gdy wszystkie obiekty animacji należące do grupy są przydzielane dynamicznie z operatorem new.

```
BOOL m_bAutodestroyAnimationObjects;
```

## <a name="canimationgroupm_bautodestroykeyframes"></a><a name="m_bautodestroykeyframes"></a> CAnimationGroup:: m_bAutodestroyKeyframes

Określa sposób niszczenia klatek kluczowych. Jeśli ta wartość jest RÓWNa TRUE, wszystkie ramki kluczowe są usuwane i niszczone. w przeciwnym razie są one usuwane tylko z listy. Wartość domyślna to TRUE.

```
BOOL m_bAutodestroyKeyframes;
```

## <a name="canimationgroupm_lstanimationobjects"></a><a name="m_lstanimationobjects"></a> CAnimationGroup:: m_lstAnimationObjects

Zawiera listę obiektów animacji.

```
CObList m_lstAnimationObjects;
```

## <a name="canimationgroupm_lstkeyframes"></a><a name="m_lstkeyframes"></a> CAnimationGroup:: m_lstKeyFrames

Zawiera listę klatek kluczowych.

```
CObList m_lstKeyFrames;
```

## <a name="canimationgroupm_ngroupid"></a><a name="m_ngroupid"></a> CAnimationGroup:: m_nGroupID

Unikatowy identyfikator grupy animacji.

```
UINT32 m_nGroupID;
```

## <a name="canimationgroupm_pparentcontroller"></a><a name="m_pparentcontroller"></a> CAnimationGroup:: m_pParentController

Wskaźnik do kontrolera animacji, do którego należy ta grupa.

```
CAnimationController* m_pParentController;
```

## <a name="canimationgroupm_pstoryboard"></a><a name="m_pstoryboard"></a> CAnimationGroup:: m_pStoryboard

Wskazuje scenorys animacji. Ten wskaźnik jest prawidłowy tylko po wywołaniu animacji.

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

## <a name="canimationgroupremovekeyframes"></a><a name="removekeyframes"></a> CAnimationGroup::RemoveKeyframes

Usuwa i opcjonalnie niszczy wszystkie ramki kluczowe należące do grupy animacji.

```cpp
void RemoveKeyframes();
```

### <a name="remarks"></a>Uwagi

Jeśli element członkowski m_bAutodestroyKeyframes ma wartość TRUE, ramki kluczowe są usuwane i niszczone. w przeciwnym razie ramki kluczowe są usuwane z wewnętrznej listy klatek kluczowych.

## <a name="canimationgroupremovetransitions"></a><a name="removetransitions"></a> CAnimationGroup::RemoveTransitions

Usuwa przejścia z obiektów animacji należących do grupy animacji.

```cpp
void RemoveTransitions();
```

### <a name="remarks"></a>Uwagi

Jeśli flaga m_bAutoclearTransitions ma wartość TRUE, ta metoda pętli wszystkie obiekty animacji należące do grupy i wywołuje CAnimationObject:: ClearTransitions (FALSE).

## <a name="canimationgroupschedule"></a><a name="schedule"></a> CAnimationGroup:: Schedule

Planuje animację w określonym czasie.

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>Parametry

*pTimer*<br/>
Wskaźnik do czasomierza animacji.

*pierwszym*<br/>
Określa czas, aby zaplanować animację.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli metoda się powiedzie; Wartość FALSE, jeśli metoda nie powiedzie się lub jeśli nie wywołano animacji z bScheduleNow ustawioną na wartość FALSE.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby zaplanować animację w określonym czasie. Należy najpierw wywołać animację z bScheduleNowm ustawionym na wartość FALSE.

## <a name="canimationgroupsetautodestroytransitions"></a><a name="setautodestroytransitions"></a> CAnimationGroup::SetAutodestroyTransitions

Kieruje wszystkie obiekty animacji należące do grupy automatycznie niszczy przejścia.

```cpp
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*bAutoDestroy*<br/>
Określa sposób niszczenia przejść.

### <a name="remarks"></a>Uwagi

Ustaw tę wartość na FALSE tylko w przypadku przydzielenia przejść na stosie. Wartość domyślna to TRUE, dlatego zdecydowanie zaleca się przydzielenie obiektów przejścia przy użyciu operatora new.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

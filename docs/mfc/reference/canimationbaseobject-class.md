---
description: 'Dowiedz się więcej na temat: Klasa CAnimationBaseObject'
title: Klasa CAnimationBaseObject
ms.date: 03/27/2019
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
helpviewer_keywords:
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
ms.openlocfilehash: bc44d0e55b409f66648007eeb27fefd386640d9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318666"
---
# <a name="canimationbaseobject-class"></a>Klasa CAnimationBaseObject

Klasa bazowa dla wszystkich obiektów animacji.

## <a name="syntax"></a>Składnia

```
class CAnimationBaseObject : public CObject;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|Przeciążone. Konstruuje obiekt animacji.|
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#_dtorcanimationbaseobject)|Destruktor. Wywoływana, gdy trwa niszczenie obiektu animacji.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|Dodaje przejścia do scenorysu z zmienną animacji hermetyzowanej.|
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|Usuwa wszystkie powiązane przejścia.|
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|Określa, czy obiekt animacji zawiera konkretną zmienną animacji.|
|[CAnimationBaseObject:: settransitions](#createtransitions)|Tworzy przejścia skojarzone z obiektem animacji.|
|[CAnimationBaseObject::D etachFromController](#detachfromcontroller)|Odłącza obiekt animacji od nadrzędnego kontrolera animacji.|
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Konfiguruje procedurę obsługi zdarzeń zmiany wartości całkowitej.|
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Konfiguruje procedurę obsługi zdarzeń zmienionych wartości.|
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|Informuje, czy powiązane przejścia są niszczone automatycznie.|
|[CAnimationBaseObject::GetGroupID](#getgroupid)|Zwraca bieżący identyfikator grupy.|
|[CAnimationBaseObject:: getobjectid](#getobjectid)|Zwraca bieżący identyfikator obiektu.|
|[CAnimationBaseObject:: GetUserData](#getuserdata)|Zwraca dane zdefiniowane przez użytkownika.|
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|Ustawia flagę, aby automatycznie zniszczyć przejścia.|
|[CAnimationBaseObject::SetID](#setid)|Ustawia nowe identyfikatory.|
|[CAnimationBaseObject:: SetUserData](#setuserdata)|Ustawia dane zdefiniowane przez użytkownika.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|Zbiera wskaźniki do zawartych zmiennych animacji.|
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Ustanawia relację między zmiennymi animacji, zawartymi w obiekcie animacji i ich kontenera.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationBaseObject:: m_bAutodestroyTransitions](#m_bautodestroytransitions)|Określa, czy powiązane przejścia powinny zostać automatycznie zniszczone.|
|[CAnimationBaseObject:: m_dwUserData](#m_dwuserdata)|Przechowuje dane zdefiniowane przez użytkownika.|
|[CAnimationBaseObject:: m_nGroupID](#m_ngroupid)|Określa identyfikator grupy obiektu animacji.|
|[CAnimationBaseObject:: m_nObjectID](#m_nobjectid)|Określa identyfikator obiektu obiektu animacji.|
|[CAnimationBaseObject:: m_pParentController](#m_pparentcontroller)|Wskaźnik do nadrzędnego kontrolera animacji.|

## <a name="remarks"></a>Uwagi

Ta klasa implementuje podstawowe metody dla wszystkich obiektów animacji. Obiekt animacji może reprezentować wartość, punkt, rozmiar, prostokąt lub kolor w aplikacji, a także dowolną jednostkę niestandardową. Obiekty animacji są przechowywane w grupach animacji (zobacz CAnimationGroup). Każdą grupę można animować osobno i może być traktowana jako analogowa z scenorysu. Obiekt animacji hermetyzuje co najmniej jedną zmienną animacji (zobacz CAnimationVariable), w zależności od jej logicznej reprezentacji. Na przykład CAnimationRect zawiera cztery zmienne animacji — jedną zmienną dla każdej krawędzi prostokąta. Każda klasa obiektu animacji uwidacznia przeciążoną metodę AddTransition, która powinna być używana do zastosowania przejść do zmiennych animacji hermetyzowanych. Obiekt animacji może być identyfikowany przez identyfikator obiektu (opcjonalnie) i według identyfikatora grupy. Identyfikator grupy jest wymagany w celu umieszczenia obiektu animacji w celu poprawienia grupy, ale jeśli nie zostanie określony identyfikator grupy, obiekt zostanie umieszczony w grupie domyślnej o IDENTYFIKATORze 0. Jeśli wywołasz SetID z innym identyfikatorem GroupID, obiekt animacji zostanie przeniesiony do innej grupy (w razie potrzeby zostanie utworzona nowa grupa).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="_dtorcanimationbaseobject"></a> CAnimationBaseObject:: ~ CAnimationBaseObject

Destruktor. Wywoływana, gdy trwa niszczenie obiektu animacji.

```
virtual ~CAnimationBaseObject();
```

## <a name="canimationbaseobjectapplytransitions"></a><a name="applytransitions"></a> CAnimationBaseObject::ApplyTransitions

Dodaje przejścia do scenorysu z zmienną animacji hermetyzowanej.

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Parametry

*pStoryboard*<br/>
Wskaźnik do scenorysu.

*bDependOnKeyframes*<br/>
W przypadku wartości FALSE ta metoda dodaje tylko te przejścia, które nie zależą od klatek kluczowych.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli przejścia zostały pomyślnie dodane.

### <a name="remarks"></a>Uwagi

Dodaje powiązane przejścia, które zostały dodane za pomocą AddTransition (przeciążone metody w klasach pochodnych) do scenorysu.

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="canimationbaseobject"></a> CAnimationBaseObject::CAnimationBaseObject

Konstruuje obiekt animacji.

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametry

*nGroupID*<br/>
Określa identyfikator grupy.

*nObjectID*<br/>
Określa identyfikator obiektu.

*dwUserData*<br/>
Dane zdefiniowane przez użytkownika, które można skojarzyć z obiektem animacji i pobrane później w czasie wykonywania.

### <a name="remarks"></a>Uwagi

Konstruuje obiekty animacji i przypisuje domyślny identyfikator obiektu (0) i identyfikator grupy (0).

## <a name="canimationbaseobjectcleartransitions"></a><a name="cleartransitions"></a> CAnimationBaseObject::ClearTransitions

Usuwa wszystkie powiązane przejścia.

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Parametry

*bAutodestroy*<br/>
Określa, czy obiekty przejścia mają być niszczyne automatycznie, czy po prostu usuń je z listy powiązanej.

### <a name="remarks"></a>Uwagi

Usuwa wszystkie powiązane przejścia i niszczy je, jeśli flaga bAutodestroy lub m_bAutodestroyTransitions ma wartość TRUE. Przejścia powinny być niszczone automatycznie tylko wtedy, gdy nie są przydzieleni na stosie. Jeśli powyższe flagi są fałszywe, przejścia są usuwane z wewnętrznej listy powiązanych przejść.

## <a name="canimationbaseobjectcontainsvariable"></a><a name="containsvariable"></a> CAnimationBaseObject::ContainsVariable

Określa, czy obiekt animacji zawiera konkretną zmienną animacji.

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Parametry

*pVariable*<br/>
Wskaźnik do zmiennej animacji.

### <a name="return-value"></a>Wartość zwracana

TRUE, jeśli zmienna animacji jest zawarta w obiekcie animacji; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda może służyć do określenia, czy zmienna animacji określona przez pVariable jest zawarta w obiekcie animacji. Obiekt animacji, w zależności od jego typu, może zawierać kilka zmiennych animacji. Na przykład CAnimationColor zawiera trzy zmienne: jeden dla każdego składnika koloru (czerwony, zielony i niebieski). Gdy wartość zmiennej animacji została zmieniona, interfejs API animacji systemu Windows wysyła zdarzenia ValueChanged lub IntegerValueChanged (jeśli są włączone), a parametr tego zdarzenia jest wskaźnikiem do IUIAnimationVariable zmiennej animacji. Ta metoda pomaga uzyskać wskaźnik do animacji ze wskaźnika do zawartego obiektu COM.

## <a name="canimationbaseobjectcreatetransitions"></a><a name="createtransitions"></a> CAnimationBaseObject:: settransitions

Tworzy przejścia skojarzone z obiektem animacji.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli pomyślnie utworzono przejścia; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Pętle nad listą zmiennych animacji, które są hermetyzowane w pochodnym obiekcie animacji i tworzą przejścia skojarzone z poszczególnymi zmiennymi animacji.

## <a name="canimationbaseobjectdetachfromcontroller"></a><a name="detachfromcontroller"></a> CAnimationBaseObject::D etachFromController

Odłącza obiekt animacji od nadrzędnego kontrolera animacji.

```cpp
void DetachFromController();
```

### <a name="remarks"></a>Uwagi

Ta metoda jest używana wewnętrznie.

## <a name="canimationbaseobjectenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a> CAnimationBaseObject::EnableIntegerValueChangedEvent

Konfiguruje procedurę obsługi zdarzeń zmiany wartości całkowitej.

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametry

*pController*<br/>
Wskaźnik do kontrolera nadrzędnego.

*bEnable*<br/>
Określa, czy należy włączyć lub wyłączyć zdarzenie zmiany wartości całkowitej.

### <a name="remarks"></a>Uwagi

Jeśli włączono obsługę zdarzeń w postaci liczby całkowitej, można obsłużyć to zdarzenie w metodzie CAnimationController:: OnAnimationIntegerValueChanged, która powinna zostać przesłonięta w klasie pochodnej CAnimationController. Ta metoda jest wywoływana za każdym razem, gdy wartość całkowita animacji została zmieniona.

## <a name="canimationbaseobjectenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a> CAnimationBaseObject::EnableValueChangedEvent

Konfiguruje procedurę obsługi zdarzeń zmienionych wartości.

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Parametry

*pController*<br/>
Wskaźnik do kontrolera nadrzędnego.

*bEnable*<br/>
Określa, czy należy włączyć lub wyłączyć zdarzenie zmiany wartości.

### <a name="remarks"></a>Uwagi

W przypadku włączenia obsługi zdarzeń zmiana wartości można obsłużyć to zdarzenie w metodzie CAnimationController:: OnAnimationValueChanged, która powinna zostać przesłonięta w klasie pochodnej CAnimationController. Ta metoda jest wywoływana za każdym razem, gdy wartość animacji została zmieniona.

## <a name="canimationbaseobjectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationBaseObject::GetAnimationVariableList

Zbiera wskaźniki do zawartych zmiennych animacji.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& list) = 0;
```

### <a name="parameters"></a>Parametry

*list*<br/>
Lista, która musi być wypełniona zmiennymi animacji zawartymi w obiekcie animacji.

### <a name="remarks"></a>Uwagi

Ta czysta metoda wirtualna musi zostać przesłonięta w klasie pochodnej. Obiekt animacji, w zależności od jego typu, zawiera co najmniej jedną zmienną animacji. Na przykład CAnimationPoint zawiera dwie zmienne, odpowiednio dla współrzędnych X i Y. Klasa bazowa CAnimationBaseObject implementuje niektóre metody ogólne, które działają na liście zmiennych animacji: ApplyTransitions, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Metody te wywołują GetAnimationVariableList, która jest wypełniona klasą pochodną z rzeczywistymi zmiennymi animacji zawartymi w konkretnym obiekcie animacji, a następnie przechodzi na listę i wykonują wymagane akcje. W przypadku tworzenia niestandardowego obiektu animacji należy dodać do *listy* wszystkie zmienne animacji zawarte w tym obiekcie.

## <a name="canimationbaseobjectgetautodestroytransitions"></a><a name="getautodestroytransitions"></a> CAnimationBaseObject::GetAutodestroyTransitions

Informuje, czy powiązane przejścia są niszczone automatycznie.

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>Wartość zwracana

W przypadku wartości TRUE powiązane przejścia są niszczone automatycznie; w przypadku wartości FALSE obiekty przejściowe powinny być cofnięte przydzielenie przez aplikację wywołującą.

### <a name="remarks"></a>Uwagi

Domyślnie ta flaga ma wartość TRUE. Ustaw tę flagę tylko wtedy, gdy przydzielono przejście na stosie i/lub przejścia powinny zostać cofnięte przez aplikację wywołującą.

## <a name="canimationbaseobjectgetgroupid"></a><a name="getgroupid"></a> CAnimationBaseObject::GetGroupID

Zwraca bieżący identyfikator grupy.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Wartość zwracana

Bieżący identyfikator grupy.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby pobrać identyfikator grupy. Ta wartość jest równa 0, jeśli identyfikator grupy nie został jawnie ustawiony w konstruktorze lub z SetID.

## <a name="canimationbaseobjectgetobjectid"></a><a name="getobjectid"></a> CAnimationBaseObject:: getobjectid

Zwraca bieżący identyfikator obiektu.

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>Wartość zwracana

Bieżący identyfikator obiektu.

### <a name="remarks"></a>Uwagi

Ta metoda umożliwia pobranie identyfikatora obiektu. Wartość 0, jeśli identyfikator obiektu nie został jawnie ustawiony w konstruktorze lub z SetID.

## <a name="canimationbaseobjectgetuserdata"></a><a name="getuserdata"></a> CAnimationBaseObject:: GetUserData

Zwraca dane zdefiniowane przez użytkownika.

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość danych niestandardowych.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby pobrać dane niestandardowe w czasie wykonywania. Zwracana wartość będzie równa 0, jeśli nie została jawnie zainicjowana w konstruktorze lub przy użyciu SetUserData.

## <a name="canimationbaseobjectm_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a> CAnimationBaseObject:: m_bAutodestroyTransitions

Określa, czy powiązane przejścia powinny zostać automatycznie zniszczone.

```
BOOL m_bAutodestroyTransitions;
```

## <a name="canimationbaseobjectm_dwuserdata"></a><a name="m_dwuserdata"></a> CAnimationBaseObject:: m_dwUserData

Przechowuje dane zdefiniowane przez użytkownika.

```
DWORD m_dwUserData;
```

## <a name="canimationbaseobjectm_ngroupid"></a><a name="m_ngroupid"></a> CAnimationBaseObject:: m_nGroupID

Określa identyfikator grupy obiektu animacji.

```
UINT32 m_nGroupID;
```

## <a name="canimationbaseobjectm_nobjectid"></a><a name="m_nobjectid"></a> CAnimationBaseObject:: m_nObjectID

Określa identyfikator obiektu obiektu animacji.

```
UINT32 m_nObjectID;
```

## <a name="canimationbaseobjectm_pparentcontroller"></a><a name="m_pparentcontroller"></a> CAnimationBaseObject:: m_pParentController

Wskaźnik do nadrzędnego kontrolera animacji.

```
CAnimationController* m_pParentController;
```

## <a name="canimationbaseobjectsetautodestroytransitions"></a><a name="setautodestroytransitions"></a> CAnimationBaseObject::SetAutodestroyTransitions

Ustawia flagę, aby automatycznie zniszczyć przejścia.

```cpp
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>Parametry

*bValue*<br/>
Określa flagę autoniszczenia.

### <a name="remarks"></a>Uwagi

Ustaw tę flagę tylko w przypadku przydzielenia obiektów przejścia przy użyciu operatora new. Jeśli z jakiegoś powodu obiekty przejściowe na stosie są przydzieleni, flaga autoniszczenia powinna mieć wartość FALSE. Domyślnie ta flaga ma wartość TRUE.

## <a name="canimationbaseobjectsetid"></a><a name="setid"></a> CAnimationBaseObject::SetID

Ustawia nowe identyfikatory.

```cpp
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>Parametry

*nObjectID*<br/>
Określa nowy identyfikator obiektu.

*nGroupID*<br/>
Określa nowy identyfikator grupy.

### <a name="remarks"></a>Uwagi

Umożliwia zmianę identyfikatora obiektu i identyfikatora grupy. Jeśli nowy identyfikator grupy różni się od bieżącego identyfikatora, obiekt animacji zostanie przeniesiony do innej grupy (w razie potrzeby zostanie utworzona nowa grupa).

## <a name="canimationbaseobjectsetparentanimationobjects"></a><a name="setparentanimationobjects"></a> CAnimationBaseObject::SetParentAnimationObjects

Ustanawia relację między zmiennymi animacji, zawartymi w obiekcie animacji i ich kontenera.

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>Uwagi

Tego pomocnika można użyć do ustanowienia relacji między zmiennymi animacji zawartymi w obiekcie animacji i ich kontenera. Powoduje pętlę względem zmiennych animacji i ustawia tylny wskaźnik do nadrzędnego obiektu animacji do każdej zmiennej animacji. W bieżącej implementacji rzeczywista relacja jest ustanawiana w CAnimationBaseObject:: ApplyTransitions, dlatego wsteczne wskaźniki nie są ustawiane do momentu wywołania CAnimationGroup:: Animuj. Znajomość relacji może być przydatna podczas przetwarzania zdarzeń i musi uzyskać nadrzędny obiekt animacji z CAnimationVariable. Użyj CAnimationVariable:: GetParentAnimationObject.

## <a name="canimationbaseobjectsetuserdata"></a><a name="setuserdata"></a> CAnimationBaseObject:: SetUserData

Ustawia dane zdefiniowane przez użytkownika.

```cpp
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>Parametry

*dwUserData*<br/>
Określa dane niestandardowe.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby skojarzyć dane niestandardowe z obiektem animacji. Te dane mogą zostać pobrane później w czasie wykonywania przez program GetUserData.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

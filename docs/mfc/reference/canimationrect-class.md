---
description: 'Dowiedz się więcej na temat: Klasa CAnimationRect'
title: Klasa CAnimationRect
ms.date: 11/04/2016
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
ms.openlocfilehash: 590b1382992a32e0eb3d49e0ea562d10193c1990
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207894"
---
# <a name="canimationrect-class"></a>Klasa CAnimationRect

Implementuje funkcję prostokąta, którego boki mogą być animowane.

## <a name="syntax"></a>Składnia

```
class CAnimationRect : public CAnimationBaseObject;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationRect::CAnimationRect](#canimationrect)|Przeciążone. Konstruuje obiekt Rect animacji.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationRect:: AddTransition](#addtransition)|Dodaje przejścia dla współrzędnych Left, Top, Right i Bottom.|
|[CAnimationRect:: GetBottom](#getbottom)|Zapewnia dostęp do CAnimationVariable reprezentującego dolną współrzędną.|
|[CAnimationRect:: getdefaultvalue](#getdefaultvalue)|Zwraca wartości domyślne dla granic prostokąta.|
|[CAnimationRect:: GetLeft](#getleft)|Zapewnia dostęp do CAnimationVariable reprezentującego lewą współrzędną.|
|[CAnimationRect::GetRight](#getright)|Zapewnia dostęp do CAnimationVariable reprezentującego prawą współrzędną.|
|[CAnimationRect::GetTop](#gettop)|Zapewnia dostęp do CAnimationVariable reprezentującego górną współrzędną.|
|[CAnimationRect:: GetValue](#getvalue)|Zwraca bieżącą wartość.|
|[CAnimationRect:: SetDefaultValue](#setdefaultvalue)|Ustawia wartość domyślną.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Umieszcza hermetyzowane zmienne animacji w postaci listy. (Przesłania [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationRect:: operator prostokąt](#operator_rect)|Konwertuje CAnimationRect na RECT.|
|[CAnimationRect:: operator =](#operator_eq)|Przypisuje prostokąt do CAnimationRect.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationRect:: m_bFixedSize](#m_bfixedsize)|Określa, czy prostokąt ma stały rozmiar.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationRect:: m_bottomValue](#m_bottomvalue)|Zmienna animacji hermetyzowanej, która reprezentuje dolną granicę prostokąta animacji.|
|[CAnimationRect:: m_leftValue](#m_leftvalue)|Zmienna animacji hermetyzowanej, która reprezentuje lewą granicę prostokąta animacji.|
|[CAnimationRect:: m_rightValue](#m_rightvalue)|Zmienna animacji hermetyzowanej, która reprezentuje prawą granicę prostokąta animacji.|
|[CAnimationRect:: m_szInitial](#m_szinitial)|Określa początkowy rozmiar prostokąta animacji.|
|[CAnimationRect:: m_topValue](#m_topvalue)|Zmienna animacji hermetyzowanej, która reprezentuje górną granicę prostokąta animacji.|

## <a name="remarks"></a>Uwagi

Klasa CAnimationRect hermetyzuje cztery obiekty CAnimationVariable i może reprezentować w aplikacji prostokąt. Aby użyć tej klasy w aplikacji, należy po prostu utworzyć wystąpienie obiektu tej klasy, dodać go do kontrolera animacji przy użyciu CAnimationController:: AddAnimationObject i wywołać metodę AddTransition dla każdego przejścia, które ma zostać zastosowane do lewej, prawego górnego i dolnego współrzędnej.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationrectaddtransition"></a><a name="addtransition"></a> CAnimationRect:: AddTransition

Dodaje przejścia dla współrzędnych Left, Top, Right i Bottom.

```cpp
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>Parametry

*pLeftTransition*<br/>
Określa przejście po lewej stronie.

*pTopTransition*<br/>
Określa przejście dla górnej krawędzi.

*pRightTransition*<br/>
Określa przejście po prawej stronie.

*pBottomTransition*<br/>
Określa przejście dla dolnej krawędzi.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby dodać określone przejścia do wewnętrznej listy przejść, które mają zostać zastosowane do zmiennych animacji dla każdego prostokąta. Po dodaniu przejść nie są one stosowane natychmiast i przechowywane na liście wewnętrznej. Przejścia są stosowane (dodawane do scenorysu dla określonej wartości) podczas wywoływania CAnimationController:: animować. Jeśli nie musisz stosować przejścia do jednego ze prostokątów, możesz przekazać wartość NULL.

## <a name="canimationrectcanimationrect"></a><a name="canimationrect"></a> CAnimationRect::CAnimationRect

Konstruuje obiekt CAnimationRect.

```
CAnimationRect();

CAnimationRect(
    const CRect& rect,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    const CPoint& pt,
    const CSize& sz,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    int nLeft,
    int nTop,
    int nRight,
    int nBottom,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametry

*cinania*<br/>
Określa domyślny prostokąt.

*nGroupID*<br/>
Określa identyfikator grupy.

*nObjectID*<br/>
Określa identyfikator obiektu.

*dwUserData*<br/>
Określa dane zdefiniowane przez użytkownika.

*zmiennoprzecinkow*<br/>
Współrzędna lewego górnego rogu.

*sz*<br/>
Rozmiar prostokąta.

*nLeft*<br/>
Określa współrzędną lewej krawędzi.

*nTop*<br/>
Określa współrzędną górnej granicy.

*nRight*<br/>
Określa współrzędną prawej granicy.

*nBottom*<br/>
Określa współrzędną dolną granicę.

### <a name="remarks"></a>Uwagi

Obiekt jest skonstruowany z wartościami domyślnymi dla lewego, górnego, prawego i dolnego, identyfikatora obiektu i grupy, która zostanie ustawiona na 0. Można je później zmienić w czasie wykonywania przy użyciu funkcji SetDefaults i SetID.

## <a name="canimationrectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationRect::GetAnimationVariableList

Umieszcza hermetyzowane zmienne animacji w postaci listy.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametry

*dzieł*<br/>
Gdy funkcja zwraca, zawiera wskaźniki do czterech obiektów CAnimationVariable reprezentujących współrzędne prostokąta.

## <a name="canimationrectgetbottom"></a><a name="getbottom"></a> CAnimationRect:: GetBottom

Zapewnia dostęp do CAnimationVariable reprezentującego dolną współrzędną.

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do hermetyzowanych CAnimationVariable reprezentujących dolną współrzędną.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowego CAnimationVariable reprezentującego dolną współrzędną.

## <a name="canimationrectgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationRect:: getdefaultvalue

Zwraca wartości domyślne dla granic prostokąta.

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>Wartość zwracana

Wartość CRect, która zawiera wartości domyślne dla lewej, prawej, góry i dołu.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać wartość domyślną, która została wcześniej ustawiona przez konstruktora lub SetDefaultValue.

## <a name="canimationrectgetleft"></a><a name="getleft"></a> CAnimationRect:: GetLeft

Zapewnia dostęp do CAnimationVariable reprezentującego lewą współrzędną.

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do hermetyzowanych CAnimationVariable reprezentujących lewą współrzędną.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowego CAnimationVariable reprezentującego lewą współrzędną.

## <a name="canimationrectgetright"></a><a name="getright"></a> CAnimationRect::GetRight

Zapewnia dostęp do CAnimationVariable reprezentującego prawą współrzędną.

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do zhermetyzowanej CAnimationVariable reprezentującej prawą współrzędną.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowej CAnimationVariable reprezentującej prawą współrzędną.

## <a name="canimationrectgettop"></a><a name="gettop"></a> CAnimationRect::GetTop

Zapewnia dostęp do CAnimationVariable reprezentującego górną współrzędną.

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do hermetyzowanych CAnimationVariable reprezentujących górną współrzędną.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowego CAnimationVariable reprezentującego górną współrzędną.

## <a name="canimationrectgetvalue"></a><a name="getvalue"></a> CAnimationRect:: GetValue

Zwraca bieżącą wartość.

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>Parametry

*cinania*<br/>
Rozdzielczości. Zawiera bieżącą wartość, gdy ta metoda zwraca.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli bieżąca wartość została pobrana pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać bieżącą wartość prostokąta animacji. Jeśli ta metoda nie powiedzie się lub nie zainicjowano bazowych obiektów COM dla lewej, Góra, prawo i dół, Rect zawiera wartość domyślną, która została wcześniej ustawiona w konstruktorze lub przez SetDefaultValue.

## <a name="canimationrectm_bfixedsize"></a><a name="m_bfixedsize"></a> CAnimationRect:: m_bFixedSize

Określa, czy prostokąt ma stały rozmiar.

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>Uwagi

Jeśli ten element członkowski ma wartość true, rozmiar prostokąta jest stały i wartości Right i Bottom są ponownie obliczane po każdym przesunięciu lewego górnego rogu zgodnie ze stałym rozmiarem. Ustaw tę wartość na TRUE, aby łatwo przesunąć prostokąt wokół ekranu. W tym przypadku zmiany zastosowane do prawych i dolnych współrzędnych są ignorowane. Rozmiar jest przechowywany wewnętrznie podczas konstruowania obiektu i/lub wywołania metody SetDefaultValue. Domyślnie ten element członkowski jest ustawiony na wartość FALSE.

## <a name="canimationrectm_bottomvalue"></a><a name="m_bottomvalue"></a> CAnimationRect:: m_bottomValue

Zmienna animacji hermetyzowanej, która reprezentuje dolną granicę prostokąta animacji.

```
CAnimationVariable m_bottomValue;
```

## <a name="canimationrectm_leftvalue"></a><a name="m_leftvalue"></a> CAnimationRect:: m_leftValue

Zmienna animacji hermetyzowanej, która reprezentuje lewą granicę prostokąta animacji.

```
CAnimationVariable m_leftValue;
```

## <a name="canimationrectm_rightvalue"></a><a name="m_rightvalue"></a> CAnimationRect:: m_rightValue

Zmienna animacji hermetyzowanej, która reprezentuje prawą granicę prostokąta animacji.

```
CAnimationVariable m_rightValue;
```

## <a name="canimationrectm_szinitial"></a><a name="m_szinitial"></a> CAnimationRect:: m_szInitial

Określa początkowy rozmiar prostokąta animacji.

```
CSize m_szInitial;
```

## <a name="canimationrectm_topvalue"></a><a name="m_topvalue"></a> CAnimationRect:: m_topValue

Zmienna animacji hermetyzowanej, która reprezentuje górną granicę prostokąta animacji.

```
CAnimationVariable m_topValue;
```

## <a name="canimationrectoperator-rect"></a><a name="operator_rect"></a> CAnimationRect:: operator prostokąt

Konwertuje CAnimationRect na RECT.

```
operator RECT();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość prostokąta animacji jako RECT.

### <a name="remarks"></a>Uwagi

Ta funkcja wewnętrznie wywołuje metodę GetValue. Jeśli GetValue z jakiegoś powodu nie powiedzie się, zwracany prostokąt będzie zawierać wartości domyślne dla wszystkich współrzędnych prostokąta.

## <a name="canimationrectoperator"></a><a name="operator_eq"></a> CAnimationRect:: operator =

Przypisuje prostokąt do CAnimationRect.

```cpp
void operator=(const RECT& rect);
```

### <a name="parameters"></a>Parametry

*cinania*<br/>
Nowa wartość prostokąta animacji.

### <a name="remarks"></a>Uwagi

Zaleca się wykonanie tej czynności przed rozpoczęciem animacji, ponieważ ten operator wywołuje metodę SetDefaultValue, która odtworzy bazowe obiekty COM dla składników koloru, jeśli zostały utworzone. Jeśli zasubskrybowano ten obiekt animacji do zdarzeń (ValueChanged lub IntegerValueChanged), należy ponownie włączyć te zdarzenia.

## <a name="canimationrectsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationRect:: SetDefaultValue

Ustawia wartość domyślną.

```cpp
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>Parametry

*cinania*<br/>
Określa nowe wartości domyślne dla lewej, Góra, prawo i dół.

### <a name="remarks"></a>Uwagi

Ta funkcja służy do ustawiania wartości domyślnej dla obiektu animacji. Te metody przypisują wartości domyślne do granic prostokąta. Tworzy również ponownie bazowe obiekty COM, jeśli zostały utworzone. Jeśli zasubskrybowano ten obiekt animacji do zdarzeń (ValueChanged lub IntegerValueChanged), należy ponownie włączyć te zdarzenia.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

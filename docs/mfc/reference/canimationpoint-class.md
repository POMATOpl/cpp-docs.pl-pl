---
description: 'Dowiedz się więcej na temat: Klasa CAnimationPoint'
title: Klasa CAnimationPoint
ms.date: 11/04/2016
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
helpviewer_keywords:
- CAnimationPoint [MFC], CAnimationPoint
- CAnimationPoint [MFC], AddTransition
- CAnimationPoint [MFC], GetDefaultValue
- CAnimationPoint [MFC], GetValue
- CAnimationPoint [MFC], GetX
- CAnimationPoint [MFC], GetY
- CAnimationPoint [MFC], SetDefaultValue
- CAnimationPoint [MFC], GetAnimationVariableList
- CAnimationPoint [MFC], m_xValue
- CAnimationPoint [MFC], m_yValue
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
ms.openlocfilehash: ddefb93950f0ff1109478f3574413faf9f60a22a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336780"
---
# <a name="canimationpoint-class"></a>Klasa CAnimationPoint

Implementuje funkcję punktu, którego współrzędne mogą być animowane.

## <a name="syntax"></a>Składnia

```
class CAnimationPoint : public CAnimationBaseObject;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|Przeciążone. Tworzy obiekt CAnimationPoint.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationPoint:: AddTransition](#addtransition)|Dodaje przejścia dla współrzędnych X i Y.|
|[CAnimationPoint:: getdefaultvalue](#getdefaultvalue)|Zwraca wartości domyślne dla współrzędnych X i Y.|
|[CAnimationPoint:: GetValue](#getvalue)|Zwraca bieżącą wartość.|
|[CAnimationPoint::GetX](#getx)|Zapewnia dostęp do CAnimationVariable dla współrzędnych X.|
|[CAnimationPoint::GetY](#gety)|Zapewnia dostęp do CAnimationVariable dla współrzędnych Y.|
|[CAnimationPoint:: SetDefaultValue](#setdefaultvalue)|Ustawia wartość domyślną.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|Umieszcza hermetyzowane zmienne animacji w postaci listy. (Przesłania [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationPoint:: operator CPoint](#operator_cpoint)|Konwertuje CAnimationPoint na CPoint.|
|[CAnimationPoint:: operator =](#operator_eq)|Przypisuje ptSrc do CAnimationPoint.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationPoint:: m_xValue](#m_xvalue)|Zmienna animacji hermetyzowanej, która reprezentuje współrzędną X punktu animacji.|
|[CAnimationPoint:: m_yValue](#m_yvalue)|Zmienna animacji hermetyzowanej, która reprezentuje współrzędną Y punktu animacji.|

## <a name="remarks"></a>Uwagi

Klasa CAnimationPoint hermetyzuje dwa obiekty CAnimationVariable i może reprezentować w aplikacji punkt. Na przykład można użyć tej klasy do animowania położenia dowolnego obiektu na ekranie (np. ciąg tekstowy, okrąg, punkt itp.). Aby użyć tej klasy w aplikacji, należy po prostu utworzyć wystąpienie obiektu tej klasy, dodać go do kontrolera animacji przy użyciu CAnimationController:: AddAnimationObject i wywołać metodę AddTransition dla każdego przejścia, które ma zostać zastosowane do współrzędnych X i/Y.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationPoint`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationpointaddtransition"></a><a name="addtransition"></a> CAnimationPoint:: AddTransition

Dodaje przejścia dla współrzędnych X i Y.

```cpp
void AddTransition(
    CBaseTransition* pXTransition,
    CBaseTransition* pYTransition);
```

### <a name="parameters"></a>Parametry

*pXTransition*<br/>
Wskaźnik przejścia dla współrzędnych X.

*pYTransition*<br/>
Wskaźnik przejścia dla współrzędnych Y.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby dodać określone przejścia do wewnętrznej listy przejść, które mają zostać zastosowane do zmiennych animacji dla współrzędnych X i Y. Po dodaniu przejść nie są one stosowane natychmiast i przechowywane na liście wewnętrznej. Przejścia są stosowane (dodawane do scenorysu dla określonej wartości) podczas wywoływania CAnimationController:: animować. Jeśli nie musisz stosować przejścia do jednej z współrzędnych, możesz przekazać wartość NULL.

## <a name="canimationpointcanimationpoint"></a><a name="canimationpoint"></a> CAnimationPoint::CAnimationPoint

Tworzy obiekt CAnimationPoint.

```
CAnimationPoint();

CAnimationPoint(
    const CPoint& ptDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametry

*ptDefault*<br/>
Określa współrzędne punktu domyślnego.

*nGroupID*<br/>
Określa identyfikator grupy.

*nObjectID*<br/>
Określa identyfikator obiektu.

*dwUserData*<br/>
Określa dane zdefiniowane przez użytkownika.

### <a name="remarks"></a>Uwagi

Konstruuje obiekt CAnimationPoint z właściwościami domyślnymi: współrzędne punktu domyślnego, identyfikator grupy i identyfikator obiektu są ustawione na 0.

## <a name="canimationpointgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationPoint::GetAnimationVariableList

Umieszcza hermetyzowane zmienne animacji w postaci listy.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametry

*dzieł*<br/>
Gdy funkcja zwraca, zawiera wskaźniki do dwóch obiektów CAnimationVariable reprezentujących współrzędne X i Y.

## <a name="canimationpointgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationPoint:: getdefaultvalue

Zwraca wartości domyślne dla współrzędnych X i Y.

```
CPoint GetDefaultValue();
```

### <a name="return-value"></a>Wartość zwracana

Punkt zawierający wartość domyślną.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać wartość domyślną, która została wcześniej ustawiona przez konstruktora lub SetDefaultValue.

## <a name="canimationpointgetvalue"></a><a name="getvalue"></a> CAnimationPoint:: GetValue

Zwraca bieżącą wartość.

```
BOOL GetValue(CPoint& ptValue);
```

### <a name="parameters"></a>Parametry

*ptValue*<br/>
Rozdzielczości. Zawiera bieżącą wartość, gdy ta metoda zwraca.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli bieżąca wartość została pobrana pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać bieżącą wartość punktu animacji. Jeśli ta metoda zakończy się niepowodzeniem lub bazowe obiekty COM dla współrzędnych X i Y nie zostały zainicjowane, ptValue zawiera wartość domyślną, która została wcześniej ustawiona w konstruktorze lub przez SetDefaultValue.

## <a name="canimationpointgetx"></a><a name="getx"></a> CAnimationPoint::GetX

Zapewnia dostęp do CAnimationVariable dla współrzędnych X.

```
CAnimationVariable& GetX();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do hermetyzowanych CAnimationVariable reprezentujących współrzędną X.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowej CAnimationVariable reprezentującej współrzędną X.

## <a name="canimationpointgety"></a><a name="gety"></a> CAnimationPoint::GetY

Zapewnia dostęp do CAnimationVariable dla współrzędnych Y.

```
CAnimationVariable& GetY();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do hermetyzowanych CAnimationVariable reprezentujących współrzędną Y.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowej CAnimationVariable reprezentującej współrzędną Y.

## <a name="canimationpointm_xvalue"></a><a name="m_xvalue"></a> CAnimationPoint:: m_xValue

Zmienna animacji hermetyzowanej, która reprezentuje współrzędną X punktu animacji.

```
CAnimationVariable m_xValue;
```

## <a name="canimationpointm_yvalue"></a><a name="m_yvalue"></a> CAnimationPoint:: m_yValue

Zmienna animacji hermetyzowanej, która reprezentuje współrzędną Y punktu animacji.

```
CAnimationVariable m_yValue;
```

## <a name="canimationpointoperator-cpoint"></a><a name="operator_cpoint"></a> CAnimationPoint:: operator CPoint

Konwertuje CAnimationPoint na CPoint.

```
operator CPoint();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość CAnimationPoint jako CPoint.

### <a name="remarks"></a>Uwagi

Ta funkcja wewnętrznie wywołuje metodę GetValue. Jeśli GetValue z jakiegoś powodu nie powiedzie się, zwracany punkt będzie zawierać wartości domyślne dla współrzędnych X i Y.

## <a name="canimationpointoperator"></a><a name="operator_eq"></a> CAnimationPoint:: operator =

Przypisuje ptSrc do CAnimationPoint.

```cpp
void operator=(const CPoint& ptSrc);
```

### <a name="parameters"></a>Parametry

*ptSrc*<br/>
Odwołuje się do CPoint lub punktu.

### <a name="remarks"></a>Uwagi

Przypisuje ptSrc do CAnimationPoint. Zaleca się wykonanie tej czynności przed rozpoczęciem animacji, ponieważ ten operator wywołuje metodę SetDefaultValue, która odtworzy bazowe obiekty COM dla współrzędnych X i Y, jeśli zostały utworzone. Jeśli zasubskrybowano ten obiekt animacji do zdarzeń (ValueChanged lub IntegerValueChanged), należy ponownie włączyć te zdarzenia.

## <a name="canimationpointsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationPoint:: SetDefaultValue

Ustawia wartość domyślną.

```cpp
void SetDefaultValue(const POINT& ptDefault);
```

### <a name="parameters"></a>Parametry

*ptDefault*<br/>
Określa domyślną wartość punktu.

### <a name="remarks"></a>Uwagi

Ta funkcja służy do ustawiania wartości domyślnej dla obiektu animacji. Te metody przypisują wartości domyślne do współrzędnych X i Y punktu animacji. Tworzy również ponownie bazowe obiekty COM, jeśli zostały utworzone. Jeśli zasubskrybowano ten obiekt animacji do zdarzeń (ValueChanged lub IntegerValueChanged), należy ponownie włączyć te zdarzenia.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

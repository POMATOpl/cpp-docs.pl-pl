---
description: 'Dowiedz się więcej na temat: Klasa CAnimationSize'
title: Klasa CAnimationSize
ms.date: 11/04/2016
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
ms.openlocfilehash: 894675c485077291c3fca35acfb9bfa9a3d10286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336766"
---
# <a name="canimationsize-class"></a>Klasa CAnimationSize

Implementuje funkcje obiektu size, którego wymiary mogą być animowane.

## <a name="syntax"></a>Składnia

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationSize::CAnimationSize](#canimationsize)|Przeciążone. Konstruuje obiekt rozmiaru animacji.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationSize:: AddTransition](#addtransition)|Dodaje przejścia dla szerokości i wysokości.|
|[CAnimationSize::GetCX](#getcx)|Zapewnia dostęp do CAnimationVariable reprezentującego szerokość.|
|[CAnimationSize::GetCY](#getcy)|Zapewnia dostęp do CAnimationVariable reprezentującego wysokość.|
|[CAnimationSize:: getdefaultvalue](#getdefaultvalue)|Zwraca wartości domyślne dla szerokości i wysokości.|
|[CAnimationSize:: GetValue](#getvalue)|Zwraca bieżącą wartość.|
|[CAnimationSize:: SetDefaultValue](#setdefaultvalue)|Ustawia wartość domyślną.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Umieszcza hermetyzowane zmienne animacji w postaci listy. (Przesłania [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationSize:: operator CSize](#operator_csize)|Konwertuje CAnimationSize na CSize.|
|[CAnimationSize:: operator =](#operator_eq)|Przypisuje szSrc do CAnimationSize.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationSize:: m_cxValue](#m_cxvalue)|Zmienna animacji hermetyzowanej, która reprezentuje szerokość animacji.|
|[CAnimationSize:: m_cyValue](#m_cyvalue)|Zmienna animacji hermetyzowanej, która reprezentuje wysokość animacji.|

## <a name="remarks"></a>Uwagi

Klasa CAnimationSize hermetyzuje dwa obiekty CAnimationVariable i może reprezentować w aplikacji rozmiar. Na przykład można użyć tej klasy do animowania rozmiaru dowolnego dwuwymiarowego obiektu na ekranie (np. prostokąta, kontrolki itp.). Aby użyć tej klasy w aplikacji, należy po prostu utworzyć wystąpienie obiektu tej klasy, dodać go do kontrolera animacji przy użyciu CAnimationController:: AddAnimationObject i wywołać metodę AddTransition dla każdego przejścia, które ma zostać zastosowane do szerokości i/lub wysokości.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationsizeaddtransition"></a><a name="addtransition"></a> CAnimationSize:: AddTransition

Dodaje przejścia dla szerokości i wysokości.

```cpp
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>Parametry

*pCXTransition*<br/>
Wskaźnik przejścia dla szerokości.

*pCYTransition*<br/>
Wskaźnik do przejścia na wysokość.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby dodać określone przejścia do wewnętrznej listy przejść, które mają zostać zastosowane do zmiennych animacji dla szerokości i wysokości. Po dodaniu przejść nie są one stosowane natychmiast i przechowywane na liście wewnętrznej. Przejścia są stosowane (dodawane do scenorysu dla określonej wartości) podczas wywoływania CAnimationController:: animować. Jeśli nie musisz stosować przejścia do jednego z wymiarów, możesz przekazać wartość NULL.

## <a name="canimationsizecanimationsize"></a><a name="canimationsize"></a> CAnimationSize::CAnimationSize

Konstruuje obiekt rozmiaru animacji.

```
CAnimationSize();

CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametry

*szDefault*<br/>
Określa rozmiar domyślny.

*nGroupID*<br/>
Określa identyfikator grupy.

*nObjectID*<br/>
Określa identyfikator obiektu.

*dwUserData*<br/>
Określa dane zdefiniowane przez użytkownika.

### <a name="remarks"></a>Uwagi

Obiekt jest skonstruowany z wartościami domyślnymi dla szerokości, wysokości, identyfikatora obiektu i identyfikatora grupy, dla których zostanie ustawiona wartość 0. Można je później zmienić w czasie wykonywania przy użyciu funkcji SetDefaults i SetID.

## <a name="canimationsizegetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationSize::GetAnimationVariableList

Umieszcza hermetyzowane zmienne animacji w postaci listy.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametry

*dzieł*<br/>
Gdy funkcja zwraca, zawiera wskaźniki do dwóch obiektów CAnimationVariable reprezentujących szerokość i wysokość.

## <a name="canimationsizegetcx"></a><a name="getcx"></a> CAnimationSize::GetCX

Zapewnia dostęp do CAnimationVariable reprezentującego szerokość.

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do zhermetyzowanej CAnimationVariable reprezentującej szerokość.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowej CAnimationVariable reprezentującej szerokość.

## <a name="canimationsizegetcy"></a><a name="getcy"></a> CAnimationSize::GetCY

Zapewnia dostęp do CAnimationVariable reprezentującego wysokość.

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do zhermetyzowanej CAnimationVariable reprezentującej wysokość.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowego CAnimationVariable reprezentującego wysokość.

## <a name="canimationsizegetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationSize:: getdefaultvalue

Zwraca wartości domyślne dla szerokości i wysokości.

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>Wartość zwracana

Obiekt CSize zawierający wartości domyślne.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać wartość domyślną, która została wcześniej ustawiona przez konstruktora lub SetDefaultValue.

## <a name="canimationsizegetvalue"></a><a name="getvalue"></a> CAnimationSize:: GetValue

Zwraca bieżącą wartość.

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>Parametry

*szValue*<br/>
Rozdzielczości. Zawiera bieżącą wartość, gdy ta metoda zwraca.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli bieżąca wartość została pobrana pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać bieżącą wartość rozmiaru animacji. Jeśli ta metoda nie powiedzie się lub nie zainicjowano bazowych obiektów COM o szerokości i rozmiarze, szValue zawiera wartość domyślną, która została wcześniej ustawiona w konstruktorze lub przez SetDefaultValue.

## <a name="canimationsizem_cxvalue"></a><a name="m_cxvalue"></a> CAnimationSize:: m_cxValue

Zmienna animacji hermetyzowanej, która reprezentuje szerokość animacji.

```
CAnimationVariable m_cxValue;
```

## <a name="canimationsizem_cyvalue"></a><a name="m_cyvalue"></a> CAnimationSize:: m_cyValue

Zmienna animacji hermetyzowanej, która reprezentuje wysokość animacji.

```
CAnimationVariable m_cyValue;
```

## <a name="canimationsizeoperator-csize"></a><a name="operator_csize"></a> CAnimationSize:: operator CSize

Konwertuje CAnimationSize na CSize.

```
operator CSize();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość rozmiaru animacji jako CSize.

### <a name="remarks"></a>Uwagi

Ta funkcja wewnętrznie wywołuje metodę GetValue. Jeśli GetValue z jakiegoś powodu nie powiedzie się, zwrócony rozmiar będzie zawierać wartości domyślne dla szerokości i wysokości.

## <a name="canimationsizeoperator"></a><a name="operator_eq"></a> CAnimationSize:: operator =

Przypisuje szSrc do CAnimationSize.

```cpp
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>Parametry

*szSrc*<br/>
Odwołuje się do CSize lub rozmiaru.

### <a name="remarks"></a>Uwagi

Przypisuje szSrc do CAnimationSize. Zaleca się wykonanie tej czynności przed rozpoczęciem animacji, ponieważ ten operator wywołuje metodę SetDefaultValue, która ponownie tworzy bazowe obiekty COM dla szerokości i wysokości, jeśli zostały utworzone. Jeśli zasubskrybowano ten obiekt animacji do zdarzeń (ValueChanged lub IntegerValueChanged), należy ponownie włączyć te zdarzenia.

## <a name="canimationsizesetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationSize:: SetDefaultValue

Ustawia wartość domyślną.

```cpp
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>Parametry

*szDefault*<br/>
Określa nowy rozmiar domyślny.

### <a name="remarks"></a>Uwagi

Ta funkcja służy do ustawiania wartości domyślnej dla obiektu animacji. Te metody przypisują wartości domyślne do szerokości i wysokości rozmiaru animacji. Tworzy również ponownie bazowe obiekty COM, jeśli zostały utworzone. Jeśli zasubskrybowano ten obiekt animacji do zdarzeń (ValueChanged lub IntegerValueChanged), należy ponownie włączyć te zdarzenia.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

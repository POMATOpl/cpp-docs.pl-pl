---
description: 'Dowiedz się więcej na temat: Klasa CAnimationColor'
title: Klasa CAnimationColor
ms.date: 11/04/2016
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
ms.openlocfilehash: 430f017bc9d60eed5e2d42b71f0303546deecaca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318640"
---
# <a name="canimationcolor-class"></a>Klasa CAnimationColor

Implementuje funkcję koloru, którego składniki Red, Green i Blue mogą być animowane.

## <a name="syntax"></a>Składnia

```
class CAnimationColor : public CAnimationBaseObject;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationColor::CAnimationColor](#canimationcolor)|Przeciążone. Konstruuje obiekt koloru animacji.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationColor:: AddTransition](#addtransition)|Dodaje przejścia dla składników czerwony, zielony i niebieski.|
|[CAnimationColor::GetB](#getb)|Zapewnia dostęp do CAnimationVariable reprezentującego niebieski składnik.|
|[CAnimationColor:: getdefaultvalue](#getdefaultvalue)|Zwraca wartości domyślne dla składników koloru.|
|[CAnimationColor::GetG](#getg)|Zapewnia dostęp do CAnimationVariable reprezentującego zielony składnik.|
|[CAnimationColor::GetR](#getr)|Zapewnia dostęp do CAnimationVariable reprezentującego składnik czerwony.|
|[CAnimationColor:: GetValue](#getvalue)|Zwraca bieżącą wartość.|
|[CAnimationColor:: SetDefaultValue](#setdefaultvalue)|Ustawia wartość domyślną.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Umieszcza hermetyzowane zmienne animacji w postaci listy. (Przesłania [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationColor:: operator COLORREF](#operator_colorref)||
|[CAnimationColor:: operator =](#operator_eq)|Przypisuje kolor do CAnimationColor.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationColor:: m_bValue](#m_bvalue)|Zmienna animacji hermetyzowanej reprezentująca niebieski składnik koloru animacji.|
|[CAnimationColor:: m_gValue](#m_gvalue)|Zmienna animacji hermetyzowanej reprezentująca zielony składnik koloru animacji.|
|[CAnimationColor:: m_rValue](#m_rvalue)|Zmienna animacji hermetyzowanej reprezentująca czerwony składnik koloru animacji.|

## <a name="remarks"></a>Uwagi

Klasa CAnimationColor hermetyzuje trzy obiekty CAnimationVariable i może reprezentować aplikacje kolorem. Na przykład można użyć tej klasy do animowania kolorów dowolnego obiektu na ekranie (np. kolor tekstu, kolor tła itp.). Aby użyć tej klasy w aplikacji, należy po prostu utworzyć wystąpienie obiektu tej klasy, dodać go do kontrolera animacji przy użyciu CAnimationController:: AddAnimationObject i wywołać metodę AddTransition dla każdego przejścia, które ma zostać zastosowane do składników czerwony, zielony i niebieski.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationcoloraddtransition"></a><a name="addtransition"></a> CAnimationColor:: AddTransition

Dodaje przejścia dla składników czerwony, zielony i niebieski.

```cpp
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>Parametry

*pRTransition*<br/>
Przejście dla składnika czerwony.

*pGTransition*<br/>
Przejście dla zielonego składnika.

*pBTransition*<br/>
Przejście dla niebieskiego składnika.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby dodać określone przejścia do wewnętrznej listy przejść, które mają zostać zastosowane do zmiennych animacji reprezentujących składniki koloru. Po dodaniu przejść nie są one stosowane natychmiast i przechowywane na liście wewnętrznej. Przejścia są stosowane (dodawane do scenorysu dla określonej wartości) podczas wywoływania CAnimationController:: animować. Jeśli nie musisz stosować przejścia do jednego z komponentów koloru, możesz przekazać wartość NULL.

## <a name="canimationcolorcanimationcolor"></a><a name="canimationcolor"></a> CAnimationColor::CAnimationColor

Konstruuje obiekt CAnimationColor.

```
CAnimationColor();

CAnimationColor(
    COLORREF color,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
Określa kolor domyślny.

*nGroupID*<br/>
Określa identyfikator grupy.

*nObjectID*<br/>
Określa identyfikator obiektu.

*dwUserData*<br/>
Określa dane zdefiniowane przez użytkownika.

### <a name="remarks"></a>Uwagi

Obiekt jest skonstruowany z wartościami domyślnymi dla czerwonego, zielonego, niebieskiego, identyfikatora obiektu i grupy o IDENTYFIKATORze, która zostanie ustawiona na 0. Można je później zmienić w czasie wykonywania przy użyciu funkcji SetDefaults i SetID.

## <a name="canimationcolorgetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationColor::GetAnimationVariableList

Umieszcza hermetyzowane zmienne animacji w postaci listy.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametry

*dzieł*<br/>
Gdy funkcja zwraca, zawiera wskaźniki do trzech obiektów CAnimationVariable reprezentujących czerwony, zielony i niebieski składnik.

## <a name="canimationcolorgetb"></a><a name="getb"></a> CAnimationColor::GetB

Zapewnia dostęp do CAnimationVariable reprezentującego niebieski składnik.

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do zhermetyzowanej CAnimationVariable reprezentującej niebieski składnik.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowej CAnimationVariable reprezentującej niebieski składnik.

## <a name="canimationcolorgetdefaultvalue"></a><a name="getdefaultvalue"></a> CAnimationColor:: getdefaultvalue

Zwraca wartości domyślne dla składników koloru.

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>Wartość zwracana

Wartość COLORREF, która zawiera wartości domyślne dla składników RGB.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać wartość domyślną, która została wcześniej ustawiona przez konstruktora lub SetDefaultValue.

## <a name="canimationcolorgetg"></a><a name="getg"></a> CAnimationColor::GetG

Zapewnia dostęp do CAnimationVariable reprezentującego zielony składnik.

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do zhermetyzowanej CAnimationVariable reprezentującej zielony składnik.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowej CAnimationVariable reprezentującej zielony składnik.

## <a name="canimationcolorgetr"></a><a name="getr"></a> CAnimationColor::GetR

Zapewnia dostęp do CAnimationVariable reprezentującego składnik czerwony.

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do zhermetyzowanej CAnimationVariable reprezentującej składnik czerwony.

### <a name="remarks"></a>Uwagi

Możesz wywołać tę metodę, aby uzyskać bezpośredni dostęp do bazowej CAnimationVariable reprezentującej składnik czerwony.

## <a name="canimationcolorgetvalue"></a><a name="getvalue"></a> CAnimationColor:: GetValue

Zwraca bieżącą wartość.

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
Rozdzielczości. Zawiera bieżącą wartość, gdy ta metoda zwraca.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli bieżąca wartość została pobrana pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać bieżącą wartość koloru animacji. Jeśli ta metoda nie powiedzie się lub nie zainicjowano bazowych obiektów COM dla składników koloru, kolor zawiera wartość domyślną, która została wcześniej ustawiona w konstruktorze lub przez SetDefaultValue.

## <a name="canimationcolorm_bvalue"></a><a name="m_bvalue"></a> CAnimationColor:: m_bValue

Zmienna animacji hermetyzowanej reprezentująca niebieski składnik koloru animacji.

```
CAnimationVariable m_bValue;
```

## <a name="canimationcolorm_gvalue"></a><a name="m_gvalue"></a> CAnimationColor:: m_gValue

Zmienna animacji hermetyzowanej reprezentująca zielony składnik koloru animacji.

```
CAnimationVariable m_gValue;
```

## <a name="canimationcolorm_rvalue"></a><a name="m_rvalue"></a> CAnimationColor:: m_rValue

Zmienna animacji hermetyzowanej reprezentująca czerwony składnik koloru animacji.

```
CAnimationVariable m_rValue;
```

## <a name="canimationcoloroperator-colorref"></a><a name="operator_colorref"></a> CAnimationColor:: operator COLORREF

```
operator COLORREF();
```

### <a name="return-value"></a>Wartość zwracana

## <a name="canimationcoloroperator"></a><a name="operator_eq"></a> CAnimationColor:: operator =

Przypisuje kolor do CAnimationColor.

```cpp
void operator=(COLORREF color);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
Określa nowy kolor animacji wartości.

### <a name="remarks"></a>Uwagi

Zaleca się wykonanie tej czynności przed rozpoczęciem animacji, ponieważ ten operator wywołuje metodę SetDefaultValue, która odtworzy bazowe obiekty COM dla składników koloru, jeśli zostały utworzone. Jeśli zasubskrybowano ten obiekt animacji do zdarzeń (ValueChanged lub IntegerValueChanged), należy ponownie włączyć te zdarzenia.

## <a name="canimationcolorsetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationColor:: SetDefaultValue

Ustawia wartość domyślną.

```cpp
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
Określa nowe wartości domyślne dla składników czerwony, zielony i niebieski.

### <a name="remarks"></a>Uwagi

Ta funkcja służy do ustawiania wartości domyślnej dla obiektu animacji. Te metody przypisują wartości domyślne do składników koloru animacji. Tworzy również ponownie bazowe obiekty COM, jeśli zostały utworzone. Jeśli zasubskrybowano ten obiekt animacji do zdarzeń (ValueChanged lub IntegerValueChanged), należy ponownie włączyć te zdarzenia.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

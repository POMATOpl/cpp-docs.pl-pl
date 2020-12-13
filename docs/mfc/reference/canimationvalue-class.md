---
description: 'Dowiedz się więcej na temat: Klasa CAnimationValue'
title: Klasa CAnimationValue
ms.date: 11/04/2016
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
ms.openlocfilehash: d704e83d286b4078af90d09edef35e8445d149d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336745"
---
# <a name="canimationvalue-class"></a>Klasa CAnimationValue

Implementuje funkcję obiektu animacji o jednej wartości.

## <a name="syntax"></a>Składnia

```
class CAnimationValue : public CAnimationBaseObject;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationValue::CAnimationValue](#canimationvalue)|Przeciążone. Konstruuje obiekt CAnimationValue.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationValue:: AddTransition](#addtransition)|Dodaje przejście, które ma zostać zastosowane do wartości.|
|[CAnimationValue:: GetValue](#getvalue)|Przeciążone. Pobiera bieżącą wartość.|
|[CAnimationValue:: getvariable](#getvariable)|Zapewnia dostęp do zhermetyzowanej zmiennej animacji.|
|[CAnimationValue:: SetDefaultValue](#setdefaultvalue)|Ustawia wartość domyślną.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|Umieszcza hermetyzowaną zmienną animacji w postaci listy. (Przesłania [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationValue:: operator DOUBLE](#operator_double)|Zapewnia konwersję między CAnimationValue i DOUBLE.|
|[CAnimationValue:: operator INT32](#operator_int32)|Zapewnia konwersję między CAnimationValue i INT32.|
|[CAnimationValue:: operator =](#operator_eq)|Przeciążone. Przypisuje wartość INT32 do CAnimationValue.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CAnimationValue:: m_value](#m_value)|Zmienna animacji hermetyzowanej, która reprezentuje wartość animacji.|

## <a name="remarks"></a>Uwagi

Klasa CAnimationValue hermetyzuje pojedynczy obiekt CAnimationVariable i może reprezentować w aplikacjach pojedynczą wartość animowaną. Na przykład, można użyć tej klasy do animowanej przezroczystości (efekt zaniku), kąt (do obrócenia obiektów) lub w dowolnym innym przypadku, gdy trzeba utworzyć animację w zależności od pojedynczej wartości animowanej. Aby użyć tej klasy w aplikacji, należy po prostu utworzyć wystąpienie obiektu tej klasy, dodać go do kontrolera animacji przy użyciu CAnimationController:: AddAnimationObject i wywołać metodę AddTransition dla każdego przejścia, które ma zostać zastosowane do wartości.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxanimationcontroller. h

## <a name="canimationvalueaddtransition"></a><a name="addtransition"></a> CAnimationValue:: AddTransition

Dodaje przejście, które ma zostać zastosowane do wartości.

```cpp
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Parametry

*pTransition*<br/>
Wskaźnik przejścia do obiektu.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby dodać przejście do wewnętrznej listy przejść, które mają zostać zastosowane do zmiennej animacji. Po dodaniu przejść nie są one stosowane natychmiast i przechowywane na liście wewnętrznej. Przejścia są stosowane (dodawane do scenorysu dla określonej wartości) podczas wywoływania CAnimationController:: animować.

## <a name="canimationvaluecanimationvalue"></a><a name="canimationvalue"></a> CAnimationValue::CAnimationValue

Konstruuje obiekt CAnimationValue.

```
CAnimationValue();

CAnimationValue(
    DOUBLE dblDefaultValue,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parametry

*dblDefaultValue*<br/>
Określa wartość domyślną.

*nGroupID*<br/>
Określa identyfikator grupy.

*nObjectID*<br/>
Określa identyfikator obiektu.

*dwUserData*<br/>
Określa dane zdefiniowane przez użytkownika.

### <a name="remarks"></a>Uwagi

Konstruuje obiekt CAnimationValue z właściwościami domyślnymi: wartość domyślna, identyfikator grupy i identyfikator obiektu są ustawione na 0.

## <a name="canimationvaluegetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationValue::GetAnimationVariableList

Umieszcza hermetyzowaną zmienną animacji w postaci listy.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parametry

*dzieł*<br/>
Gdy funkcja zwraca, zawiera wskaźnik do CAnimationVariable reprezentujący wartość animowaną.

## <a name="canimationvaluegetvalue"></a><a name="getvalue"></a> CAnimationValue:: GetValue

Pobiera bieżącą wartość.

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>Parametry

*dblValue*<br/>
Rozdzielczości. Gdy funkcja zwraca ją, zawiera bieżącą wartość zmiennej animacji.

*nWartość*<br/>
Rozdzielczości. Gdy funkcja zwraca ją, zawiera bieżącą wartość zmiennej animacji.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli bieżąca wartość została pobrana pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać bieżącą wartość. Ta implementacja wywołuje hermetyzowany obiekt COM, a jeśli wywołanie nie powiedzie się, ta metoda zwraca wartość domyślną, która została wcześniej ustawiona w konstruktorze lub przy użyciu SetDefaultValue.

## <a name="canimationvaluegetvariable"></a><a name="getvariable"></a> CAnimationValue:: getvariable

Zapewnia dostęp do zhermetyzowanej zmiennej animacji.

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do zhermetyzowanej zmiennej animacji.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby uzyskać dostęp do zmiennej animacji hermetyzowanej. Od CAnimationVariable uzyskasz dostęp do podstawowego obiektu IUIAnimationVariable, którego wskaźnik może mieć wartość NULL, jeśli zmienna animacji nie została utworzona.

## <a name="canimationvaluem_value"></a><a name="m_value"></a> CAnimationValue:: m_value

Zmienna animacji hermetyzowanej, która reprezentuje wartość animacji.

```
CAnimationVariable m_value;
```

## <a name="canimationvalueoperator-double"></a><a name="operator_double"></a> CAnimationValue:: operator DOUBLE

Zapewnia konwersję między CAnimationValue i DOUBLE.

```
operator DOUBLE();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość animacji.

### <a name="remarks"></a>Uwagi

Zapewnia konwersję między CAnimationValue i DOUBLE. Ta metoda wewnętrznie wywołuje metodę GetValue i nie sprawdza występowania błędów. Jeśli GetValue nie powiedzie się, zwrócona wartość będzie zawierać wartość domyślną wcześniej ustawioną w konstruktorze lub przy użyciu SetDefaultValue.

## <a name="canimationvalueoperator-int32"></a><a name="operator_int32"></a> CAnimationValue:: operator INT32

Zapewnia konwersję między CAnimationValue i INT32.

```
operator INT32();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość animacji jako liczba całkowita.

### <a name="remarks"></a>Uwagi

Zapewnia konwersję między CAnimationValue i INT32. Ta metoda wewnętrznie wywołuje metodę GetValue i nie sprawdza występowania błędów. Jeśli GetValue nie powiedzie się, zwrócona wartość będzie zawierać wartość domyślną wcześniej ustawioną w konstruktorze lub przy użyciu SetDefaultValue.

## <a name="canimationvalueoperator"></a><a name="operator_eq"></a> CAnimationValue:: operator =

Przypisuje wartość DOUBLE do CAnimationValue.

```cpp
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>Parametry

*dblVal*<br/>
Określa wartość, która ma zostać przypisana do wartości animacji.

*nVal*<br/>
Określa wartość, która ma zostać przypisana do wartości animacji.

### <a name="remarks"></a>Uwagi

Przypisuje wartość DOUBLE do CAnimationValue. Ta wartość jest ustawiana jako wartość domyślna dla hermetyzowanej zmiennej animacji. Jeśli zasubskrybowano ten obiekt animacji do zdarzeń (ValueChanged lub IntegerValueChanged), należy ponownie włączyć te zdarzenia.

## <a name="canimationvaluesetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationValue:: SetDefaultValue

Ustawia wartość domyślną.

```cpp
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Parametry

*dblDefaultValue*<br/>
Określa wartość domyślną.

### <a name="remarks"></a>Uwagi

Ta metoda służy do ustawiania wartości domyślnej. Wartość domyślna jest zwracana do aplikacji, gdy animacja nie została uruchomiona i/lub bazowy obiekt COM nie został utworzony. Jeśli źródłowy obiekt COM hermetyzowany w CAnimationVarible został już utworzony, ta metoda odtworzy go, w związku z czym może zaistnieć konieczność ponownego wywołania metod EnableValueChanged/EnableIntegerValueChanged.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

---
description: 'Dowiedz się więcej na temat: Klasa CPoint'
title: Klasa CPoint
ms.date: 11/04/2016
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
ms.openlocfilehash: 9d1c6ecb628e4d47d80503bb7a441efc4deb1252
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166762"
---
# <a name="cpoint-class"></a>Klasa CPoint

Podobne do struktury systemu Windows `POINT` .

## <a name="syntax"></a>Składnia

```
class CPoint : public tagPOINT
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CPoint:: CPoint](#cpoint)|Konstruuje a `CPoint` .|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CPoint:: offset](#offset)|Dodaje wartości do `x` `y` elementów członkowskich i `CPoint` .|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CPoint:: operator-](#operator_-)|Zwraca różnicę `CPoint` między i rozmiarem lub negacją punktu albo różnicą rozmiaru między dwoma punktami lub przesunięciem o wartości ujemnej.|
|[CPoint:: operator! =](#operator_neq)|Sprawdza pod kątem nierówności między dwoma punktami.|
|[CPoint:: operator +](#operator_add)|Zwraca sumę a `CPoint` i rozmiar lub punkt lub `CRect` przesunięcie o rozmiarze.|
|[CPoint:: operator + =](#operator_add_eq)|Przesunięcia `CPoint` przez dodanie rozmiaru lub punktu.|
|[CPoint:: operator-=](#operator_-_eq)|Przesunięcia `CPoint` przez odjęcie rozmiaru lub punktu.|
|[CPoint:: operator = =](#operator_eq_eq)|Sprawdza równość między dwoma punktami.|

## <a name="remarks"></a>Uwagi

Zawiera również funkcje członkowskie do manipulowania `CPoint` i struktur [punktów](/windows/win32/api/windef/ns-windef-point) .

`CPoint`Obiekt może być używany wszędzie tam, gdzie `POINT` jest używana struktura. Operatory tej klasy, które współdziałają z "rozmiarem", akceptują [CSize](../../atl-mfc-shared/reference/csize-class.md) obiekty lub struktury [rozmiaru](/windows/win32/api/windef/ns-windef-size) , ponieważ te dwa są zamienne.

> [!NOTE]
> Ta klasa jest pochodną `tagPOINT` struktury. (Nazwa `tagPOINT` jest mniej często używanej nazwy dla `POINT` struktury). Oznacza to, że składowe danych `POINT` struktury `x` i `y` , są dostępnymi członkami danych `CPoint` .

> [!NOTE]
> Aby uzyskać więcej informacji na temat udostępnionych klas narzędzi (takich jak `CPoint` ), zobacz [klasy udostępnione](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`tagPOINT`

`CPoint`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atltypes. h

## <a name="cpointcpoint"></a><a name="cpoint"></a> CPoint:: CPoint

Konstruuje `CPoint` obiekt.

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>Parametry

*initX*<br/>
Określa wartość `x` składowej `CPoint` .

*Inicjowanie*<br/>
Określa wartość `y` składowej `CPoint` .

*initPt*<br/>
Struktura [punktu](/windows/win32/api/windef/ns-windef-point) lub `CPoint` , która określa wartości używane do zainicjowania `CPoint` .

*initSize*<br/>
Struktura [rozmiaru](/windows/win32/api/windef/ns-windef-size) lub [CSize](../../atl-mfc-shared/reference/csize-class.md) , która określa wartości używane do zainicjowania `CPoint` .

*dwPoint*<br/>
Ustawia `x` element członkowski dla wyrazu *dwPoint* i `y` elementu członkowskiego na słowo *dwPoint* o wysokiej kolejności.

### <a name="remarks"></a>Uwagi

Jeśli nie podano argumentów, `x` a `y` elementy członkowskie są ustawione na 0.

### <a name="example"></a>Przykład

```cpp
CPoint   ptTopLeft(0, 0);
// works from a POINT, too

POINT   ptHere;
ptHere.x = 35;
ptHere.y = 95;

CPoint   ptMFCHere(ptHere);

// works from a SIZE
SIZE   sHowBig;
sHowBig.cx = 300;
sHowBig.cy = 10;

CPoint ptMFCBig(sHowBig);
// or from a DWORD

DWORD   dwSize;
dwSize = MAKELONG(35, 95);

CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```

## <a name="cpointoffset"></a><a name="offset"></a> CPoint:: offset

Dodaje wartości do `x` `y` elementów członkowskich i `CPoint` .

```cpp
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>Parametry

*xOffset*<br/>
Określa kwotę do przesunięcia `x` elementu członkowskiego `CPoint` .

*yOffset*<br/>
Określa kwotę do przesunięcia `y` elementu członkowskiego `CPoint` .

*moment*<br/>
Określa liczbę ( [punkt](/windows/win32/api/windef/ns-windef-point) lub `CPoint` ) do przesunięcia `CPoint` .

*zmienia*<br/>
Określa ilość ( [size](/windows/win32/api/windef/ns-windef-size) lub [CSize](../../atl-mfc-shared/reference/csize-class.md)) do przesunięcia `CPoint` .

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

## <a name="cpointoperator-"></a><a name="operator_eq_eq"></a> CPoint:: operator = =

Sprawdza równość między dwoma punktami.

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>Parametry

*moment*<br/>
Zawiera strukturę [](/windows/win32/api/windef/ns-windef-point) lub obiekt punktu `CPoint` .

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli punkty są równe; w przeciwnym razie 0.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

## <a name="cpointoperator-"></a><a name="operator_neq"></a> CPoint:: operator! =

Sprawdza pod kątem nierówności między dwoma punktami.

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>Parametry

*moment*<br/>
Zawiera strukturę [](/windows/win32/api/windef/ns-windef-point) lub obiekt punktu `CPoint` .

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli punkty nie są równe; w przeciwnym razie 0.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add_eq"></a> CPoint:: operator + =

Pierwsze Przeciążenie dodaje rozmiar do `CPoint` .

```cpp
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>Parametry

*zmienia*<br/>
Zawiera strukturę [rozmiaru](/windows/win32/api/windef/ns-windef-size) lub obiekt [CSize](../../atl-mfc-shared/reference/csize-class.md) .

*moment*<br/>
Zawiera strukturę [punktu](/windows/win32/api/windef/ns-windef-point) lub obiekt [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) .

### <a name="remarks"></a>Uwagi

Drugie Przeciążenie dodaje punkt do `CPoint` .

W obu przypadkach Dodawanie jest wykonywane przez dodanie `x` (lub `cx` ) składowej operandu po prawej stronie do `x` elementu członkowskiego `CPoint` i dodanie `y` (lub) składowej `cy` operandu po prawej stronie do `y` elementu członkowskiego `CPoint` .

Na przykład dodanie `CPoint(5, -7)` do zmiennej, która zawiera `CPoint(30, 40)` zmiany zmiennej do `CPoint(35, 33)` .

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-_eq"></a> CPoint:: operator-=

Pierwsze Przeciążenie odejmuje rozmiar od `CPoint` .

```cpp
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>Parametry

*zmienia*<br/>
Zawiera strukturę [rozmiaru](/windows/win32/api/windef/ns-windef-size) lub obiekt [CSize](../../atl-mfc-shared/reference/csize-class.md) .

*moment*<br/>
Zawiera strukturę [punktu](/windows/win32/api/windef/ns-windef-point) lub obiekt [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) .

### <a name="remarks"></a>Uwagi

Drugie Przeciążenie odejmuje punkt od `CPoint` .

W obu przypadkach odejmowanie jest wykonywane przez odjęcie `x` (lub `cx` ) składowej operandu po prawej stronie od `x` elementu członkowskiego `CPoint` i odejmowanie `y` (lub) składowej `cy` operandu po prawej stronie `y` elementu członkowskiego `CPoint` .

Na przykład, odejmowanie `CPoint(5, -7)` od zmiennej, która zawiera `CPoint(30, 40)` zmiany zmiennej do `CPoint(25, 47)` .

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add"></a> CPoint:: operator +

Użyj tego operatora, aby przesunięciu `CPoint` `CPoint` `CSize` obiektem lub, lub przesunięciu a `CRect` przez `CPoint` .

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>Parametry

*zmienia*<br/>
Zawiera strukturę [rozmiaru](/windows/win32/api/windef/ns-windef-size) lub obiekt [CSize](../../atl-mfc-shared/reference/csize-class.md) .

*moment*<br/>
Zawiera strukturę [punktu](/windows/win32/api/windef/ns-windef-point) lub obiekt [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) .

*lpRect*<br/>
Zawiera wskaźnik do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) lub obiektu [CRect](../../atl-mfc-shared/reference/crect-class.md) .

### <a name="return-value"></a>Wartość zwracana

, `CPoint` Który jest przesunięty o rozmiar, `CPoint` który jest przesunięciem przez punkt lub `CRect` przesunięciem przez punkt.

### <a name="remarks"></a>Uwagi

Na przykład użycie jednego z pierwszych dwóch przeciążeń w celu przesunięcia punktu `CPoint(25, -19)` przez punkt `CPoint(15, 5)` lub rozmiar `CSize(15, 5)` zwraca wartość `CPoint(40, -14)` .

Dodanie prostokąta do punktu zwraca prostokąt po przesunięciu przez `x` `y` wartości i określone w punkcie. Na przykład przy użyciu ostatniego przeciążenia do przesuwania prostokąta `CRect(125, 219, 325, 419)` przez punkt `CPoint(25, -19)` wraca `CRect(150, 200, 350, 400)` .

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-"></a> CPoint:: operator-

Użyj jednego z dwóch pierwszych przeciążeń, aby `CPoint` odjąć `CSize` obiekt lub od `CPoint` .

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>Parametry

*moment*<br/>
Struktura [punktu](/windows/win32/api/windef/ns-windef-point) lub obiekt [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) .

*zmienia*<br/>
Struktura [rozmiaru](/windows/win32/api/windef/ns-windef-size) lub obiekt [CSize](../../atl-mfc-shared/reference/csize-class.md) .

*lpRect*<br/>
Wskaźnik do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) lub obiektu [CRect](../../atl-mfc-shared/reference/crect-class.md) .

### <a name="return-value"></a>Wartość zwracana

`CSize`Jest to różnica między dwoma punktami, `CPoint` który jest przesunięty przez negację rozmiaru, `CRect` który jest przesunięty przez negację punktu lub, `CPoint` który jest negacją punktu.

### <a name="remarks"></a>Uwagi

Trzecie Przeciążenie przesunięcia a `CRect` przez negację `CPoint` . Na koniec użyj operatora jednoargumentowego do Negate `CPoint` .

Na przykład przy użyciu pierwszego przeciążenia, aby znaleźć różnicę między dwoma punktami `CPoint(25, -19)` i `CPoint(15, 5)` zwraca `CSize(10, -24)` .

Odjęcie elementu `CSize` od `CPoint` powoduje takie samo obliczenie jak powyżej, ale zwraca `CPoint` obiekt, a nie `CSize` obiekt. Na przykład przy użyciu drugiego przeciążenia, aby znaleźć różnicę między punktem `CPoint(25, -19)` a zwracanym rozmiarem `CSize(15, 5)` `CPoint(10, -24)` .

Odjęcie prostokąta od punktu zwraca przesunięcie prostokąta przez liczbę ujemnych `x` `y` wartości i określonych w punkcie. Na przykład przy użyciu ostatniego przeciążenia do przesuwania prostokąta `CRect(125, 200, 325, 400)` przez punkt `CPoint(25, -19)` wraca `CRect(100, 219, 300, 419)` .

Użyj operatora jednoargumentowego, aby Negate punkt. Na przykład użycie operatora jednoargumentowego z `CPoint(25, -19)` zwracanymi punktami `CPoint(-25, 19)` .

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>Zobacz także

[Przykładowy interfejs MDI MFC](../../overview/visual-cpp-samples.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Struktura punktów](/windows/win32/api/windef/ns-windef-point)<br/>
[Klasa CRect](../../atl-mfc-shared/reference/crect-class.md)<br/>
[Klasa CSize](../../atl-mfc-shared/reference/csize-class.md)

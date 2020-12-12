---
description: 'Dowiedz się więcej na temat: Klasa CSize'
title: Klasa CSize
ms.date: 10/18/2018
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
ms.openlocfilehash: 0a63a7e0c48948406bf5650a1b095713f701a325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166645"
---
# <a name="csize-class"></a>Klasa CSize

Podobnie jak w przypadku struktury [rozmiaru](/windows/win32/api/windef/ns-windef-size) systemu Windows, która implementuje względną współrzędną lub położeniu.

## <a name="syntax"></a>Składnia

```
class CSize : public tagSIZE
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSize:: CSize](#csize)|Konstruuje `CSize` obiekt.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CSize:: operator-](#operator_-)|Odejmuje dwa rozmiary.|
|[CSize:: operator! =](#operator_neq)|Sprawdza pod kątem nierówności między `CSize` i rozmiarem.|
|[CSize:: operator +](#operator_add)|Dodaje dwa rozmiary.|
|[CSize:: operator + =](#operator_add_eq)|Dodaje rozmiar do `CSize` .|
|[CSize:: operator-=](#operator_-_eq)|Odejmuje rozmiar od `CSize` .|
|[CSize:: operator = =](#operator_eq_eq)|Sprawdza równość między `CSize` i rozmiarem.|

## <a name="remarks"></a>Uwagi

Ta klasa jest pochodną `SIZE` struktury. Oznacza to, że można przekazać do `CSize` parametru, który wywołuje dla a `SIZE` i że elementy członkowskie danych `SIZE` struktury są dostępnymi elementami członkowskimi danych `CSize` .

`cx`Elementy i `cy` `SIZE` `CSize` są publiczne. Ponadto `CSize` implementuje funkcje elementów członkowskich do manipulowania `SIZE` strukturą.

> [!NOTE]
> Aby uzyskać więcej informacji na temat udostępnionych klas narzędzi (takich jak `CSize` ), zobacz [klasy udostępnione](../../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`tagSIZE`

`CSize`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atltypes. h

## <a name="csizecsize"></a><a name="csize"></a> CSize:: CSize

Konstruuje `CSize` obiekt.

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>Parametry

*initCX*<br/>
Ustawia `cx` element członkowski dla elementu `CSize` .

*initCY*<br/>
Ustawia `cy` element członkowski dla elementu `CSize` .

*initSize*<br/>
Struktura [rozmiaru](/windows/win32/api/windef/ns-windef-size) lub `CSize` obiekt używany do inicjowania `CSize` .

*initPt*<br/>
Struktura [punktu](/windows/win32/api/windef/ns-windef-point) lub `CPoint` obiekt używany do inicjowania `CSize` .

*dwSize*<br/>
Wartość DWORD użyta do zainicjowania `CSize` . Słowo o niskim porządku to element członkowski, `cx` a jest to element członkowski o wysokim poziomie kolejności `cy` .

### <a name="remarks"></a>Uwagi

Jeśli nie podano argumentów `cx` i `cy` są one inicjowane na zero.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

## <a name="csizeoperator-"></a><a name="operator_eq_eq"></a> CSize:: operator = =

Sprawdza równość między dwoma rozmiarami.

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>Uwagi

Zwraca wartość różną od zera, jeśli rozmiary są równe, otherwize 0.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

## <a name="csizeoperator-"></a><a name="operator_neq"></a> CSize:: operator! =

Sprawdza nierówność między dwoma rozmiarami.

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>Uwagi

Zwraca wartość różną od zera, jeśli rozmiary nie są równe. w przeciwnym razie 0.

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add_eq"></a> CSize:: operator + =

Dodaje do tego rozmiaru `CSize` .

```cpp
void operator+=(SIZE size) throw();
```

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-_eq"></a> CSize:: operator-=

Odejmuje rozmiar od tego `CSize` .

```cpp
void operator-=(SIZE size) throw();
```

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add"></a> CSize:: operator +

Te operatory dodają tę `CSize` wartość do wartości parametru.

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>Uwagi

Zobacz następujące opisy poszczególnych operatorów:

- **operator + (** *rozmiar* **)**

  Ta operacja dodaje dwie `CSize` wartości.

- **operator + (** *punkt* **)**

  Ta operacja przesunie (przenosi) wartość [punktu](/windows/win32/api/windef/ns-windef-point) (lub [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) przez tę `CSize` wartość. I elementy członkowskie `cx` `cy` tej `CSize` wartości są dodawane do `x` `y` elementów członkowskich danych i `POINT` . Jest on analogiczny do wersji [CPoint:: operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) , która przyjmuje parametr [size](/windows/win32/api/windef/ns-windef-size) .

- **operator + (** *lpRect* **)**

   Ta operacja przesunie (przenosi) wartość [Rect](/windows/win32/api/windef/ns-windef-rect) (lub [CRect](../../atl-mfc-shared/reference/crect-class.md)) o tę `CSize` wartość. `cx`I `cy` elementy członkowskie tej `CSize` wartości są dodawane do `left` `top` `right` `bottom` elementów członkowskich danych,,, i `RECT` . Jest on analogiczny do wersji [CRect:: operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) , która przyjmuje parametr [size](/windows/win32/api/windef/ns-windef-size) .

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-"></a> CSize:: operator-

Pierwsze trzy z tych operatorów odejmuje tę `CSize` wartość do wartości parametru.

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>Uwagi

Czwarty operator, jednoargumentowy minus, zmienia znak `CSize` wartości. Zobacz następujące opisy poszczególnych operatorów:

- **operator — (** *rozmiar* **)**

  Ta operacja odejmuje dwie `CSize` wartości.

- **operator-(** *punkt* **)**

  Ta operacja przesunie (przenosi) wartość [Point](/windows/win32/api/windef/ns-windef-point) lub [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) przez dodatek odwrotny do tej `CSize` wartości. `cx`Wartość i `cy` tej `CSize` wartości są odejmowane od `x` `y` elementów członkowskich danych i `POINT` . Jest on analogiczny do wersji elementu [CPoint:: operator-](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) , który pobiera parametr [size](/windows/win32/api/windef/ns-windef-size) .

- **operator-(** *lpRect* **)**

  Ta operacja przesunie (przenosi) wartość [Rect](/windows/win32/api/windef/ns-windef-rect) lub [CRect](../../atl-mfc-shared/reference/crect-class.md) przez dodatek odwrotny do tej `CSize` wartości. `cx`I `cy` elementy członkowskie tej `CSize` wartości są odejmowane od `left` `top` `right` `bottom` elementów członkowskich danych,, i `RECT` . Jest on analogiczny do wersji elementu [CRect:: operator-](../../atl-mfc-shared/reference/crect-class.md#operator_-) , który pobiera parametr [size](/windows/win32/api/windef/ns-windef-size) .

- **operator-()**

  Ta operacja zwraca dodatek do wartości odwrotnej `CSize` .

### <a name="example"></a>Przykład

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>Zobacz także

[Przykładowy interfejs MDI MFC](../../overview/visual-cpp-samples.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CRect](../../atl-mfc-shared/reference/crect-class.md)<br/>
[Klasa CPoint](../../atl-mfc-shared/reference/cpoint-class.md)

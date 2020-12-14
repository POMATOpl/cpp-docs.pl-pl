---
description: 'Dowiedz się więcej na temat: Klasa CD2DGeometrySink'
title: Klasa CD2DGeometrySink
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::AddArc
- AFXRENDERTARGET/CD2DGeometrySink::AddBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddBeziers
- AFXRENDERTARGET/CD2DGeometrySink::AddLine
- AFXRENDERTARGET/CD2DGeometrySink::AddLines
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBeziers
- AFXRENDERTARGET/CD2DGeometrySink::BeginFigure
- AFXRENDERTARGET/CD2DGeometrySink::Close
- AFXRENDERTARGET/CD2DGeometrySink::EndFigure
- AFXRENDERTARGET/CD2DGeometrySink::Get
- AFXRENDERTARGET/CD2DGeometrySink::IsValid
- AFXRENDERTARGET/CD2DGeometrySink::SetFillMode
- AFXRENDERTARGET/CD2DGeometrySink::SetSegmentFlags
- AFXRENDERTARGET/CD2DGeometrySink::m_pSink
helpviewer_keywords:
- CD2DGeometrySink [MFC], CD2DGeometrySink
- CD2DGeometrySink [MFC], AddArc
- CD2DGeometrySink [MFC], AddBezier
- CD2DGeometrySink [MFC], AddBeziers
- CD2DGeometrySink [MFC], AddLine
- CD2DGeometrySink [MFC], AddLines
- CD2DGeometrySink [MFC], AddQuadraticBezier
- CD2DGeometrySink [MFC], AddQuadraticBeziers
- CD2DGeometrySink [MFC], BeginFigure
- CD2DGeometrySink [MFC], Close
- CD2DGeometrySink [MFC], EndFigure
- CD2DGeometrySink [MFC], Get
- CD2DGeometrySink [MFC], IsValid
- CD2DGeometrySink [MFC], SetFillMode
- CD2DGeometrySink [MFC], SetSegmentFlags
- CD2DGeometrySink [MFC], m_pSink
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
ms.openlocfilehash: e7916cdb39272e924a9d6ef6c0a8322d8ce6fb1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193425"
---
# <a name="cd2dgeometrysink-class"></a>Klasa CD2DGeometrySink

Otoka dla ID2D1GeometrySink.

## <a name="syntax"></a>Składnia

```
class CD2DGeometrySink;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|Konstruuje obiekt CD2DGeometrySink z obiektu CD2DPathGeometry.|
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|Destruktor. Wywołuje się, gdy obiekt ujścia geometrii D2D jest niszczony.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DGeometrySink::AddArc](#addarc)|Dodaje pojedynczy łuk do geometrii ścieżki|
|[CD2DGeometrySink:: AddBezier](#addbezier)|Tworzy wartość krzywej Beziera sześciennego między bieżącym punktem a określonym punktem końcowym.|
|[CD2DGeometrySink:: AddBeziers](#addbeziers)|Tworzy sekwencję okrągłych krzywych Beziera i dodaje je do ujścia geometrycznego.|
|[CD2DGeometrySink:: AddLine](#addline)|Tworzy segment linii między bieżącym punktem a określonym punktem końcowym i dodaje go do ujścia geometrycznego.|
|[CD2DGeometrySink:: AddLines](#addlines)|Tworzy sekwencję wierszy przy użyciu określonych punktów i dodaje je do ujścia geometrycznego.|
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|Tworzy krzywą Beziera kwadratu między bieżącym punktem a określonym punktem końcowym.|
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|Dodaje sekwencję segmentów krzywej Beziera jako tablicę w pojedynczym wywołaniu.|
|[CD2DGeometrySink::BeginFigure](#beginfigure)|Uruchamia nowy rysunek w określonym punkcie.|
|[CD2DGeometrySink:: Close](#close)|Zamyka ujścia geometrii|
|[CD2DGeometrySink::EndFigure](#endfigure)|Koniec bieżącego rysunku; Opcjonalnie zamyka ją.|
|[CD2DGeometrySink:: Get](#get)|Zwraca interfejs ID2D1GeometrySink|
|[CD2DGeometrySink:: IsValid](#isvalid)|Sprawdza ważność zbiornika geometrii|
|[CD2DGeometrySink:: setfillmode](#setfillmode)|Określa metodę używaną do określania, które punkty znajdują się wewnątrz geometrii opisanej w tym ujścia geometrii i które punkty znajdują się poza.|
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Określa opcje pociągnięcia i sprzężenia, które mają być stosowane do nowych segmentów dodawanych do ujścia geometrycznego.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DGeometrySink:: operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|Zwraca interfejs ID2D1GeometrySink|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DGeometrySink:: m_pSink](#m_psink)|Wskaźnik do elementu ID2D1GeometrySink.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CD2DGeometrySink`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="_dtorcd2dgeometrysink"></a> CD2DGeometrySink:: ~ CD2DGeometrySink

Destruktor. Wywołuje się, gdy obiekt ujścia geometrii D2D jest niszczony.

```
virtual ~CD2DGeometrySink();
```

## <a name="cd2dgeometrysinkaddarc"></a><a name="addarc"></a> CD2DGeometrySink::AddArc

Dodaje pojedynczy łuk do geometrii ścieżki

```cpp
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>Parametry

*podformularz*<br/>
Segment łuku, który ma zostać dodany do rysunku

## <a name="cd2dgeometrysinkaddbezier"></a><a name="addbezier"></a> CD2DGeometrySink:: AddBezier

Tworzy wartość krzywej Beziera sześciennego między bieżącym punktem a określonym punktem końcowym.

```cpp
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Parametry

*Bezier*<br/>
Struktura opisująca punkty kontrolne i punkt końcowy krzywej Beziera do dodania.

## <a name="cd2dgeometrysinkaddbeziers"></a><a name="addbeziers"></a> CD2DGeometrySink:: AddBeziers

Tworzy sekwencję okrągłych krzywych Beziera i dodaje je do ujścia geometrycznego.

```cpp
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Parametry

*elementy Beziera*<br/>
Tablica segmentów Beziera opisująca krzywe Beziera do utworzenia. Krzywa jest rysowana z bieżącego punktu ujścia geometrii (punkt końcowy ostatniego rysowanego segmentu lub lokalizacja określona przez BeginFigure) do punktu końcowego pierwszego segmentu krzywej Beziera w tablicy. Jeśli tablica zawiera dodatkowe segmenty Beziera, każdy kolejny segment Beziera używa punktu końcowego poprzedniego segmentu krzywej Beziera jako punktu początkowego.

## <a name="cd2dgeometrysinkaddline"></a><a name="addline"></a> CD2DGeometrySink:: AddLine

Tworzy segment linii między bieżącym punktem a określonym punktem końcowym i dodaje go do ujścia geometrycznego.

```cpp
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>Parametry

*moment*<br/>
Punkt końcowy linii do narysowania.

## <a name="cd2dgeometrysinkaddlines"></a><a name="addlines"></a> CD2DGeometrySink:: AddLines

Tworzy sekwencję wierszy przy użyciu określonych punktów i dodaje je do ujścia geometrycznego.

```cpp
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>Parametry

*wykrzyknik*<br/>
Tablica zawierająca jeden lub więcej punktów opisujących linie do narysowania. Linia jest rysowana z bieżącego punktu ujścia geometrii (punkt końcowy ostatniego rysowanego segmentu lub lokalizacja określona przez BeginFigure) do pierwszego punktu w tablicy. Jeśli tablica zawiera dodatkowe punkty, linia jest rysowana od pierwszego punktu do drugiego punktu w tablicy, od drugiego punktu do trzeciego punktu itd. Tablica sekwencji punktów końcowych linii do narysowania.

## <a name="cd2dgeometrysinkaddquadraticbezier"></a><a name="addquadraticbezier"></a> CD2DGeometrySink::AddQuadraticBezier

Tworzy krzywą Beziera kwadratu między bieżącym punktem a określonym punktem końcowym.

```cpp
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>Parametry

*Bezier*<br/>
Struktura, która opisuje punkt kontroli i punkt końcowy krzywej Beziera kwadratowego do dodania.

## <a name="cd2dgeometrysinkaddquadraticbeziers"></a><a name="addquadraticbeziers"></a> CD2DGeometrySink::AddQuadraticBeziers

Dodaje sekwencję segmentów krzywej Beziera jako tablicę w pojedynczym wywołaniu.

```cpp
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>Parametry

*elementy Beziera*<br/>
Tablica sekwencji segmentów Beziera kwadratowego.

## <a name="cd2dgeometrysinkbeginfigure"></a><a name="beginfigure"></a> CD2DGeometrySink::BeginFigure

Uruchamia nowy rysunek w określonym punkcie.

```cpp
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>Parametry

*startPoint*<br/>
Punkt, w którym ma zostać rozpoczęty nowy rysunek.

*figureBegin*<br/>
Czy nowy rysunek powinien być pusty czy wypełniony.

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="cd2dgeometrysink"></a> CD2DGeometrySink::CD2DGeometrySink

Konstruuje obiekt CD2DGeometrySink z obiektu CD2DPathGeometry.

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>Parametry

*pathGeometry*<br/>
Istniejący obiekt CD2DPathGeometry.

## <a name="cd2dgeometrysinkclose"></a><a name="close"></a> CD2DGeometrySink:: Close

Zamyka ujścia geometrii

```
BOOL Close();
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie FALSE.

## <a name="cd2dgeometrysinkendfigure"></a><a name="endfigure"></a> CD2DGeometrySink::EndFigure

Koniec bieżącego rysunku; Opcjonalnie zamyka ją.

```cpp
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>Parametry

*figureEnd*<br/>
Wartość wskazująca, czy bieżący rysunek jest zamknięty. Jeśli rysunek jest zamknięty, wiersz jest rysowany między bieżącym punktem a punktem początkowym określonym przez BeginFigure.

## <a name="cd2dgeometrysinkget"></a><a name="get"></a> CD2DGeometrySink:: Get

Zwraca interfejs ID2D1GeometrySink

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1GeometrySink lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dgeometrysinkisvalid"></a><a name="isvalid"></a> CD2DGeometrySink:: IsValid

Sprawdza ważność zbiornika geometrii

```
BOOL IsValid() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli ujścia geometrii jest prawidłowe; w przeciwnym razie FALSE.

## <a name="cd2dgeometrysinkm_psink"></a><a name="m_psink"></a> CD2DGeometrySink:: m_pSink

Wskaźnik do elementu ID2D1GeometrySink.

```
ID2D1GeometrySink* m_pSink;
```

## <a name="cd2dgeometrysinkoperator-id2d1geometrysink"></a><a name="operator_id2d1geometrysink_star"></a> CD2DGeometrySink:: operator ID2D1GeometrySink *

Zwraca interfejs ID2D1GeometrySink

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1GeometrySink lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dgeometrysinksetfillmode"></a><a name="setfillmode"></a> CD2DGeometrySink:: setfillmode

Określa metodę używaną do określania, które punkty znajdują się wewnątrz geometrii opisanej w tym ujścia geometrii i które punkty znajdują się poza.

```cpp
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>Parametry

*FillMode*<br/>
Metoda używana do określenia, czy dany punkt jest częścią geometrii.

## <a name="cd2dgeometrysinksetsegmentflags"></a><a name="setsegmentflags"></a> CD2DGeometrySink::SetSegmentFlags

Określa opcje pociągnięcia i sprzężenia, które mają być stosowane do nowych segmentów dodawanych do ujścia geometrycznego.

```cpp
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>Parametry

*vertexFlags*<br/>
Opcje pociągnięcia i sprzężenia, które mają zostać zastosowane do nowych segmentów dodawanych do ujścia geometrycznego.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

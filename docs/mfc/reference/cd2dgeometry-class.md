---
description: 'Dowiedz się więcej na temat: Klasa CD2DGeometry'
title: Klasa CD2DGeometry
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::Attach
- AFXRENDERTARGET/CD2DGeometry::CombineWithGeometry
- AFXRENDERTARGET/CD2DGeometry::CompareWithGeometry
- AFXRENDERTARGET/CD2DGeometry::ComputeArea
- AFXRENDERTARGET/CD2DGeometry::ComputeLength
- AFXRENDERTARGET/CD2DGeometry::ComputePointAtLength
- AFXRENDERTARGET/CD2DGeometry::Destroy
- AFXRENDERTARGET/CD2DGeometry::Detach
- AFXRENDERTARGET/CD2DGeometry::FillContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Get
- AFXRENDERTARGET/CD2DGeometry::GetBounds
- AFXRENDERTARGET/CD2DGeometry::GetWidenedBounds
- AFXRENDERTARGET/CD2DGeometry::IsValid
- AFXRENDERTARGET/CD2DGeometry::Outline
- AFXRENDERTARGET/CD2DGeometry::Simplify
- AFXRENDERTARGET/CD2DGeometry::StrokeContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Tessellate
- AFXRENDERTARGET/CD2DGeometry::Widen
- AFXRENDERTARGET/CD2DGeometry::m_pGeometry
helpviewer_keywords:
- CD2DGeometry [MFC], CD2DGeometry
- CD2DGeometry [MFC], Attach
- CD2DGeometry [MFC], CombineWithGeometry
- CD2DGeometry [MFC], CompareWithGeometry
- CD2DGeometry [MFC], ComputeArea
- CD2DGeometry [MFC], ComputeLength
- CD2DGeometry [MFC], ComputePointAtLength
- CD2DGeometry [MFC], Destroy
- CD2DGeometry [MFC], Detach
- CD2DGeometry [MFC], FillContainsPoint
- CD2DGeometry [MFC], Get
- CD2DGeometry [MFC], GetBounds
- CD2DGeometry [MFC], GetWidenedBounds
- CD2DGeometry [MFC], IsValid
- CD2DGeometry [MFC], Outline
- CD2DGeometry [MFC], Simplify
- CD2DGeometry [MFC], StrokeContainsPoint
- CD2DGeometry [MFC], Tessellate
- CD2DGeometry [MFC], Widen
- CD2DGeometry [MFC], m_pGeometry
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
ms.openlocfilehash: 2c902554ba5377ce9f7a4a481d4001a9ef7a47f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193451"
---
# <a name="cd2dgeometry-class"></a>Klasa CD2DGeometry

Otoka dla ID2D1Geometry.

## <a name="syntax"></a>Składnia

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|Konstruuje obiekt CD2DGeometry.|
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|Destruktor. Wywołuje się, gdy obiekt geometrii D2D jest niszczony.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DGeometry:: Attach](#attach)|Dołącza istniejący interfejs zasobów do obiektu|
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|Łączy tę geometrię z określoną geometrią i zapisuje wynik w ID2D1SimplifiedGeometrySink.|
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|Opisuje wspólną część między tą geometrią i określoną geometrią. Porównanie jest wykonywane przy użyciu określonej tolerancji spłaszczania.|
|[CD2DGeometry::ComputeArea](#computearea)|Oblicza obszar geometrii, gdy został on przekształcony przez określoną macierz i spłaszczony przy użyciu określonej tolerancji.|
|[CD2DGeometry::ComputeLength](#computelength)|Oblicza długość geometrii, tak jakby każdy segment był nieprzetworzony w wierszu.|
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|Oblicza wektor punktów i styczności w określonej odległości wzdłuż geometrii, gdy został on przekształcony przez określoną macierz i spłaszczony przy użyciu określonej tolerancji.|
|[CD2DGeometry::D Estroy](#destroy)|Niszczy obiekt CD2DGeometry. (Przesłania [CD2DResource::D Estroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DGeometry::D etach](#detach)|Odłącza interfejs zasobów od obiektu|
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|Wskazuje, czy obszar wypełniony przez geometrię będzie zawierać określony punkt z określoną tolerancją spłaszczania.|
|[CD2DGeometry:: Get](#get)|Zwraca interfejs ID2D1Geometry|
|[CD2DGeometry:: GetBounds](#getbounds)||
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|Pobiera granice geometrii po jej pobraniu o określoną szerokość i styl obrysu i przekształcony przez określoną macierz.|
|[CD2DGeometry:: IsValid](#isvalid)|Sprawdza poprawność zasobów (Przesłania [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)).|
|[CD2DGeometry:: konspekt](#outline)|Oblicza kontur geometrii i zapisuje wynik w ID2D1SimplifiedGeometrySink.|
|[CD2DGeometry:: Uprość](#simplify)|Tworzy uproszczoną wersję geometrii, która zawiera tylko wiersze i (opcjonalnie) krzywe Beziera sześciennego i zapisuje wynik do ID2D1SimplifiedGeometrySink.|
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|Określa, czy naciśnięcie geometrii zawiera określony punkt o określonej grubości, stylu i transformacji.|
|[CD2DGeometry::Tessellate](#tessellate)|Tworzy zestaw trójkątów ubocznych z ruchem wskazówek zegara, które obejmują geometrię, gdy zostanie on przekształcony przy użyciu określonej macierzy i spłaszczony przy użyciu określonej tolerancji.|
|[CD2DGeometry:: rozszerzając](#widen)|Rozszerza geometrię o określony pociągnięcie i zapisuje wynik do ID2D1SimplifiedGeometrySink, gdy zostanie on przekształcony przez określoną macierz i spłaszczony przy użyciu określonej tolerancji.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DGeometry:: operator ID2D1Geometry *](#operator_id2d1geometry_star)|Zwraca interfejs ID2D1Geometry|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DGeometry:: m_pGeometry](#m_pgeometry)|Wskaźnik do elementu ID2D1Geometry.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dgeometrycd2dgeometry"></a><a name="_dtorcd2dgeometry"></a> CD2DGeometry:: ~ CD2DGeometry

Destruktor. Wywołuje się, gdy obiekt geometrii D2D jest niszczony.

```
virtual ~CD2DGeometry();
```

## <a name="cd2dgeometryattach"></a><a name="attach"></a> CD2DGeometry:: Attach

Dołącza istniejący interfejs zasobów do obiektu

```cpp
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>Parametry

*Źródło*<br/>
Istniejący interfejs zasobów. Nie może mieć wartości NULL

## <a name="cd2dgeometrycd2dgeometry"></a><a name="cd2dgeometry"></a> CD2DGeometry::CD2DGeometry

Konstruuje obiekt CD2DGeometry.

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

## <a name="cd2dgeometrycombinewithgeometry"></a><a name="combinewithgeometry"></a> CD2DGeometry::CombineWithGeometry

Łączy tę geometrię z określoną geometrią i zapisuje wynik w ID2D1SimplifiedGeometrySink.

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*inputGeometry*<br/>
Geometria do połączenia z tym wystąpieniem.

*Funkcja CombineMode*<br/>
Typ operacji łączenia do wykonania.

*inputGeometryTransform*<br/>
Transformacja, która ma zostać zastosowana do inputGeometry przed połączeniem.

*geometrySink*<br/>
Wynik operacji łączenia.

*flatteningTolerance*<br/>
Maksymalna granica odległości między punktami w przybliżeniu wielokąta geometrie. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometrycomparewithgeometry"></a><a name="comparewithgeometry"></a> CD2DGeometry::CompareWithGeometry

Opisuje wspólną część między tą geometrią i określoną geometrią. Porównanie jest wykonywane przy użyciu określonej tolerancji spłaszczania.

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*inputGeometry*<br/>
Geometria do przetestowania.

*inputGeometryTransform*<br/>
Transformacja, która ma zostać zastosowana do inputGeometry.

*flatteningTolerance*<br/>
Maksymalna granica odległości między punktami w przybliżeniu wielokąta geometrie. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometrycomputearea"></a><a name="computearea"></a> CD2DGeometry::ComputeArea

Oblicza obszar geometrii, gdy został on przekształcony przez określoną macierz i spłaszczony przy użyciu określonej tolerancji.

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*worldTransform*<br/>
Transformacja, która ma zostać zastosowana do tej geometrii przed rozpoczęciem przetwarzania jej obszaru.

*stref*<br/>
Gdy ta metoda zwraca, zawiera wskaźnik do obszaru przekształconej, spłaszczonej wersji tej geometrii. Należy przydzielić magazyn dla tego parametru.

*flatteningTolerance*<br/>
Maksymalna granica odległości między punktami w przybliżeniu wielokąta geometrii. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometrycomputelength"></a><a name="computelength"></a> CD2DGeometry::ComputeLength

Oblicza długość geometrii, tak jakby każdy segment był nieprzetworzony w wierszu.

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*worldTransform*<br/>
Transformacja, która ma zostać zastosowana do geometrii przed obliczeniem jej długości.

*length*<br/>
Gdy ta metoda zwraca, zawiera wskaźnik do długości geometrii. W przypadku zamkniętych geometrie długość zawiera niejawny segment zamykający. Należy przydzielić magazyn dla tego parametru.

*flatteningTolerance*<br/>
Maksymalna granica odległości między punktami w przybliżeniu wielokąta geometrii. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometrycomputepointatlength"></a><a name="computepointatlength"></a> CD2DGeometry::ComputePointAtLength

Oblicza wektor punktów i styczności w określonej odległości wzdłuż geometrii, gdy został on przekształcony przez określoną macierz i spłaszczony przy użyciu określonej tolerancji.

```
BOOL ComputePointAtLength(
    FLOAT length,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DPointF& point,
    CD2DPointF& unitTangentVector,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*length*<br/>
Odległość wzdłuż geometrii punktu i tangensa do znalezienia. Jeśli ta odległość jest mniejsza niż 0, ta metoda oblicza pierwszy punkt w geometrii. Jeśli ta odległość jest większa niż długość geometrii, ta metoda oblicza ostatni punkt w geometrii.

*worldTransform*<br/>
Transformacja, która ma zostać zastosowana do geometrii przed obliczeniem określonego punktu i tangensa.

*moment*<br/>
Lokalizacja w określonej odległości wzdłuż geometrii. Jeśli geometria jest pusta, ten punkt zawiera NaN jako wartości x i y.

*unitTangentVector*<br/>
Gdy ta metoda zwraca, zawiera wskaźnik do wektora stycznego w określonej odległości i geometrii. Jeśli geometria jest pusta, ten wektor zawiera NaN jako wartości x i y. Należy przydzielić magazyn dla tego parametru.

*flatteningTolerance*<br/>
Maksymalna granica odległości między punktami w przybliżeniu wielokąta geometrii. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometrydestroy"></a><a name="destroy"></a> CD2DGeometry::D Estroy

Niszczy obiekt CD2DGeometry.

```
virtual void Destroy();
```

## <a name="cd2dgeometrydetach"></a><a name="detach"></a> CD2DGeometry::D etach

Odłącza interfejs zasobów od obiektu

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu zasobu.

## <a name="cd2dgeometryfillcontainspoint"></a><a name="fillcontainspoint"></a> CD2DGeometry::FillContainsPoint

Wskazuje, czy obszar wypełniony przez geometrię będzie zawierać określony punkt z określoną tolerancją spłaszczania.

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*moment*<br/>
Punkt do przetestowania.

*worldTransform*<br/>
Transformacja, która ma zostać zastosowana do geometrii przed testowaniem w celu zawierania.

*wyświetlana*<br/>
Gdy ta metoda zwraca, zawiera wartość logiczną PRAWDA, jeśli obszar wypełniony przez geometrię zawiera punkt; w przeciwnym razie FALSE. Należy przydzielić magazyn dla tego parametru.

*flatteningTolerance*<br/>
Dokładność liczbowa, z którą jest obliczana dokładna ścieżka geometryczna i przecięcie ścieżki. Punkty, w których brakuje wypełnienia o wartości mniejszej niż tolerancja, są nadal uznawane za wewnątrz. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometryget"></a><a name="get"></a> CD2DGeometry:: Get

Zwraca interfejs ID2D1Geometry

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1Geometry lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dgeometrygetbounds"></a><a name="getbounds"></a> CD2DGeometry:: GetBounds

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>Parametry

*worldTransform*<br/>
*granice*

### <a name="return-value"></a>Wartość zwracana

## <a name="cd2dgeometrygetwidenedbounds"></a><a name="getwidenedbounds"></a> CD2DGeometry::GetWidenedBounds

Pobiera granice geometrii po jej pobraniu o określoną szerokość i styl obrysu i przekształcony przez określoną macierz.

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*strokeWidth*<br/>
Wartość, według której ma zostać poszerzona geometria, przez obrysowywanie jej konspektu.

*pociągnięcie*<br/>
Styl pociągnięcia, który poszerza geometrię.

*worldTransform*<br/>
Transformacja, która ma zostać zastosowana do geometrii po przekształceniu geometrii, i po pociągnięcia geometrii.

*granice*<br/>
Gdy ta metoda zwraca, zawiera granice rozszerzonej geometrii. Należy przydzielić magazyn dla tego parametru.

*flatteningTolerance*<br/>
Maksymalna granica odległości między punktami w przybliżeniu wielokąta geometrie. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometryisvalid"></a><a name="isvalid"></a> CD2DGeometry:: IsValid

Sprawdza poprawność zasobów

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli zasób jest prawidłowy; w przeciwnym razie FALSE.

## <a name="cd2dgeometrym_pgeometry"></a><a name="m_pgeometry"></a> CD2DGeometry:: m_pGeometry

Wskaźnik do elementu ID2D1Geometry.

```
ID2D1Geometry* m_pGeometry;
```

## <a name="cd2dgeometryoperator-id2d1geometry"></a><a name="operator_id2d1geometry_star"></a> CD2DGeometry:: operator ID2D1Geometry *

Zwraca interfejs ID2D1Geometry

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu ID2D1Geometry lub NULL, jeśli obiekt nie jest jeszcze zainicjowany.

## <a name="cd2dgeometryoutline"></a><a name="outline"></a> CD2DGeometry:: konspekt

Oblicza kontur geometrii i zapisuje wynik w ID2D1SimplifiedGeometrySink.

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*worldTransform*<br/>
Transformacja, która ma zostać zastosowana do konspektu geometrii.

*geometrySink*<br/>
ID2D1SimplifiedGeometrySink, do którego jest dołączany kontur przekształcony na geometrię.

*flatteningTolerance*<br/>
Maksymalna granica odległości między punktami w przybliżeniu wielokąta geometrii. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometrysimplify"></a><a name="simplify"></a> CD2DGeometry:: Uprość

Tworzy uproszczoną wersję geometrii, która zawiera tylko wiersze i (opcjonalnie) krzywe Beziera sześciennego i zapisuje wynik do ID2D1SimplifiedGeometrySink.

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*simplificationOption*<br/>
Wartość określająca, czy uproszczona geometria powinna zawierać krzywe.

*worldTransform*<br/>
Transformacja, która ma zostać zastosowana do uproszczonej geometrii.

*geometrySink*<br/>
ID2D1SimplifiedGeometrySink, do którego jest dołączana uproszczona geometria.

*flatteningTolerance*<br/>
Maksymalna granica odległości między punktami w przybliżeniu wielokąta geometrii. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometrystrokecontainspoint"></a><a name="strokecontainspoint"></a> CD2DGeometry::StrokeContainsPoint

Określa, czy naciśnięcie geometrii zawiera określony punkt o określonej grubości, stylu i transformacji.

```
BOOL StrokeContainsPoint(
    CD2DPointF point,
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*moment*<br/>
Punkt do testowania zawierania.

*strokeWidth*<br/>
Grubość pociągnięcia, która ma zostać zastosowana.

*pociągnięcie*<br/>
Styl pociągnięcia, który ma zostać zastosowany.

*worldTransform*<br/>
Transformacja, która ma zostać zastosowana do pociągnięcia geometrycznego.

*wyświetlana*<br/>
Gdy ta metoda zwraca, zawiera wartość Boolean ustawioną na wartość TRUE, jeśli obrys geometrii zawiera określony punkt; w przeciwnym razie FALSE. Należy przydzielić magazyn dla tego parametru.

*flatteningTolerance*<br/>
Dokładność liczbowa, z którą jest obliczana dokładna ścieżka geometryczna i przecięcie ścieżki. Punkty, w których brakuje pociągnięcia o wartości mniejszej niż tolerancja, są nadal uznawane za wewnątrz. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometrytessellate"></a><a name="tessellate"></a> CD2DGeometry::Tessellate

Tworzy zestaw trójkątów ubocznych z ruchem wskazówek zegara, które obejmują geometrię, gdy zostanie on przekształcony przy użyciu określonej macierzy i spłaszczony przy użyciu określonej tolerancji.

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*worldTransform*<br/>
Transformacja, która ma zostać zastosowana do tej geometrii, lub wartość NULL.

*tessellationSink*<br/>
ID2D1TessellationSink, do którego jest dołączany tessellated.

*flatteningTolerance*<br/>
Maksymalna granica odległości między punktami w przybliżeniu wielokąta geometrii. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="cd2dgeometrywiden"></a><a name="widen"></a> CD2DGeometry:: rozszerzając

Rozszerza geometrię o określony pociągnięcie i zapisuje wynik do ID2D1SimplifiedGeometrySink, gdy zostanie on przekształcony przez określoną macierz i spłaszczony przy użyciu określonej tolerancji.

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>Parametry

*strokeWidth*<br/>
Wartość, według której ma zostać poszerzona geometria.

*pociągnięcie*<br/>
Styl pociągnięcia, który ma zostać zastosowany do geometrii lub wartość NULL.

*worldTransform*<br/>
Transformacja, która ma zostać zastosowana do geometrii po jej poszerzeniu.

*geometrySink*<br/>
ID2D1SimplifiedGeometrySink, do którego jest dołączana poszerzona geometria.

*flatteningTolerance*<br/>
Maksymalna granica odległości między punktami w przybliżeniu wielokąta geometrii. Mniejsze wartości dają dokładniejsze wyniki, ale powodują wolniejsze wykonywanie.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

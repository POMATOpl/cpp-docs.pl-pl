---
description: 'Dowiedz się więcej na temat: Klasa CD2DPathGeometry'
title: Klasa CD2DPathGeometry
ms.date: 11/04/2016
f1_keywords:
- CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::Attach
- AFXRENDERTARGET/CD2DPathGeometry::Create
- AFXRENDERTARGET/CD2DPathGeometry::Destroy
- AFXRENDERTARGET/CD2DPathGeometry::Detach
- AFXRENDERTARGET/CD2DPathGeometry::GetFigureCount
- AFXRENDERTARGET/CD2DPathGeometry::GetSegmentCount
- AFXRENDERTARGET/CD2DPathGeometry::Open
- AFXRENDERTARGET/CD2DPathGeometry::Stream
- AFXRENDERTARGET/CD2DPathGeometry::m_pPathGeometry
helpviewer_keywords:
- CD2DPathGeometry [MFC], CD2DPathGeometry
- CD2DPathGeometry [MFC], Attach
- CD2DPathGeometry [MFC], Create
- CD2DPathGeometry [MFC], Destroy
- CD2DPathGeometry [MFC], Detach
- CD2DPathGeometry [MFC], GetFigureCount
- CD2DPathGeometry [MFC], GetSegmentCount
- CD2DPathGeometry [MFC], Open
- CD2DPathGeometry [MFC], Stream
- CD2DPathGeometry [MFC], m_pPathGeometry
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
ms.openlocfilehash: eb33d498436c887eb038b3312e2b98ca04d6620b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280537"
---
# <a name="cd2dpathgeometry-class"></a>Klasa CD2DPathGeometry

Otoka dla ID2D1PathGeometry.

## <a name="syntax"></a>Składnia

```
class CD2DPathGeometry : public CD2DGeometry;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DPathGeometry::CD2DPathGeometry](#cd2dpathgeometry)|Konstruuje obiekt CD2DPathGeometry.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CD2DPathGeometry:: Attach](#attach)|Dołącza istniejący interfejs zasobów do obiektu|
|[CD2DPathGeometry:: Create](#create)|Tworzy element CD2DPathGeometry. (Przesłania [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DPathGeometry::D Estroy](#destroy)|Niszczy obiekt CD2DPathGeometry. (Przesłania [CD2DGeometry::D Estroy](../../mfc/reference/cd2dgeometry-class.md#destroy).)|
|[CD2DPathGeometry::D etach](#detach)|Odłącza interfejs zasobów od obiektu|
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|Pobiera liczbę cyfr w geometrii ścieżki.|
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|Pobiera liczbę segmentów w geometrii ścieżki.|
|[CD2DPathGeometry:: Open](#open)|Pobiera obiekt sink geometryczny, który jest używany do wypełniania geometrii ścieżki z ilustracjami i segmentami.|
|[CD2DPathGeometry:: Stream](#stream)|Kopiuje zawartość geometrii ścieżki do określonego ID2D1GeometrySink.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CD2DPathGeometry:: m_pPathGeometry](#m_ppathgeometry)|Wskaźnik do elementu ID2D1PathGeometry.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)

`CD2DPathGeometry`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxrendertarget. h

## <a name="cd2dpathgeometryattach"></a><a name="attach"></a> CD2DPathGeometry:: Attach

Dołącza istniejący interfejs zasobów do obiektu

```cpp
void Attach(ID2D1PathGeometry* pResource);
```

### <a name="parameters"></a>Parametry

*Źródło*<br/>
Istniejący interfejs zasobów. Nie może mieć wartości NULL

## <a name="cd2dpathgeometrycd2dpathgeometry"></a><a name="cd2dpathgeometry"></a> CD2DPathGeometry::CD2DPathGeometry

Konstruuje obiekt CD2DPathGeometry.

```
CD2DPathGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parametry

*pParentTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

*bAutoDestroy*<br/>
Wskazuje, że obiekt zostanie zniszczony przez właściciela (pParentTarget).

## <a name="cd2dpathgeometrycreate"></a><a name="create"></a> CD2DPathGeometry:: Create

Tworzy element CD2DPathGeometry.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parametry

*pRenderTarget*<br/>
Wskaźnik do elementu docelowego renderowania.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca S_OK. W przeciwnym razie zwraca kod błędu HRESULT.

## <a name="cd2dpathgeometrydestroy"></a><a name="destroy"></a> CD2DPathGeometry::D Estroy

Niszczy obiekt CD2DPathGeometry.

```
virtual void Destroy();
```

## <a name="cd2dpathgeometrydetach"></a><a name="detach"></a> CD2DPathGeometry::D etach

Odłącza interfejs zasobów od obiektu

```
ID2D1PathGeometry* Detach();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do odłączonego interfejsu zasobu.

## <a name="cd2dpathgeometrygetfigurecount"></a><a name="getfigurecount"></a> CD2DPathGeometry::GetFigureCount

Pobiera liczbę cyfr w geometrii ścieżki.

```
int GetFigureCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę cyfr w geometrii ścieżki.

## <a name="cd2dpathgeometrygetsegmentcount"></a><a name="getsegmentcount"></a> CD2DPathGeometry::GetSegmentCount

Pobiera liczbę segmentów w geometrii ścieżki.

```
int GetSegmentCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę segmentów w geometrii ścieżki.

## <a name="cd2dpathgeometrym_ppathgeometry"></a><a name="m_ppathgeometry"></a> CD2DPathGeometry:: m_pPathGeometry

Wskaźnik do elementu ID2D1PathGeometry.

```
ID2D1PathGeometry* m_pPathGeometry;
```

## <a name="cd2dpathgeometryopen"></a><a name="open"></a> CD2DPathGeometry:: Open

Pobiera obiekt sink geometryczny, który jest używany do wypełniania geometrii ścieżki z ilustracjami i segmentami.

```
ID2D1GeometrySink* Open();
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do ID2D1GeometrySink, który jest używany do wypełniania geometrii ścieżki z ilustracjami i segmentami.

## <a name="cd2dpathgeometrystream"></a><a name="stream"></a> CD2DPathGeometry:: Stream

Kopiuje zawartość geometrii ścieżki do określonego ID2D1GeometrySink.

```
BOOL Stream(ID2D1GeometrySink* geometrySink);
```

### <a name="parameters"></a>Parametry

*geometrySink*<br/>
Ujścia, do którego kopiowana jest zawartość geometrii ścieżki. Modyfikacja tego ujścia nie zmienia zawartości tej ścieżki geometrycznej.

### <a name="return-value"></a>Wartość zwracana

Jeśli metoda się powiedzie, zwraca wartość TRUE. W przeciwnym razie zwraca wartość FALSE.

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonProgressBar'
title: Klasa CMFCRibbonProgressBar
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
ms.openlocfilehash: b4e91a604386a57aa7cac59294c569635583304c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321764"
---
# <a name="cmfcribbonprogressbar-class"></a>Klasa CMFCRibbonProgressBar

Implementuje formant, który wizualnie wskazuje postęp długotrwałej operacji.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Konstruuje i inicjuje `CMFCRibbonProgressBar` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonProgressBar::GetPos](#getpos)|Zwraca bieżący postęp.|
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Zwraca maksymalną wartość bieżącego zakresu.|
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Zwraca minimalną wartość bieżącego zakresu.|
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Zwraca zwykły rozmiar elementu wstążki. (Przesłania [CMFCRibbonBaseElement:: GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonProgressBar:: IsInfinite](#isinfinitemode)|Określa, czy pasek postępu działa w trybie nieskończonym.|
|[CMFCRibbonProgressBar:: OnDraw](#ondraw)|Wywoływane przez platformę, by narysować element wstążki. (Przesłania [CMFCRibbonBaseElement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCRibbonProgressBar:: setinfinite](#setinfinitemode)|Ustawia pasek postępu, aby działał w trybie nieskończoności.|
|[CMFCRibbonProgressBar::SetPos](#setpos)|Ustawia bieżący postęp.|
|[CMFCRibbonProgressBar:: SetRange](#setrange)|Ustawia wartości minimalne i maksymalne.|

## <a name="remarks"></a>Uwagi

A `CMFCRibbonProgressBar` może działać w dwóch trybach: zwykła i nieskończona. W trybie regularnym pasek postępu jest wypełniany od lewej do prawej i zostaje zatrzymany, gdy osiągnie wartość maksymalną. W trybie nieskończonym pasek postępu jest wielokrotnie wypełniany od wartości minimalnej do wartości maksymalnej. Możesz użyć trybu nieskończonego, aby wskazać, że operacja jest w toku, ale czas zakończenia jest nieznany.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCRibbonProgressBar` klasie. W przykładzie pokazano, jak ustawić pasek postępu w tryb nieskończony (w którym jest nieznany czas zakończenia operacji), ustawić wartości minimalne i maksymalne dla paska postępu i ustawić bieżącą pozycję paska postępu. Ten fragment kodu jest częścią [przykładu demonstracyjnego pakietu MS Office 2007](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxRibbonProgressBar. h

## <a name="cmfcribbonprogressbarcmfcribbonprogressbar"></a><a name="cmfcribbonprogressbar"></a> CMFCRibbonProgressBar::CMFCRibbonProgressBar

Tworzy i inicjuje obiekt [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) .

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>Parametry

*nID*<br/>
podczas Określa identyfikator polecenia dla paska postępu wstążki.

*nWidth*<br/>
podczas Określa szerokość (w pikselach) paska postępu wstążki.

*nHeight*<br/>
podczas Określa wysokość (w pikselach) paska postępu wstążki.

## <a name="cmfcribbonprogressbargetpos"></a><a name="getpos"></a> CMFCRibbonProgressBar::GetPos

Zwraca bieżącą pozycję paska postępu.

```
int GetPos () const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość reprezentująca bieżącą pozycję paska postępu.

### <a name="remarks"></a>Uwagi

Ustawiany zakres musi znajdować się w zakresie określonym przez metodę [CMFCRibbonProgressBar:: SetRange](#setrange) .

## <a name="cmfcribbonprogressbargetrangemax"></a><a name="getrangemax"></a> CMFCRibbonProgressBar::GetRangeMax

Zwraca bieżącą wartość maksymalną paska postępu.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość maksymalna bieżącego zakresu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonprogressbargetrangemin"></a><a name="getrangemin"></a> CMFCRibbonProgressBar::GetRangeMin

Zwraca bieżącą wartość minimalnego zakresu paska postępu.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość minimalna bieżącego zakresu.

## <a name="cmfcribbonprogressbargetregularsize"></a><a name="getregularsize"></a> CMFCRibbonProgressBar::GetRegularSize

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametry

podczas *kontroler PDC*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonprogressbarisinfinitemode"></a><a name="isinfinitemode"></a> CMFCRibbonProgressBar:: IsInfinite

Określa, czy pasek postępu działa w trybie nieskończonym.

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli pasek postępu jest w trybie nieskończonym; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

W trybie nieskończonym pasek postępu jest wypełniany wielokrotnie od wartości minimalnej do wartości maksymalnej. Możesz użyć trybu nieskończonego, aby wskazać, że operacja jest w toku, ale czas zakończenia jest nieznany.

## <a name="cmfcribbonprogressbarondraw"></a><a name="ondraw"></a> CMFCRibbonProgressBar:: OnDraw

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametry

podczas *kontroler PDC*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonprogressbarsetinfinitemode"></a><a name="setinfinitemode"></a> CMFCRibbonProgressBar:: setinfinite

Ustawia pasek postępu, aby działał w trybie nieskończoności.

```cpp
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametry

*bSet*<br/>
podczas PRAWDA, aby określić, że pasek postępu jest w trybie nieskończonym; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Zazwyczaj Jeśli pasek postępu jest w trybie nieskończonym, informuje użytkownika, że operacja jest w toku, ale czas zakończenia jest nieznany. W ten sposób pasek postępu jest wielokrotnie wypełniany od wartości minimalnej do wartości maksymalnej.

## <a name="cmfcribbonprogressbarsetpos"></a><a name="setpos"></a> CMFCRibbonProgressBar::SetPos

Ustawia bieżącą pozycję paska postępu.

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametry

*nPos*<br/>
podczas Określa pozycję, do której jest ustawiony pasek postępu.

*bRedraw*<br/>
podczas Określa, czy pasek postępu powinien być rysowany ponownie.

### <a name="remarks"></a>Uwagi

Ustawiany zakres musi znajdować się w zakresie określonym przez metodę [CMFCRibbonProgressBar:: SetRange](#setrange) .

## <a name="cmfcribbonprogressbarsetrange"></a><a name="setrange"></a> CMFCRibbonProgressBar:: SetRange

Ustawia wartości minimalne i maksymalne na pasku postępu.

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametry

*nMin*<br/>
podczas Określa minimalną wartość zakresu.

*Nmaks.*<br/>
podczas Określa maksymalną wartość zakresu.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby zdefiniować zakres paska postępu, ustawiając wartości minimalne i maksymalne.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[Klasa CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)

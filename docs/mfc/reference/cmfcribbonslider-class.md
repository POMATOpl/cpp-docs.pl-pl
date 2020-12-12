---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonSlider'
title: Klasa CMFCRibbonSlider
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
helpviewer_keywords:
- CMFCRibbonSlider [MFC], CMFCRibbonSlider
- CMFCRibbonSlider [MFC], GetPos
- CMFCRibbonSlider [MFC], GetRangeMax
- CMFCRibbonSlider [MFC], GetRangeMin
- CMFCRibbonSlider [MFC], GetRegularSize
- CMFCRibbonSlider [MFC], GetZoomIncrement
- CMFCRibbonSlider [MFC], HasZoomButtons
- CMFCRibbonSlider [MFC], OnDraw
- CMFCRibbonSlider [MFC], SetPos
- CMFCRibbonSlider [MFC], SetRange
- CMFCRibbonSlider [MFC], SetZoomButtons
- CMFCRibbonSlider [MFC], SetZoomIncrement
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
ms.openlocfilehash: d125afdf961d97c0501742acdc75d7802c7e104d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321737"
---
# <a name="cmfcribbonslider-class"></a>Klasa CMFCRibbonSlider

`CMFCRibbonSlider`Klasa implementuje kontrolkę suwaka, którą można dodać do paska wstążki lub paska stanu wstążki. Kontrolka suwaka jest podobna do suwaków powiększenia, które pojawiają się w aplikacjach pakietu Office 2007.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonSlider : public CMFCRibbonBaseElement
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|Tworzy i inicjuje kontrolkę suwaka wstążki.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonSlider::GetPos](#getpos)|Zwraca bieżącą pozycję kontrolki suwaka.|
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|Zwraca maksymalną wartość suwaka.|
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|Zwraca minimalną wartość suwaka.|
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|Zwraca zwykły rozmiar elementu wstążki. (Przesłania [CMFCRibbonBaseElement:: GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|Zwraca rozmiar przyrostu powiększenia kontrolki suwaka.|
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|Określa, czy suwak ma Przyciski powiększenia.|
|[CMFCRibbonSlider:: OnDraw](#ondraw)|Wywoływane przez platformę, by narysować element wstążki. (Przesłania [CMFCRibbonBaseElement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCRibbonSlider::SetPos](#setpos)|Ustawia bieżącą pozycję kontrolki suwaka.|
|[CMFCRibbonSlider:: SetRange](#setrange)|Określa zakres kontrolki suwaka, ustawiając wartości minimalne i maksymalne.|
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|Pokazuje lub ukrywa Przyciski powiększenia.|
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|Ustawia rozmiar przyrostu powiększenia dla kontrolki suwaka.|

## <a name="remarks"></a>Uwagi

Możesz użyć metody, `SetRange` Aby skonfigurować zakres przyrostów powiększenia dla suwaka. Możesz ustawić bieżące położenie suwaka przy użyciu `SetPos` metody.

Możesz wyświetlić przyciski powiększania cyklicznego po lewej i prawej stronie kontrolki suwaka przy użyciu `SetZoomButtons` metody. Domyślnie suwak jest poziomy, a lewy przycisk powiększenie wyświetla znak minus, a prawy przycisk powiększenie wyświetla znak plus.

`SetZoomIncrement`Metoda definiuje przyrost do dodania lub odejmowania od bieżącego położenia, gdy użytkownik kliknie Przyciski powiększenia.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCRibbonSlider` klasie w celu ustawienia właściwości suwaka. W przykładzie pokazano, jak utworzyć `CMFCRibbonSlider` obiekt, wyświetlić przyciski powiększenia, ustawić bieżącą pozycję kontrolki suwaka i ustawić zakres wartości dla kontrolki suwak.

[!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxribbonslider. h

## <a name="cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a> CMFCRibbonSlider::CMFCRibbonSlider

Utwórz suwak wstążki.

```
CMFCRibbonSlider(
    UINT nID,
    int nWidth=100);
```

### <a name="parameters"></a>Parametry

*nID*<br/>
podczas Identyfikator suwaka.

[in]. *nWidth* Szerokość suwaka (w pikselach).

### <a name="remarks"></a>Uwagi

Konstruuje suwak wstążki, który jest *nWidth* pikseli w kategorii panelu, do której dodano suwak. Domyślnie suwak jest poziomy.

## <a name="cmfcribbonslidergetpos"></a><a name="getpos"></a> CMFCRibbonSlider::GetPos

Zwraca bieżącą pozycję kontrolki suwaka.

```
int GetPos() const;
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca pozycja kontrolki suwaka, która jest pozycją względem początku suwaka.

## <a name="cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a> CMFCRibbonSlider::GetRangeMax

Uzyskuje maksymalne zwiększenie suwaka, które suwak może obsłużyć na kontrolce suwaka.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Wartość zwracana

Maksymalne zwiększenie suwaka, które suwak może obsłużyć na kontrolce suwaka.

## <a name="cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a> CMFCRibbonSlider::GetRangeMin

Zwraca minimalny przyrost, który suwak może obsłużyć na kontrolce suwaka.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Wartość zwracana

Minimalny przyrost, jaki suwak może obsłużyć na kontrolce suwaka.

## <a name="cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a> CMFCRibbonSlider::GetRegularSize

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametry

podczas *kontroler PDC*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a> CMFCRibbonSlider::GetZoomIncrement

Uzyskaj przyrost powiększenia dla kontrolki suwaka.

```
int GetZoomIncrement() const;
```

### <a name="return-value"></a>Wartość zwracana

Przyrost powiększenia kontrolki suwaka.

## <a name="cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a> CMFCRibbonSlider::HasZoomButtons

Określa, czy suwak ma Przyciski powiększenia.

```
BOOL HasZoomButtons() const;
```

### <a name="return-value"></a>Wartość zwracana

TRUE, jeśli suwak ma Przyciski powiększenia; W przeciwnym razie zwraca wartość FALSE.

## <a name="cmfcribbonsliderondraw"></a><a name="ondraw"></a> CMFCRibbonSlider:: OnDraw

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametry

podczas *kontroler PDC*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonslidersetpos"></a><a name="setpos"></a> CMFCRibbonSlider::SetPos

Ustaw bieżące położenie kontrolki suwaka.

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametry

*nPos*<br/>
podczas Określa pozycję ustawioną dla suwaka. Pozycja jest względem początku suwaka.

*bRedraw*<br/>
podczas W przypadku wartości TRUE suwak zostanie narysowany ponownie.

## <a name="cmfcribbonslidersetrange"></a><a name="setrange"></a> CMFCRibbonSlider:: SetRange

Ustaw zakres wartości dla kontrolki suwak.

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametry

*nMin*<br/>
podczas Określa minimalną wartość kontrolki suwaka.

*Nmaks.*<br/>
podczas Określa maksymalną wartość kontrolki suwaka.

### <a name="remarks"></a>Uwagi

Określa zakres wartości kontrolki suwaka, ustawiając wartości minimalne i maksymalne.

## <a name="cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a> CMFCRibbonSlider::SetZoomButtons

Wyświetla lub ukrywa Przyciski powiększenia.

```cpp
void SetZoomButtons(BOOL bSet=TRUE);
```

### <a name="parameters"></a>Parametry

[in]. *bSet* PRAWDA, aby wyświetlić przyciski powiększenia; Wartość FALSE, aby je ukryć.

## <a name="cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a> CMFCRibbonSlider::SetZoomIncrement

Ustaw przyrost powiększenia dla kontrolki suwaka.

```cpp
void SetZoomIncrement(int nZoomIncrement);
```

### <a name="parameters"></a>Parametry

*nZoomIncrement*<br/>
podczas Określa przyrost powiększenia kontrolki suwaka.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

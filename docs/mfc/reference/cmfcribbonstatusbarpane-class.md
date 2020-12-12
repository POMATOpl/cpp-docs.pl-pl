---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonStatusBarPane'
title: Klasa CMFCRibbonStatusBarPane
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
ms.openlocfilehash: 4ddbee5a6c44411ef2ac34bff3e07b47c3d950a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264989"
---
# <a name="cmfcribbonstatusbarpane-class"></a>Klasa CMFCRibbonStatusBarPane

`CMFCRibbonStatusBarPane`Klasa implementuje element wstążki, który można dodać do paska stanu wstążki.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|Konstruuje i inicjuje `CMFCRibbonStatusBarPane` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](#getalmostlargetext)|Zwraca ciąg, który definiuje najdłuższy ciąg tekstowy, który może być wyświetlany w okienku bez obcinania.|
|[CMFCRibbonStatusBarPane:: TextAlign](#gettextalign)|Zwraca bieżące ustawienie wyrównania tekstu.|
|[CMFCRibbonStatusBarPane:: isanimation](#isanimation)|Określa, czy animacja jest w toku.|
|[CMFCRibbonStatusBarPane:: isextended](#isextended)|Określa, czy okienko znajduje się w rozszerzonym obszarze paska stanu wstążki.|
|[CMFCRibbonStatusBarPane::OnDrawBorder](#ondrawborder)|(Przesłania [CMFCRibbonButton:: OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|
|[CMFCRibbonStatusBarPane::OnFillBackground](#onfillbackground)|(Przesłania [CMFCRibbonButton:: OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](#setalmostlargetext)|Definiuje najdłuższy ciąg tekstowy, który może być wyświetlany w okienku bez obcinania.|
|[CMFCRibbonStatusBarPane::SetAnimationList](#setanimationlist)|Przypisuje do okienka listę obrazów, która może być używana do animacji.|
|[CMFCRibbonStatusBarPane:: TextAlign](#settextalign)|Ustawia wyrównanie tekstu.|
|[CMFCRibbonStatusBarPane::StartAnimation](#startanimation)|Uruchamia animację, która jest przypisana do okienka.|
|[CMFCRibbonStatusBarPane::StopAnimation](#stopanimation)|Powoduje zatrzymanie animacji przypisanej do okienka. .|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonStatusBarPane::OnFinishAnimation](#onfinishanimation)|Wywoływane przez platformę, gdy animacja przypisana do okienka zostanie zatrzymana.|

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCRibbonStatusBarPane` klasie. W przykładzie pokazano sposób konstruowania `CMFCRibbonStatusBarPane` obiektu, ustawiania wyrównania tekstu etykiety okienka pasek stanu, definiowania najdłuższego tekstu, który może być wyświetlany w okienku paska stanu bez obcinania, dołączania do okienka pasek stanu listy obrazów, która może być używana do animacji, i uruchamiania animacji.

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxribbonstatusbarpane. h

## <a name="cmfcribbonstatusbarpanecmfcribbonstatusbarpane"></a><a name="cmfcribbonstatusbarpane"></a> CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane

Utwórz obiekt okienka na pasku stanu.

```
CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    BOOL bIsStatic=FALSE,
    HICON hIcon=NULL,
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);
```

### <a name="parameters"></a>Parametry

*nCmdID*<br/>
podczas Określa identyfikator polecenia okienka.

*lpszText*<br/>
podczas Określa ciąg tekstowy, który ma być wyświetlany w okienku.

*bIsStatic*<br/>
podczas Jeśli wartość jest równa TRUE, okienko stanu nie może być wyróżnione lub wybrane przez kliknięcie go.

*hIcon*<br/>
podczas Określa dojście do ikony, która ma być wyświetlana w okienku.

*lpszAlmostLargeText*<br/>
podczas Określa najdłuższy ciąg tekstowy, który może być wyświetlany w okienku.

*hBmpAnimationList*<br/>
podczas Określa uchwyt do listy obrazów, który jest używany na potrzeby animacji.

*cxAnimation*<br/>
podczas Określa szerokość (w pikselach) ikony na liście obrazów, która jest używana do animacji.

*clrTrnsp*<br/>
podczas Określa przezroczysty kolor obrazów na liście obrazów, które są używane na potrzeby animacji.

*uiAnimationListResID*<br/>
podczas Określa identyfikator zasobu listy obrazów, który jest używany na potrzeby animacji.

## <a name="cmfcribbonstatusbarpanegetalmostlargetext"></a><a name="getalmostlargetext"></a> CMFCRibbonStatusBarPane::GetAlmostLargeText

Pobiera najdłuższy ciąg tekstowy, który może być wyświetlany w okienku paska stanu.

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>Wartość zwracana

Najdłuższy ciąg tekstowy, który może być wyświetlany w okienku paska stanu.

## <a name="cmfcribbonstatusbarpanegettextalign"></a><a name="gettextalign"></a> CMFCRibbonStatusBarPane:: TextAlign

Pobiera bieżące ustawienie wyrównania tekstu etykiety okienka pasek stanu.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>Wartość zwracana

Bieżące wyrównanie tekstu, które może mieć jedną z następujących wartości:

- TA_LEFT

- TA_CENTER

- TA_RIGHT.

## <a name="cmfcribbonstatusbarpaneisanimation"></a><a name="isanimation"></a> CMFCRibbonStatusBarPane:: isanimation

Określa, czy animacja jest w toku.

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli animacja jest w toku; W przeciwnym razie zwraca wartość FALSE.

## <a name="cmfcribbonstatusbarpaneisextended"></a><a name="isextended"></a> CMFCRibbonStatusBarPane:: isextended

Ustal, czy okienko znajduje się w rozszerzonym obszarze paska stanu wstążki.

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli okienko znajduje się w obszarze rozszerzonym paska stanu. W przeciwnym razie zwraca wartość FALSE.

## <a name="cmfcribbonstatusbarpaneondrawborder"></a><a name="ondrawborder"></a> CMFCRibbonStatusBarPane::OnDrawBorder

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>Parametry

podczas *&#42;przechwytywania* zmian<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonstatusbarpaneonfillbackground"></a><a name="onfillbackground"></a> CMFCRibbonStatusBarPane::OnFillBackground

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Parametry

podczas *kontroler PDC*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonstatusbarpaneonfinishanimation"></a><a name="onfinishanimation"></a> CMFCRibbonStatusBarPane::OnFinishAnimation

Platforma wywołuje tę metodę, gdy animacja przypisana do okienka zostanie zakończona.

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>Uwagi

`StopAnimation` Metoda wywołuje `OnFinishAnimation` metodę, której można użyć do oczyszczenia danych po zakończeniu animacji.

## <a name="cmfcribbonstatusbarpanesetalmostlargetext"></a><a name="setalmostlargetext"></a> CMFCRibbonStatusBarPane::SetAlmostLargeText

Zdefiniuj najdłuższy tekst, który będzie wyświetlany w okienku paska stanu bez obcinania.

```cpp
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>Parametry

*lpszAlmostLargeText*<br/>
podczas Określa najdłuższy ciąg, który może być wyświetlany w okienku paska stanu bez obcinania.

### <a name="remarks"></a>Uwagi

Biblioteka oblicza rozmiar tekstu, który *lpszAlmostLargeText* określa i zmienia rozmiar okienka odpowiednio. Tekst zostanie obcięty, jeśli nadal nie mieści się w okienku.

## <a name="cmfcribbonstatusbarpanesetanimationlist"></a><a name="setanimationlist"></a> CMFCRibbonStatusBarPane::SetAnimationList

Dołącza do okienka pasek stanu listę obrazów, która może być używana do animacji.

```cpp
void SetAnimationList(
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```

### <a name="parameters"></a>Parametry

*hBmpAnimationList*<br/>
podczas Określa uchwyt do listy obrazów.

*cxAnimation*<br/>
podczas Określa szerokość ramki na liście obrazów (w pikselach).

*clrTransp*<br/>
podczas Określa przezroczysty kolor listy obrazów.

*uiAnimationListResID*<br/>
podczas Określa identyfikator zasobu listy obrazów.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli lista obrazów została pomyślnie dołączona do okienka paska stanu. W przeciwnym razie zwraca wartość FALSE.

## <a name="cmfcribbonstatusbarpanesettextalign"></a><a name="settextalign"></a> CMFCRibbonStatusBarPane:: TextAlign

Ustawia wyrównanie tekstu etykiety w okienku paska stanu.

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Parametry

*nAlign*<br/>
podczas Określa wyrównanie tekstu.

### <a name="remarks"></a>Uwagi

*nAlign* może mieć jedną z następujących wartości:

- TA_LEFT: wyrównanie do lewej

- TA_CENTER: wyrównanie do środka

- TA_RIGHT: wyrównanie do prawej

## <a name="cmfcribbonstatusbarpanestartanimation"></a><a name="startanimation"></a> CMFCRibbonStatusBarPane::StartAnimation

Uruchamia animację przypisaną do okienka.

```cpp
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>Parametry

*nFrameDelay*<br/>
podczas Określa częstotliwość klatek animacji (w milisekundach).

*nDuration*<br/>
podczas Określa, jak długo ma być odtwarzana animacja (w milisekundach). Użyj-1 dla pętli nieskończonej.

### <a name="remarks"></a>Uwagi

Musisz określić uchwyt do listy obrazów przed wywołaniem przy `StartAnimation` użyciu polecenia `SetAnimationList` .

## <a name="cmfcribbonstatusbarpanestopanimation"></a><a name="stopanimation"></a> CMFCRibbonStatusBarPane::StopAnimation

Powoduje zatrzymanie animacji przypisanej do okienka paska stanu.

```cpp
void StopAnimation();
```

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[Klasa CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)

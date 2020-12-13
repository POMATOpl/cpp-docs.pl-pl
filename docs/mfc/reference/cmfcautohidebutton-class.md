---
description: 'Dowiedz się więcej na temat: Klasa CMFCAutoHideButton'
title: Klasa CMFCAutoHideButton
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::BringToTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Create
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAlignment
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAutoHideWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetParentToolBar
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetRect
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetTextSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::HighlightButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsActive
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHighlighted
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHorizontal
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsVisible
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Move
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDraw
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDrawBorder
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnFillBackground
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ReplacePane
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowAttachedWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::UnSetAutoHideMode
helpviewer_keywords:
- CMFCAutoHideButton [MFC], BringToTop
- CMFCAutoHideButton [MFC], Create
- CMFCAutoHideButton [MFC], GetAlignment
- CMFCAutoHideButton [MFC], GetAutoHideWindow
- CMFCAutoHideButton [MFC], GetParentToolBar
- CMFCAutoHideButton [MFC], GetRect
- CMFCAutoHideButton [MFC], GetSize
- CMFCAutoHideButton [MFC], GetTextSize
- CMFCAutoHideButton [MFC], HighlightButton
- CMFCAutoHideButton [MFC], IsActive
- CMFCAutoHideButton [MFC], IsHighlighted
- CMFCAutoHideButton [MFC], IsHorizontal
- CMFCAutoHideButton [MFC], IsTop
- CMFCAutoHideButton [MFC], IsVisible
- CMFCAutoHideButton [MFC], Move
- CMFCAutoHideButton [MFC], OnDraw
- CMFCAutoHideButton [MFC], OnDrawBorder
- CMFCAutoHideButton [MFC], OnFillBackground
- CMFCAutoHideButton [MFC], ReplacePane
- CMFCAutoHideButton [MFC], ShowAttachedWindow
- CMFCAutoHideButton [MFC], ShowButton
- CMFCAutoHideButton [MFC], UnSetAutoHideMode
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
ms.openlocfilehash: 9d100417193ea8a757b02b9cc8fad0cdedf668f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336580"
---
# <a name="cmfcautohidebutton-class"></a>Klasa CMFCAutoHideButton

Przycisk, który wyświetla lub ukrywa [klasę CDockablePane](../../mfc/reference/cdockablepane-class.md) , która jest skonfigurowana do ukrycia.

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

## <a name="syntax"></a>Składnia

```
class CMFCAutoHideButton : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCAutoHideButton::BringToTop](#bringtotop)||
|[CMFCAutoHideButton:: Create](#create)|Tworzy i inicjuje przycisk Autoukrywanie.|
|[CMFCAutoHideButton:: getalignment](#getalignment)|Pobiera wyrównanie przycisku Autoukrywanie.|
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|Zwraca obiekt [CDockablePane](../../mfc/reference/cdockablepane-class.md) skojarzony z przyciskiem Autoukrywanie.|
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||
|[CMFCAutoHideButton:: getRect](#getrect)||
|[CMFCAutoHideButton:: GetSize](#getsize)|Określa rozmiar przycisku autoukrywania.|
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|Zwraca rozmiar etykiety tekstowej przycisku autoukrywania.|
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|Podświetl przycisk Autoukrywanie.|
|[CMFCAutoHideButton:: IsActive](#isactive)|Wskazuje, czy przycisk Autoukrywanie jest aktywny.|
|[CMFCAutoHideButton:: ispodświetlacz](#ishighlighted)|Zwraca wyróżnienie stanu przycisku autoukrywania.|
|[CMFCAutoHideButton:: ispoziome](#ishorizontal)|Określa, czy przycisk Autoukrywanie jest poziomy, czy pionowy.|
|[CMFCAutoHideButton::IsTop](#istop)||
|[CMFCAutoHideButton:: IsVisible](#isvisible)|Wskazuje, czy przycisk jest widoczny.|
|[CMFCAutoHideButton:: Move](#move)||
|[CMFCAutoHideButton:: OnDraw](#ondraw)|Struktura wywołuje tę metodę, gdy rysuje przycisk Autoukrywanie.|
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|Struktura wywołuje tę metodę, gdy rysuje obramowanie przycisku Autoukrywanie.|
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|Struktura wywołuje tę metodę, gdy wypełnia tło przycisku autoukrywania.|
|[CMFCAutoHideButton::ReplacePane](#replacepane)||
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|Pokazuje lub ukrywa skojarzoną [klasę CDockablePane](../../mfc/reference/cdockablepane-class.md).|
|[CMFCAutoHideButton:: ShowButton](#showbutton)|Pokazuje lub ukrywa przycisk Autoukrywanie.|
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>Uwagi

Przy tworzeniu `CMFCAutoHideButton` obiekt jest dołączany do [klasy CDockablePane](../../mfc/reference/cdockablepane-class.md). `CDockablePane`Obiekt jest ukryty lub wyświetlany, gdy użytkownik współdziała z `CMFCAutoHideButton` obiektem.

Domyślnie struktura automatycznie tworzy, `CMFCAutoHideButton` gdy użytkownik włącza automatyczne ukrywanie. Struktura może utworzyć element niestandardowej klasy interfejsu użytkownika zamiast `CMFCAutoHideButton` klasy. Aby określić, która Klasa niestandardowego interfejsu użytkownika ma być używana przez platformę, ustaw statyczną zmienną elementu członkowskiego `CMFCAutoHideBar::m_pAutoHideButtonRTS` równą niestandardowej klasie interfejsu użytkownika. Domyślnie ta zmienna jest ustawiona na `CMFCAutoHideButton` .

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania `CMFCAutoHideButton` obiektu i używania różnych metod w `CMFCAutoHideButton` klasie. W przykładzie pokazano, jak zainicjować `CMFCAutoHideButton` obiekt za pomocą jego `Create` metody, pokazać skojarzoną `CDockablePane` klasę i wyświetlić przycisk Autoukrywanie.

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxautohidebutton. h

## <a name="cmfcautohidebuttonbringtotop"></a><a name="bringtotop"></a> CMFCAutoHideButton::BringToTop

```cpp
void BringToTop();
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebuttoncreate"></a><a name="create"></a> CMFCAutoHideButton:: Create

Tworzy i inicjuje przycisk Autoukrywanie.

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parametry

*pParentBar*<br/>
podczas Wskaźnik do nadrzędnego paska narzędzi.

*pAutoHideWnd*<br/>
podczas Wskaźnik do obiektu [CDockablePane](../../mfc/reference/cdockablepane-class.md) . Ten przycisk Autoukrywanie ukrywa i pokazuje, że `CDockablePane` .

*dwAlignment*<br/>
podczas Wartość określająca wyrównanie przycisku przy użyciu okna głównego ramki.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Podczas tworzenia `CMFCAutoHideButton` obiektu należy skojarzyć przycisk Autoukrywanie z określonym `CDockablePane` . Użytkownik może użyć przycisku Autoukrywanie, aby ukryć i pokazać skojarzone `CDockablePane` .

Parametr *dwAlignment* wskazuje, gdzie znajduje się przycisk Autoukrywanie w aplikacji. Parametr może mieć jedną z następujących wartości:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetalignment"></a><a name="getalignment"></a> CMFCAutoHideButton:: getalignment

Pobiera wyrównanie przycisku Autoukrywanie.

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość DWORD, która zawiera bieżące wyrównanie przycisku Autoukrywanie.

### <a name="remarks"></a>Uwagi

Wyrównanie przycisku Autoukrywanie wskazuje, gdzie znajduje się przycisk w aplikacji. Może to być jedna z następujących wartości:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebuttongetautohidewindow"></a><a name="getautohidewindow"></a> CMFCAutoHideButton::GetAutoHideWindow

Zwraca obiekt [CDockablePane](../../mfc/reference/cdockablepane-class.md) skojarzony z przyciskiem Autoukrywanie.

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do skojarzonego `CDockablePane` obiektu.

### <a name="remarks"></a>Uwagi

Aby skojarzyć przycisk Autoukrywanie z obiektem `CDockablePane` , Przekaż `CDockablePane` parametr AS do metody [CMFCAutoHideButton:: Create](#create) .

## <a name="cmfcautohidebuttongetparenttoolbar"></a><a name="getparenttoolbar"></a> CMFCAutoHideButton::GetParentToolBar

```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebuttongetrect"></a><a name="getrect"></a> CMFCAutoHideButton:: getRect

```
CRect GetRect() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebuttongetsize"></a><a name="getsize"></a> CMFCAutoHideButton:: GetSize

Określa rozmiar przycisku autoukrywania.

```
CSize GetSize() const;
```

### <a name="return-value"></a>Wartość zwracana

`CSize`Obiekt, który zawiera rozmiar przycisku.

### <a name="remarks"></a>Uwagi

Obliczony rozmiar obejmuje rozmiar obramowania przycisku Autoukrywanie.

## <a name="cmfcautohidebuttongettextsize"></a><a name="gettextsize"></a> CMFCAutoHideButton::GetTextSize

Zwraca rozmiar etykiety tekstowej przycisku autoukrywania.

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Obiekt [CSize](../../atl-mfc-shared/reference/csize-class.md) , który zawiera rozmiar tekstu przycisku autoukrywania.

## <a name="cmfcautohidebuttonisactive"></a><a name="isactive"></a> CMFCAutoHideButton:: IsActive

Wskazuje, czy przycisk Autoukrywanie jest aktywny.

```
BOOL IsActive() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli przycisk Autoukrywanie jest aktywny. W przeciwnym razie zwraca wartość FALSE.

### <a name="remarks"></a>Uwagi

Przycisk Autoukrywanie jest aktywny, gdy zostanie wyświetlone skojarzone okno [klasy CDockablePane](../../mfc/reference/cdockablepane-class.md) .

## <a name="cmfcautohidebuttonishorizontal"></a><a name="ishorizontal"></a> CMFCAutoHideButton:: ispoziome

Określa, czy przycisk Autoukrywanie jest poziomy, czy pionowy.

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli przycisk jest poziomy. 0 w przeciwnym razie.

### <a name="remarks"></a>Uwagi

Struktura Ustawia orientację obiektu [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) podczas jego tworzenia.  Orientację można kontrolować przy użyciu parametru *dwAlignment* w metodzie [CMFCAutoHideButton:: Create](#create) .

## <a name="cmfcautohidebuttonistop"></a><a name="istop"></a> CMFCAutoHideButton::IsTop

```
BOOL IsTop() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebuttonisvisible"></a><a name="isvisible"></a> CMFCAutoHideButton:: IsVisible

Wskazuje, czy przycisk Autoukrywanie jest widoczny.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli przycisk jest widoczny; W przeciwnym razie zwraca wartość FALSE.

## <a name="cmfcautohidebuttonondraw"></a><a name="ondraw"></a> CMFCAutoHideButton:: OnDraw

Struktura wywołuje tę metodę, gdy rysuje przycisk Autoukrywanie.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

### <a name="remarks"></a>Uwagi

Jeśli chcesz dostosować wygląd przycisków Autoukrywanie w aplikacji, Utwórz nową klasę pochodną od `CMFCAutoHideButton` . W klasie pochodnej Przesłoń tę metodę.

## <a name="cmfcautohidebuttonondrawborder"></a><a name="ondrawborder"></a> CMFCAutoHideButton::OnDrawBorder

Struktura wywołuje tę metodę, gdy rysuje obramowanie przycisku Autoukrywanie.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

*rectBounds*<br/>
podczas Prostokąt ograniczający przycisk Autoukrywanie.

*rectBorderSize*<br/>
podczas Grubość obramowania dla każdej strony przycisku Autoukrywanie.

### <a name="remarks"></a>Uwagi

Jeśli chcesz dostosować obramowanie każdego przycisku Autoukrywanie w aplikacji, Utwórz nową klasę pochodną od `CMFCAutoHideButton` . W klasie pochodnej Przesłoń tę metodę.

## <a name="cmfcautohidebuttononfillbackground"></a><a name="onfillbackground"></a> CMFCAutoHideButton::OnFillBackground

Struktura wywołuje tę metodę, gdy wypełnia tło przycisku autoukrywania.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

*cinania*<br/>
podczas Prostokąt ograniczający przycisk Autoukrywanie.

### <a name="remarks"></a>Uwagi

Jeśli chcesz dostosować tło dla przycisków Autoukrywanie w aplikacji, Utwórz nową klasę pochodną od `CMFCAutoHideButton` . W klasie pochodnej Przesłoń tę metodę.

## <a name="cmfcautohidebuttonshowattachedwindow"></a><a name="showattachedwindow"></a> CMFCAutoHideButton::ShowAttachedWindow

Pokazuje lub ukrywa skojarzoną [klasę CDockablePane](../../mfc/reference/cdockablepane-class.md).

```cpp
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>Parametry

*bShow*<br/>
podczas Wartość logiczna określająca, czy ta metoda pokazuje dołączony `CDockablePane` .

## <a name="cmfcautohidebuttonshowbutton"></a><a name="showbutton"></a> CMFCAutoHideButton:: ShowButton

Pokazuje lub ukrywa przycisk Autoukrywanie.

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>Parametry

*bShow*<br/>
podczas Wartość logiczna określająca, czy ma być wyświetlany przycisk Autoukrywanie.

## <a name="cmfcautohidebuttonmove"></a><a name="move"></a> CMFCAutoHideButton:: Move

```cpp
void Move(int nOffset);
```

### <a name="parameters"></a>Parametry

podczas *nOffset*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebuttonreplacepane"></a><a name="replacepane"></a> CMFCAutoHideButton::ReplacePane

```cpp
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>Parametry

podczas *pNewBar*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebuttonunsetautohidemode"></a><a name="unsetautohidemode"></a> CMFCAutoHideButton::UnSetAutoHideMode

Wyłącz tryb autoukrywania.

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>Parametry

*pFirstBarInGroup*<br/>
podczas Wskaźnik do pierwszego paska w grupie.

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebuttonhighlightbutton"></a><a name="highlightbutton"></a> CMFCAutoHideButton::HighlightButton

Podświetla przycisk Autoukrywanie.

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>Parametry

*bHighlight*<br/>
Określa nowy stan przycisku Autoukrywanie. Wartość TRUE oznacza, że przycisk jest wyróżniony, wartość FALSE wskazuje, że przycisk nie jest wyróżniony.

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebuttonishighlighted"></a><a name="ishighlighted"></a> CMFCAutoHideButton:: ispodświetlacz

Zwraca stan wyróżnienia przycisku Autoukrywanie.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli przycisk Autoukrywanie jest wyróżniony; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[Klasa CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)

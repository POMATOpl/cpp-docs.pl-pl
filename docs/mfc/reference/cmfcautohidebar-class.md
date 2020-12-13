---
description: 'Dowiedz się więcej na temat: Klasa CMFCAutoHideBar'
title: Klasa CMFCAutoHideBar
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
helpviewer_keywords:
- CMFCAutoHideBar [MFC], CMFCAutoHideBar
- CMFCAutoHideBar [MFC], AddAutoHideWindow
- CMFCAutoHideBar [MFC], AllowShowOnPaneMenu
- CMFCAutoHideBar [MFC], CalcFixedLayout
- CMFCAutoHideBar [MFC], Create
- CMFCAutoHideBar [MFC], GetFirstAHWindow
- CMFCAutoHideBar [MFC], GetVisibleCount
- CMFCAutoHideBar [MFC], OnShowControlBarMenu
- CMFCAutoHideBar [MFC], RemoveAutoHideWindow
- CMFCAutoHideBar [MFC], SetActiveInGroup
- CMFCAutoHideBar [MFC], SetRecentVisibleState
- CMFCAutoHideBar [MFC], ShowAutoHideWindow
- CMFCAutoHideBar [MFC], StretchPane
- CMFCAutoHideBar [MFC], UnSetAutoHideMode
- CMFCAutoHideBar [MFC], UpdateVisibleState
- CMFCAutoHideBar [MFC], m_nShowAHWndDelay
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
ms.openlocfilehash: d7cea85a71b8390520d1345e12000aa700026269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336607"
---
# <a name="cmfcautohidebar-class"></a>Klasa CMFCAutoHideBar

`CMFCAutoHideBar`Klasa jest specjalną klasą paska narzędzi, która implementuje funkcję autoukrywania.

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

## <a name="syntax"></a>Składnia

```
class CMFCAutoHideBar : public CPane
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Przesłania `CPane::AllowShowOnPaneMenu`).|
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(Przesłania [CBasePane:: CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCAutoHideBar:: Create](#create)|Tworzy pasek sterowania i dołącza go do obiektu [CPane](../../mfc/reference/cpane-class.md) . (Przesłania [CPane:: Create](../../mfc/reference/cpane-class.md#create).)|
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|Wywoływane przez platformę, gdy zostanie wyświetlone specjalne menu okienka. (Przesłania [CPane:: OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(Przesłania [CPane:: SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).)|
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||
|[CMFCAutoHideBar::StretchPane](#stretchpane)|Rozciąga okienko w pionie lub w poziomie. (Przesłania [CBasePane:: StretchPane](../../mfc/reference/cbasepane-class.md#stretchpane).)|
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMFCAutoHideBar:: m_nShowAHWndDelay](#m_nshowahwnddelay)|Opóźnienie czasu między chwilą, gdy użytkownik umieści wskaźnik myszy nad [klasą CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) i chwilę, gdy struktura pokazuje skojarzone okno.|

## <a name="remarks"></a>Uwagi

Gdy użytkownik przełącza okienko dokowania do trybu Autoukrywanie, struktura automatycznie tworzy `CMFCAutoHideBar` obiekt. Tworzy również niezbędne obiekty [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) i [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) . Każdy `CAutoHideDockSite` obiekt jest skojarzony z osobą `CMFCAutoHideButton` .

`CMFCAutoHideBar`Klasa implementuje wyświetlanie, `CAutoHideDockSite` gdy wskaźnik myszy jest przesuwany nad `CMFCAutoHideButton` . Gdy pasek narzędzi odbiera komunikat WM_MOUSEMOVE, `CMFCAutoHideBar` uruchamia czasomierz. Po zakończeniu czasomierza wysyła pasek narzędzi WM_TIMER powiadomienia o zdarzeniu. Pasek narzędzi obsługuje to zdarzenie, sprawdzając, czy wskaźnik myszy znajduje się nad tym samym przyciskiem Autoukrywanie, który został umieszczony w momencie uruchomienia czasomierza. Jeśli jest, zostanie `CAutoHideDockSite` wyświetlona wartość dołączone.

Można kontrolować długość opóźnienia czasomierza według ustawienia `m_nShowAHWndDelay` . Wartość domyślna to 400 MS.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania `CMFCAutoHideBar` obiektu i używania jego `GetDockSiteRow` metody.

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxautohidebar. h

## <a name="cmfcautohidebaraddautohidewindow"></a><a name="addautohidewindow"></a> CMFCAutoHideBar::AddAutoHideWindow

Dodaje funkcję do `CDockablePane` okna, które umożliwia jego Autoukrywanie.

```
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parametry

*pAutoHideWnd*<br/>
podczas Okno, które ma być ukryte.

*dwAlignment*<br/>
podczas Wartość określająca wyrównanie przycisku Autoukrywanie w oknie aplikacji.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Parametr *dwAlignment* wskazuje, gdzie znajduje się przycisk Autoukrywanie w aplikacji. Parametr może mieć jedną z następujących wartości:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a> CMFCAutoHideBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebarcalcfixedlayout"></a><a name="calcfixedlayout"></a> CMFCAutoHideBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametry

podczas *bStretch*<br/>

podczas *bHorz*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebarcmfcautohidebar"></a><a name="cmfcautohidebar"></a> CMFCAutoHideBar::CMFCAutoHideBar

Konstruuje obiekt CMFCAutoHideBar.

```
CMFCAutoHideBar();
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebarcreate"></a><a name="create"></a> CMFCAutoHideBar:: Create

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametry

*lpszClassName*<br/>

*dwStyle*<br/>

*cinania*<br/>

*pParentWnd*<br/>

*nID*<br/>

*dwControlBarStyle*<br/>

*pContext*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebargetfirstahwindow"></a><a name="getfirstahwindow"></a> CMFCAutoHideBar::GetFirstAHWindow

Zwraca wskaźnik do pierwszego okna autoukrywania w aplikacji.

```
CDockablePane* GetFirstAHWindow();
```

### <a name="return-value"></a>Wartość zwracana

Pierwsze Autoukrywanie okna w aplikacji lub wartość NULL, jeśli nie istnieje.

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebargetvisiblecount"></a><a name="getvisiblecount"></a> CMFCAutoHideBar::GetVisibleCount

Pobiera liczbę widocznych przycisków autoukrywania.

```
int GetVisibleCount();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę widocznych przycisków autoukrywania.

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebarm_nshowahwnddelay"></a><a name="m_nshowahwnddelay"></a> CMFCAutoHideBar:: m_nShowAHWndDelay

Opóźnienie czasu między chwilą, gdy użytkownik umieści wskaźnik myszy nad [klasą CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) i chwilę, gdy struktura pokazuje skojarzone okno.

```
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;
```

### <a name="remarks"></a>Uwagi

Gdy użytkownik umieści wskaźnik myszy nad obiektem `CMFCAutoHideButton` , istnieje niewielkie opóźnienie, zanim środowisko wyświetli skojarzone okno. Ten parametr określa długość opóźnienia (w milisekundach).

## <a name="cmfcautohidebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a> CMFCAutoHideBar::OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Parametry

podczas *CPoint*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebarremoveautohidewindow"></a><a name="removeautohidewindow"></a> CMFCAutoHideBar::RemoveAutoHideWindow

Usuwa i niszczy okno Autoukrywanie.

```
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```

### <a name="parameters"></a>Parametry

CDockablePane * *pAutoHideWnd* okno Autoukrywanie do usunięcia.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli powodzenie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebarsetactiveingroup"></a><a name="setactiveingroup"></a> CMFCAutoHideBar::SetActiveInGroup

Flaguje autoukrywanie paska jako aktywnego.

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>Parametry

podczas BOOL *bActive* wartość true, aby ustawić jako aktywną; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Zobacz [CPane:: SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).

## <a name="cmfcautohidebarsetrecentvisiblestate"></a><a name="setrecentvisiblestate"></a> CMFCAutoHideBar::SetRecentVisibleState

```cpp
void SetRecentVisibleState(BOOL bState);
```

### <a name="parameters"></a>Parametry

*bState*<br/>
podczas Stan do ustawienia.

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebarshowautohidewindow"></a><a name="showautohidewindow"></a> CMFCAutoHideBar::ShowAutoHideWindow

Wyświetla okno Autoukrywanie.

```
BOOL ShowAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Parametry

*pAutoHideWnd*<br/>
podczas Okno do wyświetlenia.

*bShow*<br/>
podczas Wartość TRUE, aby wyświetlić okno.

*bDelay*<br/>
podczas Ten parametr jest ignorowany.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli powodzenie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebarstretchpane"></a><a name="stretchpane"></a> CMFCAutoHideBar::StretchPane

Zmienia rozmiar paska Autoukrywanie w stanie zwiniętym, aby dopasować go do `CMFCAutoHideButton` obiektu.

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>Parametry

*nLength*<br/>
podczas Wartość nie jest używana w implementacji podstawowej. W przypadku implementacji pochodnych Użyj tej wartości, aby wskazać długość okienka o zmienionym rozmiarze.

*bVert*<br/>
podczas Wartość nie jest używana w implementacji podstawowej. W implementacjach pochodnych Użyj wartości TRUE, aby obsłużyć przypadek, w którym pasek Autoukrywanie jest zwinięty pionowo, i wartość FALSE dla przypadku, gdy pasek Autoukrywanie jest zwinięty w poziomie.

### <a name="return-value"></a>Wartość zwracana

Rozmiar powstającego okienka o zmienionym rozmiarze.

### <a name="remarks"></a>Uwagi

Klasy pochodne mogą przesłonić tę metodę, aby dostosować zachowanie.

## <a name="cmfcautohidebarunsetautohidemode"></a><a name="unsetautohidemode"></a> CMFCAutoHideBar::UnSetAutoHideMode

Wyłącza tryb autoukrywania dla grupy Autoukrywanie słupków.

```cpp
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)
```

### <a name="parameters"></a>Parametry

[in] pFirstBarInGroup wskaźnik do pierwszego paska Autoukrywanie w grupie.

### <a name="remarks"></a>Uwagi

## <a name="cmfcautohidebarupdatevisiblestate"></a><a name="updatevisiblestate"></a> CMFCAutoHideBar::UpdateVisibleState

Wywoływane przez platformę, gdy należy ponownie narysować pasek autoukrywania.

```cpp
void UpdateVisibleState();
```

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CPane](../../mfc/reference/cpane-class.md)<br/>
[Klasa CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)<br/>
[Klasa CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)

---
description: 'Dowiedz się więcej na temat: Klasa CDockingPanesRow'
title: Klasa CDockingPanesRow
ms.date: 10/18/2018
f1_keywords:
- CDockingPanesRow
- AFXDOCKINGPANESROW/CDockingPanesRow
- AFXDOCKINGPANESROW/CDockingPanesRow::AddPane
- AFXDOCKINGPANESROW/CDockingPanesRow::AddPaneFromRow
- AFXDOCKINGPANESROW/CDockingPanesRow::ArrangePanes
- AFXDOCKINGPANESROW/CDockingPanesRow::CalcFixedLayout
- AFXDOCKINGPANESROW/CDockingPanesRow::Create
- AFXDOCKINGPANESROW/CDockingPanesRow::ExpandStretchedPanes
- AFXDOCKINGPANESROW/CDockingPanesRow::ExpandStretchedPanesRect
- AFXDOCKINGPANESROW/CDockingPanesRow::FixupVirtualRects
- AFXDOCKINGPANESROW/CDockingPanesRow::GetAvailableLength
- AFXDOCKINGPANESROW/CDockingPanesRow::GetAvailableSpace
- AFXDOCKINGPANESROW/CDockingPanesRow::GetClientRect
- AFXDOCKINGPANESROW/CDockingPanesRow::GetDockSite
- AFXDOCKINGPANESROW/CDockingPanesRow::GetExtraSpace
- AFXDOCKINGPANESROW/CDockingPanesRow::GetGroupFromPane
- AFXDOCKINGPANESROW/CDockingPanesRow::GetID
- AFXDOCKINGPANESROW/CDockingPanesRow::GetMaxPaneSize
- AFXDOCKINGPANESROW/CDockingPanesRow::GetPaneCount
- AFXDOCKINGPANESROW/CDockingPanesRow::GetPaneList
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowAlignment
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowHeight
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowOffset
- AFXDOCKINGPANESROW/CDockingPanesRow::GetVisibleCount
- AFXDOCKINGPANESROW/CDockingPanesRow::GetWindowRect
- AFXDOCKINGPANESROW/CDockingPanesRow::HasPane
- AFXDOCKINGPANESROW/CDockingPanesRow::IsEmpty
- AFXDOCKINGPANESROW/CDockingPanesRow::IsExclusiveRow
- AFXDOCKINGPANESROW/CDockingPanesRow::IsHorizontal
- AFXDOCKINGPANESROW/CDockingPanesRow::IsVisible
- AFXDOCKINGPANESROW/CDockingPanesRow::Move
- AFXDOCKINGPANESROW/CDockingPanesRow::MovePane
- AFXDOCKINGPANESROW/CDockingPanesRow::OnResizePane
- AFXDOCKINGPANESROW/CDockingPanesRow::RedrawAll
- AFXDOCKINGPANESROW/CDockingPanesRow::RemovePane
- AFXDOCKINGPANESROW/CDockingPanesRow::ReplacePane
- AFXDOCKINGPANESROW/CDockingPanesRow::RepositionPanes
- AFXDOCKINGPANESROW/CDockingPanesRow::Resize
- AFXDOCKINGPANESROW/CDockingPanesRow::ResizeByPaneDivider
- AFXDOCKINGPANESROW/CDockingPanesRow::ScreenToClient
- AFXDOCKINGPANESROW/CDockingPanesRow::SetExtra
- AFXDOCKINGPANESROW/CDockingPanesRow::ShowDockSiteRow
- AFXDOCKINGPANESROW/CDockingPanesRow::ShowPane
- AFXDOCKINGPANESROW/CDockingPanesRow::UpdateVisibleState
helpviewer_keywords:
- CDockingPanesRow [MFC], AddPane
- CDockingPanesRow [MFC], AddPaneFromRow
- CDockingPanesRow [MFC], ArrangePanes
- CDockingPanesRow [MFC], CalcFixedLayout
- CDockingPanesRow [MFC], Create
- CDockingPanesRow [MFC], ExpandStretchedPanes
- CDockingPanesRow [MFC], ExpandStretchedPanesRect
- CDockingPanesRow [MFC], FixupVirtualRects
- CDockingPanesRow [MFC], GetAvailableLength
- CDockingPanesRow [MFC], GetAvailableSpace
- CDockingPanesRow [MFC], GetClientRect
- CDockingPanesRow [MFC], GetDockSite
- CDockingPanesRow [MFC], GetExtraSpace
- CDockingPanesRow [MFC], GetGroupFromPane
- CDockingPanesRow [MFC], GetID
- CDockingPanesRow [MFC], GetMaxPaneSize
- CDockingPanesRow [MFC], GetPaneCount
- CDockingPanesRow [MFC], GetPaneList
- CDockingPanesRow [MFC], GetRowAlignment
- CDockingPanesRow [MFC], GetRowHeight
- CDockingPanesRow [MFC], GetRowOffset
- CDockingPanesRow [MFC], GetVisibleCount
- CDockingPanesRow [MFC], GetWindowRect
- CDockingPanesRow [MFC], HasPane
- CDockingPanesRow [MFC], IsEmpty
- CDockingPanesRow [MFC], IsExclusiveRow
- CDockingPanesRow [MFC], IsHorizontal
- CDockingPanesRow [MFC], IsVisible
- CDockingPanesRow [MFC], Move
- CDockingPanesRow [MFC], MovePane
- CDockingPanesRow [MFC], OnResizePane
- CDockingPanesRow [MFC], RedrawAll
- CDockingPanesRow [MFC], RemovePane
- CDockingPanesRow [MFC], ReplacePane
- CDockingPanesRow [MFC], RepositionPanes
- CDockingPanesRow [MFC], Resize
- CDockingPanesRow [MFC], ResizeByPaneDivider
- CDockingPanesRow [MFC], ScreenToClient
- CDockingPanesRow [MFC], SetExtra
- CDockingPanesRow [MFC], ShowDockSiteRow
- CDockingPanesRow [MFC], ShowPane
- CDockingPanesRow [MFC], UpdateVisibleState
ms.assetid: e7a17832-0ebb-4bce-b799-cec9b60f76fe
ms.openlocfilehash: bf031b19c25cde36705333feb3baa3af9e1932ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185014"
---
# <a name="cdockingpanesrow-class"></a>Klasa CDockingPanesRow

Zarządza listą okienek, które znajdują się w tym samym lub pionowym wierszu (kolumnie) witryny dokowania.

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

## <a name="syntax"></a>Składnia

```
class CDockingPanesRow : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CDockingPanesRow::CDockingPanesRow`|Konstruktor domyślny.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDockingPanesRow:: Add— okienko](#addpane)||
|[CDockingPanesRow::AddPaneFromRow](#addpanefromrow)||
|[CDockingPanesRow::ArrangePanes](#arrangepanes)|Rozmieszcza okienka w wierszu zgodnie z określonymi parametrami marginesu i odstępu.|
|[CDockingPanesRow::CalcFixedLayout](#calcfixedlayout)||
|[CDockingPanesRow:: Create](#create)||
|[CDockingPanesRow::ExpandStretchedPanes](#expandstretchedpanes)||
|[CDockingPanesRow::ExpandStretchedPanesRect](#expandstretchedpanesrect)||
|[CDockingPanesRow::FixupVirtualRects](#fixupvirtualrects)||
|[CDockingPanesRow::GetAvailableLength](#getavailablelength)||
|[CDockingPanesRow::GetAvailableSpace](#getavailablespace)||
|[CDockingPanesRow::GetClientRect](#getclientrect)||
|[CDockingPanesRow::GetDockSite](#getdocksite)||
|[CDockingPanesRow::GetExtraSpace](#getextraspace)||
|[CDockingPanesRow::GetGroupFromPane](#getgroupfrompane)||
|[CDockingPanesRow:: GetId —](#getid)||
|[CDockingPanesRow::GetMaxPaneSize](#getmaxpanesize)||
|[CDockingPanesRow::GetPaneCount](#getpanecount)||
|[CDockingPanesRow:: getpanelname](#getpanelist)||
|[CDockingPanesRow::GetRowAlignment](#getrowalignment)||
|[CDockingPanesRow::GetRowHeight](#getrowheight)||
|[CDockingPanesRow::GetRowOffset](#getrowoffset)||
|[CDockingPanesRow::GetVisibleCount](#getvisiblecount)||
|[CDockingPanesRow::GetWindowRect](#getwindowrect)||
|[CDockingPanesRow::HasPane](#haspane)||
|[CDockingPanesRow:: IsEmpty](#isempty)||
|[CDockingPanesRow::IsExclusiveRow](#isexclusiverow)||
|[CDockingPanesRow:: ispoziome](#ishorizontal)||
|[CDockingPanesRow:: IsVisible](#isvisible)||
|[CDockingPanesRow:: Move](#move)||
|[CDockingPanesRow::MovePane](#movepane)||
|[CDockingPanesRow::OnResizePane](#onresizepane)||
|[CDockingPanesRow::RedrawAll](#redrawall)||
|[CDockingPanesRow::RemovePane](#removepane)||
|[CDockingPanesRow::ReplacePane](#replacepane)||
|[CDockingPanesRow::RepositionPanes](#repositionpanes)||
|[CDockingPanesRow:: Resize](#resize)||
|[CDockingPanesRow::ResizeByPaneDivider](#resizebypanedivider)||
|[CDockingPanesRow::ScreenToClient](#screentoclient)||
|[CDockingPanesRow:: setextra](#setextra)||
|[CDockingPanesRow::ShowDockSiteRow](#showdocksiterow)||
|[CDockingPanesRow::ShowPane](#showpane)||
|[CDockingPanesRow::UpdateVisibleState](#updatevisiblestate)||

## <a name="remarks"></a>Uwagi

`CDockingPanesRow` obiekty są tworzone wewnętrznie przez obiekty lokacji dokowania.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak pobrać `CDockingPanesRow` obiekt z `CMFCAutoHideBar` obiektu.

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cdockingpanesrow-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxDockingPanesRow. h

## <a name="cdockingpanesrowaddpane"></a><a name="addpane"></a> CDockingPanesRow:: Add— okienko

```
virtual void AddPane(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL,
    BOOL bAddLast = FALSE);
```

### <a name="parameters"></a>Parametry

podczas *pControlBar*<br/>

podczas *dockMethod*<br/>

podczas *lpRect*<br/>

podczas *bAddLast*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowaddpanefromrow"></a><a name="addpanefromrow"></a> CDockingPanesRow::AddPaneFromRow

```
virtual void AddPaneFromRow(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parametry

podczas *pControlBar*<br/>

podczas *dockMethod*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowarrangepanes"></a><a name="arrangepanes"></a> CDockingPanesRow::ArrangePanes

Rozmieszcza okienka zadokowane w wierszu zgodnie z określonymi parametrami marginesu i odstępu.

```
virtual void ArrangePanes(
    int nMargin,
    int nSpacing);
```

### <a name="parameters"></a>Parametry

*nMargin*<br/>
podczas Określa przesunięcie (w pikselach) pierwszego okienka w lewym górnym rogu wiersza.

*nSpacing*<br/>
podczas Określa odstępy (w pikselach) między okienkami.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby rozmieścić okienka w wierszu, w którym będą zadokowane. Po wywołaniu tej metody należy wywołać metodę `CDockingPanesRow::FixupVirtualRects(FALSE, NULL)` .

## <a name="cdockingpanesrowcalcfixedlayout"></a><a name="calcfixedlayout"></a> CDockingPanesRow::CalcFixedLayout

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

## <a name="cdockingpanesrowcdockingpanesrow"></a><a name="cdockingpanesrow"></a> CDockingPanesRow::CDockingPanesRow

```
CDockingPanesRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nHeight);
```

### <a name="parameters"></a>Parametry

podczas *pParentDockBar*<br/>

podczas *nOffset*<br/>

podczas *nHeight*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowcreate"></a><a name="create"></a> CDockingPanesRow:: Create

```
virtual BOOL Create();
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowexpandstretchedpanes"></a><a name="expandstretchedpanes"></a> CDockingPanesRow::ExpandStretchedPanes

```cpp
void ExpandStretchedPanes();
```

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowexpandstretchedpanesrect"></a><a name="expandstretchedpanesrect"></a> CDockingPanesRow::ExpandStretchedPanesRect

```cpp
void ExpandStretchedPanesRect();
```

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowfixupvirtualrects"></a><a name="fixupvirtualrects"></a> CDockingPanesRow::FixupVirtualRects

```cpp
void FixupVirtualRects(
    bool bMoveBackToVirtualRect,
    CPane* pBarToExclude = NULL);
```

### <a name="parameters"></a>Parametry

podczas *bMoveBackToVirtualRect*<br/>

podczas *pBarToExclude*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetavailablelength"></a><a name="getavailablelength"></a> CDockingPanesRow::GetAvailableLength

```
virtual int GetAvailableLength(BOOL bUseVirtualRect = FALSE) const;
```

### <a name="parameters"></a>Parametry

podczas *bUseVirtualRect*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetavailablespace"></a><a name="getavailablespace"></a> CDockingPanesRow::GetAvailableSpace

```
virtual void GetAvailableSpace(CRect& rect);
```

### <a name="parameters"></a>Parametry

podczas *prostokąt*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetclientrect"></a><a name="getclientrect"></a> CDockingPanesRow::GetClientRect

```cpp
void GetClientRect(CRect& rect) const;
```

### <a name="parameters"></a>Parametry

podczas *prostokąt*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetdocksite"></a><a name="getdocksite"></a> CDockingPanesRow::GetDockSite

```
CDockSite* GetDockSite() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetextraspace"></a><a name="getextraspace"></a> CDockingPanesRow::GetExtraSpace

```
int GetExtraSpace() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetgroupfrompane"></a><a name="getgroupfrompane"></a> CDockingPanesRow::GetGroupFromPane

```cpp
void GetGroupFromPane(
    CPane* pBar,
    CObList& lst);
```

### <a name="parameters"></a>Parametry

podczas *pBar*<br/>

podczas *LST*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetid"></a><a name="getid"></a> CDockingPanesRow:: GetId —

```
int GetID() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetmaxpanesize"></a><a name="getmaxpanesize"></a> CDockingPanesRow::GetMaxPaneSize

```
int GetMaxPaneSize(BOOL bSkipHiddenBars = TRUE) const;
```

### <a name="parameters"></a>Parametry

podczas *bSkipHiddenBars*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetpanecount"></a><a name="getpanecount"></a> CDockingPanesRow::GetPaneCount

```
int GetPaneCount() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetpanelist"></a><a name="getpanelist"></a> CDockingPanesRow:: getpanelname

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetrowalignment"></a><a name="getrowalignment"></a> CDockingPanesRow::GetRowAlignment

```
DWORD GetRowAlignment() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetrowheight"></a><a name="getrowheight"></a> CDockingPanesRow::GetRowHeight

```
int GetRowHeight() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetrowoffset"></a><a name="getrowoffset"></a> CDockingPanesRow::GetRowOffset

```
int GetRowOffset() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetvisiblecount"></a><a name="getvisiblecount"></a> CDockingPanesRow::GetVisibleCount

```
virtual int GetVisibleCount();
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowgetwindowrect"></a><a name="getwindowrect"></a> CDockingPanesRow::GetWindowRect

```cpp
void GetWindowRect(CRect& rect) const;
```

### <a name="parameters"></a>Parametry

podczas *prostokąt*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowhaspane"></a><a name="haspane"></a> CDockingPanesRow::HasPane

```
BOOL HasPane(CBasePane* pControlBar);
```

### <a name="parameters"></a>Parametry

podczas *pControlBar*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowisempty"></a><a name="isempty"></a> CDockingPanesRow:: IsEmpty

```
virtual BOOL IsEmpty() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowisexclusiverow"></a><a name="isexclusiverow"></a> CDockingPanesRow::IsExclusiveRow

```
virtual BOOL IsExclusiveRow() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowishorizontal"></a><a name="ishorizontal"></a> CDockingPanesRow:: ispoziome

```
bool IsHorizontal() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowisvisible"></a><a name="isvisible"></a> CDockingPanesRow:: IsVisible

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowmove"></a><a name="move"></a> CDockingPanesRow:: Move

```
virtual void Move(int nOffset);
```

### <a name="parameters"></a>Parametry

podczas *nOffset*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowmovepane"></a><a name="movepane"></a> CDockingPanesRow::MovePane

```cpp
void MovePane(
    CPane* pControlBar,
    CPoint ptOffset,
    BOOL bSwapControlBars,
    HDWP& hdwp);

void MovePane(
    CPane* pControlBar,
    CRect rectTarget,
    HDWP& hdwp);

void MovePane(
    CPane* pControlBar,
    int nOffset,
    bool bForward,
    HDWP& hdwp);

void MovePane(
    CPane* pControlBar,
    int nAbsolutOffset,
    HDWP& hdwp);
```

### <a name="parameters"></a>Parametry

podczas *pControlBar*<br/>

podczas *ptOffset*<br/>

podczas *bSwapControlBars*<br/>

podczas *hdwp*<br/>

podczas *rectTarget*<br/>

podczas *nOffset*<br/>

podczas *bForward*<br/>

podczas *nAbsolutOffset*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowonresizepane"></a><a name="onresizepane"></a> CDockingPanesRow::OnResizePane

```
virtual void OnResizePane(CBasePane* pControlBar);
```

### <a name="parameters"></a>Parametry

podczas *pControlBar*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowredrawall"></a><a name="redrawall"></a> CDockingPanesRow::RedrawAll

```cpp
void RedrawAll();
```

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowremovepane"></a><a name="removepane"></a> CDockingPanesRow::RemovePane

```
virtual void RemovePane(CPane* pControlBar);
```

### <a name="parameters"></a>Parametry

podczas *pControlBar*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowreplacepane"></a><a name="replacepane"></a> CDockingPanesRow::ReplacePane

```
virtual BOOL ReplacePane(
    CPane* pBarOld,
    CPane* pBarNew);
```

### <a name="parameters"></a>Parametry

podczas *pBarOld*<br/>

podczas *pBarNew*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowrepositionpanes"></a><a name="repositionpanes"></a> CDockingPanesRow::RepositionPanes

```
virtual void RepositionPanes(
    CRect& rectNewParentBarArea,
    UINT nSide = (UINT)-1,
    BOOL bExpand = FALSE,
    int nOffset = 0);
```

### <a name="parameters"></a>Parametry

podczas *rectNewParentBarArea*<br/>

podczas *nSide*<br/>

podczas *bExpand*<br/>

podczas *nOffset*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowresize"></a><a name="resize"></a> CDockingPanesRow:: Resize

```
virtual int Resize(int nOffset);
```

### <a name="parameters"></a>Parametry

podczas *nOffset*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowresizebypanedivider"></a><a name="resizebypanedivider"></a> CDockingPanesRow::ResizeByPaneDivider

```
virtual int ResizeByPaneDivider(int /*ignored*/);
```

### <a name="parameters"></a>Parametry

podczas *zignorowano*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowscreentoclient"></a><a name="screentoclient"></a> CDockingPanesRow::ScreenToClient

```cpp
void ScreenToClient(CRect& rect) const;
```

### <a name="parameters"></a>Parametry

podczas *prostokąt*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowsetextra"></a><a name="setextra"></a> CDockingPanesRow:: setextra

```cpp
void SetExtra(
    int nExtraSpace,
    AFX_ROW_ALIGNMENT rowExtraAlign);
```

### <a name="parameters"></a>Parametry

podczas *nExtraSpace*<br/>

podczas *rowExtraAlign*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowshowdocksiterow"></a><a name="showdocksiterow"></a> CDockingPanesRow::ShowDockSiteRow

```
virtual void ShowDockSiteRow(
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Parametry

podczas *bShow*<br/>

podczas *bDelay*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowshowpane"></a><a name="showpane"></a> CDockingPanesRow::ShowPane

```
virtual BOOL ShowPane(
    CPane* pControlBar,
    BOOL bShow,
    BOOL bDelay = FALSE);
```

### <a name="parameters"></a>Parametry

podczas *pControlBar*<br/>

podczas *bShow*<br/>

podczas *bDelay*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdockingpanesrowupdatevisiblestate"></a><a name="updatevisiblestate"></a> CDockingPanesRow::UpdateVisibleState

```
virtual void UpdateVisibleState(BOOL bDelay);
```

### <a name="parameters"></a>Parametry

podczas *bDelay*<br/>

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CObject](../../mfc/reference/cobject-class.md)<br/>
[Klasa CDockSite](../../mfc/reference/cdocksite-class.md)<br/>
[Klasa CPane](../../mfc/reference/cpane-class.md)

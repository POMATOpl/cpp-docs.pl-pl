---
title: Klasa CGlobalUtils | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils::AdjustRectToWorkArea
- AFXGLOBALUTILS/CGlobalUtils::CalcExpectedDockedRect
- AFXGLOBALUTILS/CGlobalUtils::CanBeAttached
- AFXGLOBALUTILS/CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd
- AFXGLOBALUTILS/CGlobalUtils::CheckAlignment
- AFXGLOBALUTILS/CGlobalUtils::CyFromString
- AFXGLOBALUTILS/CGlobalUtils::DecimalFromString
- AFXGLOBALUTILS/CGlobalUtils::FlipRect
- AFXGLOBALUTILS/CGlobalUtils::ForceAdjustLayout
- AFXGLOBALUTILS/CGlobalUtils::GetDockingManager
- AFXGLOBALUTILS/CGlobalUtils::GetOppositeAlignment
- AFXGLOBALUTILS/CGlobalUtils::GetPaneAndAlignFromPoint
- AFXGLOBALUTILS/CGlobalUtils::GetWndIcon
- AFXGLOBALUTILS/CGlobalUtils::SetNewParent
- AFXGLOBALUTILS/CGlobalUtils::StringFromCy
- AFXGLOBALUTILS/CGlobalUtils::StringFromDecimal
dev_langs:
- C++
helpviewer_keywords:
- CGlobalUtils [MFC], AdjustRectToWorkArea
- CGlobalUtils [MFC], CalcExpectedDockedRect
- CGlobalUtils [MFC], CanBeAttached
- CGlobalUtils [MFC], CanPaneBeInFloatingMultiPaneFrameWnd
- CGlobalUtils [MFC], CheckAlignment
- CGlobalUtils [MFC], CyFromString
- CGlobalUtils [MFC], DecimalFromString
- CGlobalUtils [MFC], FlipRect
- CGlobalUtils [MFC], ForceAdjustLayout
- CGlobalUtils [MFC], GetDockingManager
- CGlobalUtils [MFC], GetOppositeAlignment
- CGlobalUtils [MFC], GetPaneAndAlignFromPoint
- CGlobalUtils [MFC], GetWndIcon
- CGlobalUtils [MFC], SetNewParent
- CGlobalUtils [MFC], StringFromCy
- CGlobalUtils [MFC], StringFromDecimal
ms.assetid: 2c5bd1a6-f80c-4e79-a476-b4ceebabfb2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42436a885b194e0270bc9956514f4ff0de9c7461
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445896"
---
# <a name="cglobalutils-class"></a>Klasa CGlobalUtils

Aby uzyskać więcej informacji, zobacz kod źródłowy znajdujący się w **VC\\atlmfc\\src\\mfc** folder instalacji programu Visual Studio.

## <a name="syntax"></a>Składnia

```
class CGlobalUtils
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CGlobalUtils::AdjustRectToWorkArea](#adjustrecttoworkarea)||
|[CGlobalUtils::CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CGlobalUtils::CanBeAttached](#canbeattached)||
|[CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd](#canpanebeinfloatingmultipaneframewnd)||
|[CGlobalUtils::CheckAlignment](#checkalignment)||
|[CGlobalUtils::CyFromString](#cyfromstring)||
|[CGlobalUtils::DecimalFromString](#decimalfromstring)||
|[CGlobalUtils::FlipRect](#fliprect)||
|[CGlobalUtils::ForceAdjustLayout](#forceadjustlayout)||
|[CGlobalUtils::GetDockingManager](#getdockingmanager)||
|[CGlobalUtils::GetOppositeAlignment](#getoppositealignment)||
|[CGlobalUtils::GetPaneAndAlignFromPoint](#getpaneandalignfrompoint)||
|[CGlobalUtils::GetWndIcon](#getwndicon)||
|[CGlobalUtils::SetNewParent](#setnewparent)||
|[CGlobalUtils::StringFromCy](#stringfromcy)||
|[CGlobalUtils::StringFromDecimal](#stringfromdecimal)||

## <a name="remarks"></a>Uwagi

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CGlobalUtils](../../mfc/reference/cglobalutils-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxglobalutils.h

##  <a name="adjustrecttoworkarea"></a>  CGlobalUtils::AdjustRectToWorkArea

```
void AdjustRectToworkArea(
    CRect& rect,
    CRect* pRectDelta = NULL);
```

### <a name="parameters"></a>Parametry

*Rect*<br/>
[out w] [in] *pRectDelta*

### <a name="remarks"></a>Uwagi

##  <a name="calcexpecteddockedrect"></a>  CGlobalUtils::CalcExpectedDockedRect


```
void CalcExpectedDockedRect(
    CPaneContainerManager& barContainerManager,
    CWnd* pWndTodock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Parametry

*barContainerManager*<br/>
[in] [in] *pWndTodock*
*ptMouse*<br/>
[in] [out] *rectResult*
*bDrawTab*<br/>
[out] [out] *ppTargetBar*

### <a name="remarks"></a>Uwagi

##  <a name="canbeattached"></a>  CGlobalUtils::CanBeAttached


```
BOOL CanBeAttached(CWnd* pWnd) const;
```

### <a name="parameters"></a>Parametry

[in] *pWnd*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

##  <a name="canpanebeinfloatingmultipaneframewnd"></a>  CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd


```
BOOL CanPaneBeInFloatingMultiPaneFrameWnd(CWnd* pWnd) const;
```

### <a name="parameters"></a>Parametry

[in] *pWnd*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

##  <a name="checkalignment"></a>  CGlobalUtils::CheckAlignment


```
BOOL CheckAlignment(
    CPoint point,
    CBasePane* pBar,
    int nSensitivity,
    const CDockingManager* pDockManager,
    BOOL bOuterEdge,
    DWORD& dwAlignment,
    DWORD dwEnabledDockBars = CBRS_ALIGN_ANY,
    LPCRECT lpRectBounds = NULL) const;
```

### <a name="parameters"></a>Parametry

*Punkt*<br/>
[in] [in] *pBar*
*nSensitivity*<br/>
[in] [in] *pDockManager*
*bOuterEdge*<br/>
[in] [out] *dwAlignment*
*dwEnabledDockBars*<br/>
[in] [in] *lpRectBounds*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

##  <a name="cyfromstring"></a>  CGlobalUtils::CyFromString


```
BOOL CyFromString(
    CY& cy,
    LPCTSTR psz);
```

### <a name="parameters"></a>Parametry

*CY*<br/>
[out] [in] *psz*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

##  <a name="decimalfromstring"></a>  CGlobalUtils::DecimalFromString


```
BOOL DecimalFromString(
    DECIMAL& decimal,
    LPCTSTR psz);
```

### <a name="parameters"></a>Parametry

*decimal*<br/>
[out] [in] *psz*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

##  <a name="fliprect"></a>  CGlobalUtils::FlipRect


```
void FlipRect(
    CRect& rect,
    int nDegrees);
```

### <a name="parameters"></a>Parametry

*Rect*<br/>
[out w] [in] *nDegrees*

### <a name="remarks"></a>Uwagi

##  <a name="forceadjustlayout"></a>  CGlobalUtils::ForceAdjustLayout


```
void ForceAdjustLayout(
    CDockingManager* pDockManager,
    BOOL bForce = FALSE,
    BOOL bForceInvisible = FALSE);
```

### <a name="parameters"></a>Parametry

*pDockManager*<br/>
[out w] [in] *bForce* [in] *bForceInvisible*

### <a name="remarks"></a>Uwagi

##  <a name="getdockingmanager"></a>  CGlobalUtils::GetDockingManager


```
CDockingManager* GetDockingManager(CWnd* pWnd);
```

### <a name="parameters"></a>Parametry

[in] *pWnd*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

##  <a name="getoppositealignment"></a>  CGlobalUtils::GetOppositeAlignment


```
DWORD GetOppositeAlignment(DWORD dwAlign);
```

### <a name="parameters"></a>Parametry

[in] *dwAlign*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

##  <a name="getpaneandalignfrompoint"></a>  CGlobalUtils::GetPaneAndAlignFromPoint


```
BOOL GetPaneAndAlignFromPoint(
    CPaneContainerManager& barContainerManager,
    CPoint pt,
    CDockablePane** ppTargetControlBar,
    DWORD& dwAlignment,
    BOOL& bTabArea,
    BOOL& bCaption);
```

### <a name="parameters"></a>Parametry

*barContainerManager*<br/>
[in] [in] *pt*
*ppTargetControlBar*<br/>
[out] [out] *dwAlignment*
*bTabArea*<br/>
[out] [out] *bCaption*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

##  <a name="getwndicon"></a>  CGlobalUtils::GetWndIcon


```
HICON GetWndIcon(CWnd* pWnd);
```

### <a name="parameters"></a>Parametry

[in] *pWnd*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

##  <a name="setnewparent"></a>  CGlobalUtils::SetNewParent


```
void SetNewParent(
    CObList& lstControlBars,
    CWnd* pNewParent,
    BOOL bCheckVisibility = TRUE);
```

### <a name="parameters"></a>Parametry

*lstControlBars*<br/>
[in] [in] *pNewParent* [in] *bCheckVisibility*

### <a name="remarks"></a>Uwagi

##  <a name="stringfromcy"></a>  CGlobalUtils::StringFromCy


```
BOOL StringFromCy(
    CString& str,
    CY& cy);
```

### <a name="parameters"></a>Parametry

*str*<br/>
[out] [in] *cy*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

##  <a name="stringfromdecimal"></a>  CGlobalUtils::StringFromDecimal


```
BOOL StringFromDecimal(
    CString& str,
    DECIMAL& decimal);
```

### <a name="parameters"></a>Parametry

*str*<br/>
[out] [in] *dziesiętna*

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)

---
description: 'Dowiedz się więcej na temat: Klasa CMFCDropDownToolBar'
title: Klasa CMFCDropDownToolBar
ms.date: 11/19/2018
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
ms.openlocfilehash: 158562829cb5bbebfb9a858d34751c56bdf46ed8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293992"
---
# <a name="cmfcdropdowntoolbar-class"></a>Klasa CMFCDropDownToolBar

Pasek narzędzi, który pojawia się, gdy użytkownik naciśnie przycisk paska narzędzi najwyższego poziomu.

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

## <a name="syntax"></a>Składnia

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Przesłania `CPane::AllowShowOnPaneMenu`).|
|[CMFCDropDownToolBar::LoadBitmap](#loadbitmap)|(Przesłania [CMFCToolBar:: LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap).)|
|[CMFCDropDownToolBar::LoadToolBar](#loadtoolbar)|(Przesłania [CMFCToolBar:: LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar).)|
|[CMFCDropDownToolBar::OnLButtonUp](#onlbuttonup)||
|[CMFCDropDownToolBar:: OnMouseMove](#onmousemove)||
|[CMFCDropDownToolBar::OnSendCommand](#onsendcommand)|(Przesłania `CMFCToolBar::OnSendCommand`).|
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|(Przesłania [CMFCToolBar:: OnUpdateCmdUI](cmfctoolbar-class.md).|

### <a name="remarks"></a>Uwagi

`CMFCDropDownToolBar`Obiekt łączy wizualny wygląd paska narzędzi z zachowaniem menu podręcznego. Gdy użytkownik naciśnie i utrzymuje przycisk paska narzędzi listy rozwijanej (patrz [Klasa CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)), pojawi się pasek narzędzi listy rozwijanej, a użytkownik może wybrać przycisk z paska narzędzi rozwijanych, przewijając do niego i zwalniając przycisk myszy. Gdy użytkownik wybierze przycisk na pasku narzędzi listy rozwijanej, ten przycisk jest wyświetlany jako bieżący przycisk na pasku narzędzi najwyższego poziomu.

Pasek narzędzi listy rozwijanej nie może być dostosowany ani zadokowany i nie ma stanu odrywania.

Na poniższej ilustracji przedstawiono `CMFCDropDownToolBar` obiekt:

![Przykład CMFCDropDownToolbar](../../mfc/reference/media/cmfcdropdown.png "Przykład CMFCDropDownToolbar")

Tworzysz `CMFCDropDownToolBar` obiekt w taki sam sposób, jak utworzysz zwykły pasek narzędzi (zobacz [Klasa CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)).

Aby wstawić pasek narzędzi listy rozwijanej do nadrzędnego paska narzędzi:

1. Zarezerwuj fikcyjny identyfikator zasobu dla przycisku w zasobie nadrzędnego paska narzędzi.

2. Utwórz `CMFCDropDownToolBarButton` obiekt, który zawiera pasek narzędzi listy rozwijanej (Aby uzyskać więcej informacji, zobacz [CMFCDropDownToolbarButton:: CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)).

3. Zastąp przycisk fikcyjny `CMFCDropDownToolBarButton` obiektem za pomocą [CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Aby uzyskać więcej informacji na temat przycisków paska narzędzi, zobacz [Przewodnik: umieszczanie formantów na paskach narzędzi](../../mfc/walkthrough-putting-controls-on-toolbars.md). Przykład paska narzędzi listy rozwijanej można znaleźć w przykładowym projekcie VisualStudioDemo.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia `Create` metody w `CMFCDropDownToolBar` klasie. Ten fragment kodu jest częścią [przykładu demonstracyjnego Visual Studio](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdropdowntoolbar. h

## <a name="cmfcdropdowntoolbarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a> CMFCDropDownToolBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcdropdowntoolbarloadbitmap"></a><a name="loadbitmap"></a> CMFCDropDownToolBar::LoadBitmap

Ładuje obrazy pasków narzędzi z zasobów aplikacji.

```
virtual BOOL LoadBitmap(
    UINT uiResID,
    UINT uiColdResID=0,
    UINT uiMenuResID=0,
    BOOL bLocked=FALSE,
    UINT uiDisabledResID=0,
    UINT uiMenuDisabledResID=0);
```

### <a name="parameters"></a>Parametry

*uiResID*<br/>
podczas Identyfikator zasobu mapy bitowej, który odwołuje się do obrazów gorącego paska narzędzi.

*uiColdResID*<br/>
podczas Identyfikator zasobu mapy bitowej odwołujący się do obrazów zimnego paska narzędzi.

*uiMenuResID*<br/>
podczas Identyfikator zasobu mapy bitowej, który odwołuje się do zwykłych obrazów menu.

*Blokada*<br/>
podczas Wartość TRUE, aby zablokować pasek narzędzi; w przeciwnym razie FALSE.

*uiDisabledResID*<br/>
podczas Identyfikator zasobu mapy bitowej odwołujący się do wyłączonych obrazów pasków narzędzi.

*uiMenuDisabledResID*<br/>
podczas Identyfikator zasobu mapy bitowej, który odwołuje się do wyłączonych obrazów menu.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli metoda się powiedzie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Metoda [CMFCToolBar:: LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) wywołuje tę metodę w celu załadowania obrazów skojarzonych z paskiem narzędzi. Zastąp tę metodę, aby wykonać niestandardowe ładowanie zasobów obrazu.

Wywołaj `LoadBitmapEx` metodę, aby załadować dodatkowe obrazy po utworzeniu paska narzędzi.

## <a name="cmfcdropdowntoolbarloadtoolbar"></a><a name="loadtoolbar"></a> CMFCDropDownToolBar::LoadToolBar

```
virtual BOOL LoadToolBar(
    UINT uiResID,
    UINT uiColdResID = 0,
    UINT uiMenuResID = 0,
    BOOL = FALSE,
    UINT uiDisabledResID = 0,
    UINT uiMenuDisabledResID = 0,
    UINT uiHotResID = 0);
```

### <a name="parameters"></a>Parametry

podczas *uiResID*<br/>

podczas *uiColdResID*<br/>

podczas *uiMenuResID*<br/>

podczas Wartość *logiczna*<br/>

podczas *uiDisabledResID*<br/>

podczas *uiMenuDisabledResID*<br/>

podczas *uiHotResID*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcdropdowntoolbaronlbuttonup"></a><a name="onlbuttonup"></a> CMFCDropDownToolBar::OnLButtonUp

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Parametry

podczas *nFlags*<br/>

podczas *punkt*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcdropdowntoolbaronmousemove"></a><a name="onmousemove"></a> CMFCDropDownToolBar:: OnMouseMove

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Parametry

podczas *nFlags*<br/>

podczas *punkt*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcdropdowntoolbaronsendcommand"></a><a name="onsendcommand"></a> CMFCDropDownToolBar::OnSendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parametry

podczas *pButton*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcdropdowntoolbaronupdatecmdui"></a><a name="onupdatecmdui"></a> CMFCDropDownToolBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametry

podczas *pTarget*<br/>

podczas *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBar:: Create](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Klasa CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[Wskazówki: umieszczanie formantów na paskach narzędzi](../../mfc/walkthrough-putting-controls-on-toolbars.md)

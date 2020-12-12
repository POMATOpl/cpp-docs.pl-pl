---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonMiniToolBar'
title: Klasa CMFCRibbonMiniToolBar
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
ms.openlocfilehash: 7215349323f8039bccb24860e4e5ad663bd24bcd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273946"
---
# <a name="cmfcribbonminitoolbar-class"></a>Klasa CMFCRibbonMiniToolBar

Implementuje kontekstowy podręczny pasek narzędzi.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Konstruktor domyślny.|
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CreateObject`|Używane przez platformę do tworzenia wystąpienia dynamicznego tego typu klasy.|
|`CMFCRibbonMiniToolBar::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|
|[CMFCRibbonMiniToolBar:: ismode](#iscontextmenumode)||
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(Przesłania `CMFCPopupMenu::IsRibbonMiniToolBar`).|
|[CMFCRibbonMiniToolBar:: SetCommands](#setcommands)|Ustawia listę poleceń, które mają być wyświetlane na pasku narzędzi.|
|[CMFCRibbonMiniToolBar:: show](#show)|Wyświetla minipasek narzędzi na określonych współrzędnych ekranu.|
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|Wyświetla minipasek narzędzi wraz z menu kontekstowym.|

## <a name="remarks"></a>Uwagi

Minipasek narzędzi jest zwykle wyświetlany po wybraniu przez użytkownika obiektu w dokumencie. Na przykład, gdy użytkownik wybierze blok tekstu w edytorze tekstów, aplikacja wyświetli minipasek narzędzi, który zawiera polecenia formatowania tekstu.

Minipasek narzędzi jest przezroczysty, gdy wskaźnik myszy znajduje się poza granicami minipaska narzędzi.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

`CMFCRibbonPanelMenu`

[CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxRibbonMiniToolBar. h

## <a name="cmfcribbonminitoolbarsetcommands"></a><a name="setcommands"></a> CMFCRibbonMiniToolBar:: SetCommands

Ustawia listę poleceń, które mają być wyświetlane na pasku narzędzi.

```cpp
void SetCommands(
    CMFCRibbonBar* pRibbonBar,
    const CList<UINT,UINT>& lstCommands);
```

### <a name="parameters"></a>Parametry

*pRibbonBar*<br/>
podczas Pasek wstążki, który umożliwia wyszukiwanie przycisków na ekranie przy użyciu minipaska narzędzi.

*lstCommands*<br/>
podczas Lista poleceń, które mają być wyświetlane na minipasku narzędzi. Wszystkie kategorie wstążki są przeszukiwane, aby znaleźć skojarzone przyciski.

### <a name="remarks"></a>Uwagi

Ta funkcja służy do ustawiania listy poleceń, które mają być wyświetlane na minipasku narzędzi.

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia `SetCommands` metody `CMFCRibbonMiniToolBar` klasy. Ten fragment kodu jest częścią [przykładu demonstracyjnego pakietu MS Office 2007](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]

## <a name="cmfcribbonminitoolbarshow"></a><a name="show"></a> CMFCRibbonMiniToolBar:: show

Wyświetla minipasek narzędzi na określonych współrzędnych ekranu.

```
BOOL Show(
    int x,
    int y);
```

### <a name="parameters"></a>Parametry

*x*<br/>
podczas Określa położenie w poziomie minipaska narzędzi na współrzędne ekranu.

*Y*<br/>
podczas Określa pionową pozycję minipaska narzędzi w współrzędnych ekranu.

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli minipasek narzędzi został pomyślnie wyświetlony; w przeciwnym razie FALSE.

## <a name="cmfcribbonminitoolbarshowwithcontextmenu"></a><a name="showwithcontextmenu"></a> CMFCRibbonMiniToolBar::ShowWithContextMenu

Wyświetla minipasek narzędzi wraz z menu kontekstowym.

```
BOOL ShowWithContextMenu(
    int x,
    int y,
    UINT uiMenuResID,
    CWnd* pWndOwner);
```

### <a name="parameters"></a>Parametry

*x*<br/>
podczas Określa położenie menu kontekstowego w poziomie.

*Y*<br/>
podczas Określa położenie menu kontekstowego w obszarze Współrzędne ekranu.

*uiMenuResID*<br/>
podczas Określa identyfikator zasobu menu kontekstowego do wyświetlenia.

*pWndOwner*<br/>
podczas Identyfikuje okno, które odbiera komunikaty z menu kontekstowego.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli menu kontekstowe zostało wyświetlone pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Użyj tej funkcji, aby wyświetlić minipasek narzędzi z menu kontekstowym. Menu kontekstowe jest rozmieszczone 15 pikseli poniżej minipaska narzędzi.

## <a name="cmfcribbonminitoolbariscontextmenumode"></a><a name="iscontextmenumode"></a> CMFCRibbonMiniToolBar:: ismode

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
BOOL IsContextMenuMode() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonminitoolbarisribbonminitoolbar"></a><a name="isribbonminitoolbar"></a> CMFCRibbonMiniToolBar::IsRibbonMiniToolBar

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
virtual BOOL IsRibbonMiniToolBar() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)

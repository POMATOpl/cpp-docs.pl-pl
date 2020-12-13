---
description: 'Dowiedz się więcej na temat: Klasa CMFCPopupMenuBar'
title: Klasa CMFCPopupMenuBar
ms.date: 11/04/2016
f1_keywords:
- CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::AdjustSizeImmediate
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::BuildOrigItems
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::CloseDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ExportToMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::FindDestintationToolBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetCurrentMenuImageSize
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetDefaultMenuId
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetLastCommandIndex
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ImportFromMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsDropDownListMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsPaletteMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanel
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanelInRegularMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::LoadFromHash
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::RestoreDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetButtonStyle
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::StartPopupMenuTimer
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::m_bDisableSideBarInXPMode
helpviewer_keywords:
- CMFCPopupMenuBar [MFC], AdjustSizeImmediate
- CMFCPopupMenuBar [MFC], BuildOrigItems
- CMFCPopupMenuBar [MFC], CloseDelayedSubMenu
- CMFCPopupMenuBar [MFC], ExportToMenu
- CMFCPopupMenuBar [MFC], FindDestintationToolBar
- CMFCPopupMenuBar [MFC], GetCurrentMenuImageSize
- CMFCPopupMenuBar [MFC], GetDefaultMenuId
- CMFCPopupMenuBar [MFC], GetLastCommandIndex
- CMFCPopupMenuBar [MFC], GetOffset
- CMFCPopupMenuBar [MFC], ImportFromMenu
- CMFCPopupMenuBar [MFC], IsDropDownListMode
- CMFCPopupMenuBar [MFC], IsPaletteMode
- CMFCPopupMenuBar [MFC], IsRibbonPanel
- CMFCPopupMenuBar [MFC], IsRibbonPanelInRegularMode
- CMFCPopupMenuBar [MFC], LoadFromHash
- CMFCPopupMenuBar [MFC], RestoreDelayedSubMenu
- CMFCPopupMenuBar [MFC], SetButtonStyle
- CMFCPopupMenuBar [MFC], SetOffset
- CMFCPopupMenuBar [MFC], StartPopupMenuTimer
- CMFCPopupMenuBar [MFC], m_bDisableSideBarInXPMode
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
ms.openlocfilehash: 4db8c02ed92aec5243f9a2c7800c6fd1f9747751
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334740"
---
# <a name="cmfcpopupmenubar-class"></a>Klasa CMFCPopupMenuBar

Pasek menu osadzony w menu podręcznym.

## <a name="syntax"></a>Składnia

```
class CMFCPopupMenuBar : public CMFCToolBar
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|Natychmiast ponownie oblicza układ okienka. (Przesłania [CPane:: AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|Ładuje elementy menu podręcznego z określonego zasobu menu.|
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Zamyka przycisk menu podręcznego.|
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|Tworzy menu za pomocą przycisków menu podręcznego.|
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Lokalizuje pasek narzędzi, w którym znajduje się określony punkt.|
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Wskazuje rozmiar obrazów przycisków menu.|
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Zwraca identyfikator domyślnego elementu menu.|
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|Pobiera indeks ostatnio wywoływanego polecenia menu.|
|[CMFCPopupMenuBar:: GetOffset](#getoffset)|Pobiera przesunięcie wiersza paska menu podręcznego.|
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|Importuje przyciski menu podręcznego z określonego menu.|
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|Wskazuje, czy pasek menu podręcznego znajduje się w trybie listy rozwijanej.|
|[CMFCPopupMenuBar:: ispaletmode](#ispalettemode)|Wskazuje, czy pasek menu podręcznego jest w trybie palety.|
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|Wskazuje, czy jest to panel wstążki (domyślnie FALSE).|
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Wskazuje, czy jest to panel wstążki w trybie regularnym (domyślnie FALSE).|
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|Ładuje zarchiwizowane menu.|
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Przywraca przycisk menu opóźniony do zamykania paska menu podręcznego.|
|[CMFCPopupMenuBar:: SetButton](#setbuttonstyle)|Ustawia styl przycisku paska narzędzi w danym indeksie. (Przesłania [CMFCToolBar:: SetButton](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)).|
|[CMFCPopupMenuBar:: SetOffset](#setoffset)|Ustawia przesunięcie wiersza paska menu podręcznego.|
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|Uruchamia czasomierz dla określonego przycisku opóźnionego menu podręcznego.|

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMFCPopupMenuBar:: m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Określa, czy szary pasek boczny będzie wyświetlany, gdy aplikacja ma wygląd systemu Windows XP.|

## <a name="remarks"></a>Uwagi

`CMFCPopupMenuBar`Jest tworzony w tym samym czasie co [Klasa CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) i osadzony w nim. `CMFCPopupMenuBar`Obejmuje cały obszar klienta `CMFCPopupMenu` obiektu. Obsługuje ona dane wejściowe klawiatury i myszy. Komunikuje się ona również z danymi wejściowymi do `CMFCPopupMenu` okna i z oknem ramki najwyższego poziomu.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano, jak zainicjować `CMFCPopupMenuBar` obiekt z `CMFCPopupMenu` obiektu. Ten fragment kodu jest częścią [przykładu rysowania klienta](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxpopupmenubar. h

## <a name="cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a> CMFCPopupMenuBar::AdjustSizeImmediate

Natychmiast ponownie oblicza układ okienka paska menu podręcznego. (Przesłania [CPane:: AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```

### <a name="parameters"></a>Parametry

*bRecalcLayout*<br/>
podczas Wartość TRUE powoduje automatyczne ponowne obliczenie układu okienka paska menu podręcznego. w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a> CMFCPopupMenuBar::BuildOrigItems

Ładuje elementy menu podręcznego z określonego zasobu menu.

```
BOOL BuildOrigItems(UINT uiMenuResID);
```

### <a name="parameters"></a>Parametry

*uiMenuResID*<br/>
podczas Określa identyfikator menu zasobu menu do załadowania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli wartość jest zakończona pomyślnie, lub FALSE, jeśli nie.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a> CMFCPopupMenuBar::CloseDelayedSubMenu

Zamyka przycisk menu podręcznego, który został opóźniony.

```
virtual void CloseDelayedSubMenu();
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a> CMFCPopupMenuBar::ExportToMenu

Tworzy menu za pomocą przycisków menu podręcznego.

```
virtual HMENU ExportToMenu() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca uchwyt do nowego menu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a> CMFCPopupMenuBar::FindDestintationToolBar

Lokalizuje pasek narzędzi, w którym znajduje się określony punkt.

```
CMFCToolBar* FindDestintationToolBar(CPoint point);
```

### <a name="parameters"></a>Parametry

*moment*<br/>
podczas Punkt na ekranie.

### <a name="return-value"></a>Wartość zwracana

Zwraca uchwyt do paska narzędzi, w którym znajduje się punkt, jeśli istnieje lub ma wartość NULL, jeśli nie.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a> CMFCPopupMenuBar::GetCurrentMenuImageSize

Wskazuje rozmiar obrazów przycisków menu.

```
virtual CSize GetCurrentMenuImageSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca rozmiar obrazów przycisków menu na pasku narzędzi.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a> CMFCPopupMenuBar::GetDefaultMenuId

Zwraca identyfikator domyślnego elementu menu.

```
UINT GetDefaultMenuId() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca identyfikator domyślnego elementu menu na pasku menu podręcznego.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a> CMFCPopupMenuBar::GetLastCommandIndex

Pobiera indeks ostatnio wywoływanego polecenia menu.

```
static int __stdcall GetLastCommandIndex();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca indeks ostatniego polecenia menu, które zostało wywołane.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubargetoffset"></a><a name="getoffset"></a> CMFCPopupMenuBar:: GetOffset

Pobiera przesunięcie wiersza paska menu podręcznego.

```
int GetOffset() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca przesunięcie wiersza paska menu podręcznego.

### <a name="remarks"></a>Uwagi

Ta wartość jest ustawiana za pomocą [CMFCPopupMenuBar:: SetOffset](#setoffset).

## <a name="cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a> CMFCPopupMenuBar::ImportFromMenu

Importuje przyciski menu podręcznego z określonego menu.

```
virtual BOOL ImportFromMenu(
    HMENU hMenu,
    BOOL bShowAllCommands = FALSE);
```

### <a name="parameters"></a>Parametry

*hMenu*<br/>
podczas Menu, z którego mają zostać zaimportowane przyciski menu podręcznego.

*bShowAllCommands*<br/>
podczas Ma wartość TRUE, jeśli wszystkie polecenia w menu mają być importowane lub FAŁSZ, jeśli rzadko używane wartości mogą być ukryte.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość PRAWDA, jeśli przyciski menu zostały pomyślnie zaimportowane z menu, lub wartość FAŁSZ, jeśli nie.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a> CMFCPopupMenuBar::IsDropDownListMode

Wskazuje, czy pasek menu podręcznego znajduje się w trybie listy rozwijanej.

```
BOOL IsDropDownListMode() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli pasek menu podręcznego znajduje się w trybie listy rozwijanej lub ma wartość FAŁSZ, jeśli nie.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a> CMFCPopupMenuBar:: ispaletmode

Wskazuje, czy pasek menu podręcznego jest w trybie palety.

```
BOOL IsPaletteMode() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli tryb palety jest włączony, lub FALSE, jeśli nie.

### <a name="remarks"></a>Uwagi

Gdy pasek menu jest ustawiony na tryb palety, elementy menu są wyświetlane w wielu kolumnach i ograniczonej liczbie wierszy.

## <a name="cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a> CMFCPopupMenuBar::IsRibbonPanel

Wskazuje, czy jest to panel wstążki (domyślnie FALSE).

```
virtual BOOL IsRibbonPanel() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość FALSE domyślnie, wskazując, że nie jest to panel wstążki.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a> CMFCPopupMenuBar::IsRibbonPanelInRegularMode

Wskazuje, czy jest to panel wstążki w trybie regularnym (domyślnie FALSE).

```
virtual BOOL IsRibbonPanelInRegularMode() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość FALSE domyślnie, wskazując, że nie jest to panel wstążki w trybie regularnym.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a> CMFCPopupMenuBar::LoadFromHash

Ładuje zarchiwizowane menu.

```
BOOL LoadFromHash(HMENU hMenu);
```

### <a name="parameters"></a>Parametry

*hMenu*<br/>
podczas Uchwyt do zarchiwizowanego menu do załadowania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli menu zostało załadowane pomyślnie, lub FALSE, jeśli nie.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarm_bdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a> CMFCPopupMenuBar:: m_bDisableSideBarInXPMode

Parametr logiczny, który wskazuje, czy aplikacja ma szary pasek boczny, gdy ma wygląd systemu Windows XP.

```
BOOL m_bDisableSideBarInXPMode;
```

### <a name="remarks"></a>Uwagi

Jeśli ta zmienna członkowska ma wartość FAŁSZ, a aplikacja ma wygląd systemu Windows XP, struktura rysuje szary pasek boczny w aplikacji.

Wartość domyślna to FALSE.

## <a name="cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a> CMFCPopupMenuBar::RestoreDelayedSubMenu

Przywraca przycisk menu opóźniony do zamykania paska menu podręcznego.

```
virtual void RestoreDelayedSubMenu();
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a> CMFCPopupMenuBar:: SetButton

Ustawia styl przycisku paska narzędzi w danym indeksie. (Przesłania [CMFCToolBar:: SetButton](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)).

```
virtual void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametry

*nIndex*<br/>
podczas Indeks (liczony od zera) przycisku paska narzędzi, którego styl ma być ustawiony.

*nStyle*<br/>
podczas Styl przycisku. Zobacz [Style formantów paska narzędzi](../../mfc/reference/toolbar-control-styles.md) , aby wyświetlić listę dostępnych stylów przycisków paska narzędzi.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a> CMFCPopupMenuBar:: SetOffset

Ustawia przesunięcie wiersza paska menu podręcznego.

```cpp
void SetOffset(int iOffset);
```

### <a name="parameters"></a>Parametry

*iOffset*<br/>
podczas Liczba wierszy, które mają być przesunięte na pasku menu podręcznego.

### <a name="remarks"></a>Uwagi

## <a name="cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a> CMFCPopupMenuBar::StartPopupMenuTimer

Uruchamia czasomierz dla określonego przycisku opóźnionego menu podręcznego.

```cpp
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,
    int nDelayFactor = 1);
```

### <a name="parameters"></a>Parametry

*pMenuButton*<br/>
podczas Wskaźnik do przycisku menu, dla którego ma zostać ustawiony czasomierz opóźnienia.

*nDelayFactor*<br/>
podczas Współczynnik opóźnienia, równy co najmniej jeden, do pomnożenia przez standardowy czas opóźnienia menu (zazwyczaj między pół sekundy i pięć sekund).

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)<br/>
[Klasa CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

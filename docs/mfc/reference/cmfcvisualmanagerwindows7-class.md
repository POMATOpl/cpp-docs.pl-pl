---
description: 'Dowiedz się więcej na temat: Klasa CMFCVisualManagerWindows7'
title: Klasa CMFCVisualManagerWindows7
ms.date: 03/27/2019
f1_keywords:
- CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::OnFillMenuImageRect
helpviewer_keywords:
- CMFCVisualManagerWindows7 Class [MFC]
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
ms.openlocfilehash: 108d4144bbcfbfcb82d91678611435f14365302e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331629"
---
# <a name="cmfcvisualmanagerwindows7-class"></a>Klasa CMFCVisualManagerWindows7

`CMFCVisualManagerWindows7`Nadaje aplikacji wygląd aplikacji systemu Windows 7.

## <a name="syntax"></a>Składnia

```
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7)|Konstruktor domyślny.|
|[CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7](#_dtorcmfcvisualmanagerwindows7)|Domyślny destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCVisualManagerWindows7::CleanStyle`|Czyści bieżący styl wizualizacji i resetuje domyślny styl wizualizacji.|
|`CMFCVisualManagerWindows7::CleanUp`|Czyści wszystkie obiekty w interfejsie użytkownika i resetuje menu.|
|`CMFCVisualManagerWindows7::DrawNcBtn`|Rysuje przycisk w obszarze nieklienckim w ramce. Struktura używa tej metody do rysowania przycisków Minimalizuj, Maksymalizuj, Zamknij i Przywróć w prawym górnym rogu ramki okna. Ta metoda jest wywoływana tylko wtedy, gdy program używa `Aero` motywu.|
|`CMFCVisualManagerWindows7::DrawNcText`|Rysuje tekst w obszarze nieklienckim w ramce. Struktura używa tej metody do rysowania tytułu aplikacji na pasku tytułu w górnej części okna ramki.|
|`CMFCVisualManagerWindows7::DrawSeparator`|Rysuje separator [klasy CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md).|
|`CMFCVisualManagerWindows7::GetRibbonBar`|Pobiera [klasę CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md) skojarzoną z interfejsem użytkownika.|
|[CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor](#getribboneditbackgroundcolor)|Uzyskuje kolor tła pola edycji wstążki.|
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|Przesłania [CMFCVisualManager:: GetRibbonPopupBorderSize](../../mfc/reference/cmfcvisualmanager-class.md#getribbonpopupbordersize)|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|Przesłania [CMFCVisualManager:: GetRibbonQuickAccessToolBarChevronOffset](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarchevronoffset)|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|Przesłania [CMFCVisualManager:: GetRibbonQuickAccessToolBarRightMargin](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarrightmargin)|
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|Przesłania [CMFCVisualManagerWindows:: IsHighlightWholeMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ishighlightwholemenuitem)|
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|Przesłania [CMFCVisualManager:: IsOwnerDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#isownerdrawmenucheck)|
|`CMFCVisualManagerWindows7::IsRibbonPresent`|Określa, czy element `CMFCRibbonBar` jest obecny i widoczny.|
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|Przesłania [CMFCVisualManagerWindows:: OnDrawButtonBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawbuttonborder)|
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|Przesłania [CMFCVisualManagerWindows:: OnDrawCheckBoxEx](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcheckboxex)|
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|Przesłania [CMFCVisualManagerWindows:: OnDrawComboDropButton](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcombodropbutton)|
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|Przesłania [CMFCVisualManager:: OnDrawDefaultRibbonImage](../../mfc/reference/cmfcvisualmanager-class.md#ondrawdefaultribbonimage)|
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|Przesłania [CMFCVisualManagerWindows:: OnDrawMenuBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawmenuborder)|
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|Przesłania [CMFCVisualManager:: OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck)|
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|Przesłania [CMFCVisualManager:: OnDrawMenuLabel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenulabel)|
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|Powoduje `CMFCVisualManager::OnDrawRadioButton`|
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|Przesłania [CMFCVisualManager:: OnDrawRibbonApplicationButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonapplicationbutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|Przesłania [CMFCVisualManager:: OnDrawRibbonButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonborder)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|Przesłania [CMFCVisualManager:: OnDrawRibbonCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaption)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|Przesłania [CMFCVisualManager:: OnDrawRibbonCaptionButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaptionbutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|Przesłania [CMFCVisualManager:: OnDrawRibbonCategory](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategory)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|Przesłania [CMFCVisualManager:: OnDrawRibbonCategoryTab](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab)|
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|Przesłania [CMFCVisualManager:: OnDrawRibbonDefaultPaneButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbondefaultpanebutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|Przesłania [CMFCVisualManager:: OnDrawRibbonGalleryButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbongallerybutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|Powoduje `CMFCVisualManager::OnDrawRibbonLaunchButton`|
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|Przesłania [CMFCVisualManager:: OnDrawRibbonMenuCheckFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonmenucheckframe)|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|Przesłania [CMFCVisualManager:: OnDrawRibbonPanel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanel)|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|Przesłania [CMFCVisualManager:: OnDrawRibbonPanelCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanelcaption)|
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|Przesłania [CMFCVisualManager:: OnDrawRibbonProgressBar](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonprogressbar)|
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|Przesłania [CMFCVisualManager:: OnDrawRibbonRecentFilesFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonrecentfilesframe)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|Przesłania [CMFCVisualManager:: OnDrawRibbonSliderChannel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderchannel)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|Przesłania [CMFCVisualManager:: OnDrawRibbonSliderThumb](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderthumb)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|Przesłania [CMFCVisualManager:: OnDrawRibbonSliderZoomButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderzoombutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|Przesłania [CMFCVisualManager:: OnDrawRibbonStatusBarPane](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonstatusbarpane)|
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|Przesłania [CMFCVisualManager:: OnDrawRibbonTabsFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbontabsframe)|
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|Przesłania [CMFCVisualManagerWindows:: OnDrawStatusBarSizeBox](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawstatusbarsizebox)|
|`CMFCVisualManagerWindows7::OnFillBarBackground`|Przesłania [CMFCVisualManagerWindows:: OnFillBarBackground](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbarbackground)|
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|Przesłania [CMFCVisualManagerWindows:: OnFillButtonInterior](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbuttoninterior)|
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](#onfillmenuimagerect)|Struktura wywołuje tę metodę, gdy wypełnia obszar wokół obrazów elementów menu.|
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|Przesłania [CMFCVisualManager:: OnFillRibbonButton](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonbutton)|
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|Przesłania [CMFCVisualManager:: OnFillRibbonQuickAccessToolBarPopup](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonquickaccesstoolbarpopup)|
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|Przesłania [CMFCVisualManagerWindows:: OnHighlightMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onhighlightmenuitem)|
|`CMFCVisualManagerWindows7::OnNcActivate`|Przesłania [CMFCVisualManager:: OnNcActivate](../../mfc/reference/cmfcvisualmanager-class.md#onncactivate)|
|`CMFCVisualManagerWindows7::OnNcPaint`|Przesłania [CMFCVisualManager:: OnNcPaint](../../mfc/reference/cmfcvisualmanager-class.md#onncpaint)|
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|Przesłania [CMFCVisualManagerWindows:: OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onupdatesystemcolors)|
|`CMFCVisualManagerWindows7::SetResourceHandle`|Ustawia dojście do zasobów opisujące atrybuty programu Visual Manager.|
|`CMFCVisualManagerWindows7::SetStyle`|Ustawia schemat kolorów `CMFCVisualManagerWindows7` graficznego interfejsu użytkownika.|

## <a name="remarks"></a>Uwagi

Użyj `CMFCVisualManagerWindows7` klasy, aby zmienić wygląd aplikacji w taki sposób, aby naśladować domyślną aplikację systemu Windows 7. Ta klasa może być nieważna, jeśli aplikacja jest uruchomiona w systemie Windows w wersji starszej niż Windows 7. W tym scenariuszu aplikacja używa domyślnego programu Visual Manager zdefiniowanego w [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md).

CMFCVisualManagerWindows7 dziedziczy wiele metod zarówno z [klasy CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md) , jak i `CMFCVisualManager` klasy. Metody wymienione w poprzedniej sekcji są metodami nowymi dla `CMFCVisualManagerWindows7` klasy.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)

`CMFCVisualManagerWindows7`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxvisualmanagerwindows7. h

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="_dtorcmfcvisualmanagerwindows7"></a> CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7

Domyślny destruktor.

```
virtual ~CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="cmfcvisualmanagerwindows7"></a> CMFCVisualManagerWindows7::CMFCVisualManagerWindows7

Konstruktor domyślny.

```
CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7getribboneditbackgroundcolor"></a><a name="getribboneditbackgroundcolor"></a> CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor

Uzyskuje kolor tła pola edycji wstążki.

```
virtual COLORREF GetRibbonEditBackgroundColor (
    CMFCRibbonRichEditCtrl* pEdit,
    BOOL bIsHighlighted,
    BOOL bIsPaneHighlighted,
    BOOL bIsDisabled);
```

### <a name="parameters"></a>Parametry

*pEdit*<br/>
podczas Wskaźnik do kontrolki edycji. Ta wartość nie może być RÓWNa NULL.

*bIsHighlighted*<br/>
określoną Zwraca czy pole wstążki jest wyróżnione.

*bIsPaneHighlighted*<br/>
określoną Zwraca wartość TRUE, jeśli panel wstążki zawierający *pEdit* jest wyróżniony.

*bIsDisabled*<br/>
określoną Zwraca czy *pEdit* jest wyłączona.

### <a name="return-value"></a>Wartość zwracana

Kolor tła pola edycji *pEdit*.

### <a name="remarks"></a>Uwagi

## <a name="cmfcvisualmanagerwindows7onfillmenuimagerect"></a><a name="onfillmenuimagerect"></a> CMFCVisualManagerWindows7::OnFillMenuImageRect

Struktura wywołuje tę metodę, gdy wypełnia obszar wokół obrazu elementu menu.

```
virtual void OnFillMenuImageRect(
    CDC* pDC,
    CMFCToolBarButton* pButton,
    CRect rectangle,
    CMFCVisualManager::AFX_BUTTON_STATE state);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia przycisku menu.

*pButton*<br/>
podczas Wskaźnik do `CMFCToolBarButton` . Struktura wypełnia tło tego przycisku.

*prostokąt*<br/>
podczas Prostokąt, który określa granice obszaru obrazu przycisku menu.

*Państwu*<br/>
podczas Stan przycisku.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[Klasa CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)

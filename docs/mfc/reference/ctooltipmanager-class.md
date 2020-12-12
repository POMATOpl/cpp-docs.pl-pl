---
description: 'Dowiedz się więcej na temat: Klasa CTooltipManager'
title: Klasa CTooltipManager
ms.date: 11/04/2016
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
ms.openlocfilehash: 0ec6d691abbceb7026fe9656c17ff899f1d07759
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318549"
---
# <a name="ctooltipmanager-class"></a>Klasa CTooltipManager

Utrzymuje informacje o czasie wykonywania dotyczące etykietek narzędzi. `CTooltipManager`Klasa jest tworzona jednokrotnie dla każdej aplikacji.

## <a name="syntax"></a>Składnia

```
class CTooltipManager : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTooltipManager:: istooltip](#createtooltip)|Tworzy kontrolkę ToolTip dla określonych typów formantów systemu Windows.|
|[CTooltipManager::D eleteToolTip](#deletetooltip)|Usuwa kontrolkę etykietki narzędzia.|
|[CTooltipManager::SetTooltipParams](#settooltipparams)|Dostosowuje wygląd kontrolki etykietki narzędzia dla określonych typów formantów systemu Windows.|
|[CTooltipManager::SetTooltipText](#settooltiptext)|Ustawia tekst i opis kontrolki ToolTip.|
|[CTooltipManager::UpdateTooltips](#updatetooltips)||

## <a name="remarks"></a>Uwagi

Użyj [klasy CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo` i `CTooltipManager` razem, aby zaimplementować niestandardowe etykietki narzędzi w aplikacji. Aby zapoznać się z przykładem sposobu korzystania z tych klas etykietek narzędzi, zobacz temat [Klasa CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md) .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxtooltipmanager. h

## <a name="ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a> CTooltipManager:: istooltip

Tworzy kontrolkę etykietki narzędzia.

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>Parametry

*pToolTip*<br/>
określoną Odwołanie do wskaźnika etykietki narzędzia. Jest on ustawiany tak, aby wskazywał nowo utworzoną etykietkę narzędzia, gdy funkcja zwróci wartość.

*pWndParent*<br/>
podczas Element nadrzędny etykietki narzędzia.

*Npowiadomienia*<br/>
podczas Typ etykietki narzędzia.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli etykietka narzędzia została utworzona pomyślnie.

### <a name="remarks"></a>Uwagi

Musisz wywołać [CTooltipManager::D eletetooltip](#deletetooltip) , aby usunąć formant etykietki narzędzia, który został przeszedł z powrotem w *pToolTip*.

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) ustawia parametry wyświetlania wizualizacji dla każdej etykietki narzędzia, która jest tworzona na podstawie typu etykietki narzędzia, który *npowiadomienia* określa. Aby zmienić parametry dla co najmniej jednego typu etykietki narzędzi, wywołaj [CTooltipManager:: SetTooltipParams](#settooltipparams).

W poniższej tabeli wymieniono prawidłowe typy etykietki narzędzi:

|Typ etykietki narzędzia|Kategoria kontrolki|Przykładowe typy|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|Przycisk.|CMFCButton|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Pasek podpisu.|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|Każda kontrolka, która nie pasuje do innej kategorii.|Brak.|
|AFX_TOOLTIP_TYPE_DOCKBAR|Okienko było dokować.|CDockablePane|
|AFX_TOOLTIP_TYPE_EDIT|Pole tekstowe.|Brak.|
|AFX_TOOLTIP_TYPE_MINIFRAME|Mini.|CPaneFrameWnd|
|AFX_TOOLTIP_TYPE_PLANNER|Planista.|Brak.|
|AFX_TOOLTIP_TYPE_RIBBON|Pasek wstążki.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|
|AFX_TOOLTIP_TYPE_TAB|Kontrolka karta.|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|Pasek narzędzi.|CMFCToolBar, CMFCPopupMenuBar|
|AFX_TOOLTIP_TYPE_TOOLBOX|Przybornik.|Brak.|

## <a name="ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a> CTooltipManager::D eleteToolTip

Usuwa kontrolkę etykietki narzędzia.

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>Parametry

*pToolTip*<br/>
[in. out] Odwołanie do wskaźnika do etykietki narzędzia, które ma zostać zniszczone.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę dla każdej [klasy CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) , która została utworzona za pomocą [CTooltipManager:: istooltip](#createtooltip). Kontrolka nadrzędna powinna wywołać tę metodę z `OnDestroy` programu obsługi. Jest to wymagane, aby prawidłowo usunąć etykietkę narzędzia z struktury. Ta metoda ustawia *pToolTip* na null przed zwróceniem.

## <a name="ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a> CTooltipManager::SetTooltipParams

Dostosowuje wygląd formantu tooltip dla określonych typów formantów systemu Windows.

```cpp
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>Parametry

*nTypes*<br/>
podczas Określa typy kontrolek.

*pRTC*<br/>
podczas Klasa środowiska uruchomieniowego niestandardowej etykietki narzędzia.

*pParams*<br/>
podczas Parametry etykietki narzędzia.

### <a name="remarks"></a>Uwagi

Ta metoda ustawia klasę środowiska uruchomieniowego i początkowe parametry używane przez [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) podczas tworzenia etykietek narzędzi. Gdy kontrolka wywołuje [CTooltipManager::](#createtooltip) CreateInstance i przekazuje w typie etykietki narzędzia, który jest jednym z typów wskazanych przez *nTypes*, Menedżer etykietki narzędzi tworzy formant etykietki narzędzia, który jest wystąpieniem klasy środowiska uruchomieniowego określonego przez *pRTC* i przekazuje parametry określone przez *pParams* do nowej etykietki narzędzia.

Po wywołaniu tej metody wszyscy właściciele etykietek narzędzi otrzymają komunikat AFX_WM_UPDATETOOLTIPS i muszą ponownie utworzyć swoje etykietki narzędzi przy użyciu [CTooltipManager:: istooltip](#createtooltip).

*nTypes* może być dowolną kombinacją prawidłowych typów etykietki narzędzi, które są AFX_TOOLTIP_TYPE_ALL używane przez [CTooltipManager::](#createtooltip) . Jeśli przejdziesz AFX_TOOLTIP_TYPE_ALL, wpłynie to na wszystkie typy etykietek narzędzi.

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia `SetTooltipParams` metody `CTooltipManager` klasy. Ten fragment kodu jest częścią [przykładu rysowania klienta](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

## <a name="ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a> CTooltipManager::SetTooltipText

Ustawia tekst i opis etykietki narzędzia.

```
static void SetTooltipText(
    TOOLINFO* pTI,
    CToolTipCtrl* pToolTip,
    UINT nType,
    const CString strText,
    LPCTSTR lpszDescr=NULL);
```

### <a name="parameters"></a>Parametry

*pTI*<br/>
podczas Wskaźnik do obiektu TOOLINFO.

*pToolTip*<br/>
[in. out] Wskaźnik do kontrolki ToolTip, dla której ma zostać ustawiony tekst i opis.

*Npowiadomienia*<br/>
podczas Określa typ formantu, z którym skojarzona jest ta etykietka narzędzia.

*strText*<br/>
podczas Tekst, który ma zostać ustawiony jako tekst etykietki narzędzia.

*lpszDescr*<br/>
podczas Wskaźnik do opisu etykietki narzędzia. Może mieć wartość NULL.

### <a name="remarks"></a>Uwagi

Wartość *npowiadomienia* musi być taka sama jak wartość parametru *npowiadomienia* [CTooltipManager:: istooltip](#createtooltip) podczas tworzenia etykietki narzędzia.

## <a name="ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a> CTooltipManager::UpdateTooltips

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```cpp
void UpdateTooltips();
```

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[Klasa CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

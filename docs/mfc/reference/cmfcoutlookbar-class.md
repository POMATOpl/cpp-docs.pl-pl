---
description: 'Dowiedz się więcej na temat: Klasa CMFCOutlookBar'
title: Klasa CMFCOutlookBar
ms.date: 06/25/2018
f1_keywords:
- CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar
- AFXOUTLOOKBAR/CMFCOutlookBar::AllowDestroyEmptyTabbedPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanAcceptPane
- AFXOUTLOOKBAR/CMFCOutlookBar::CanSetCaptionTextToTabName
- AFXOUTLOOKBAR/CMFCOutlookBar::Create
- AFXOUTLOOKBAR/CMFCOutlookBar::CreateCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::DoesAllowDynInsertBefore
- AFXOUTLOOKBAR/CMFCOutlookBar::FloatTab
- AFXOUTLOOKBAR/CMFCOutlookBar::GetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::GetTabArea
- AFXOUTLOOKBAR/CMFCOutlookBar::IsMode2003
- AFXOUTLOOKBAR/CMFCOutlookBar::OnAfterAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnBeforeAnimation
- AFXOUTLOOKBAR/CMFCOutlookBar::OnScroll
- AFXOUTLOOKBAR/CMFCOutlookBar::RemoveCustomPage
- AFXOUTLOOKBAR/CMFCOutlookBar::SetButtonsFont
- AFXOUTLOOKBAR/CMFCOutlookBar::SetMode2003
helpviewer_keywords:
- CMFCOutlookBar [MFC], AllowDestroyEmptyTabbedPane
- CMFCOutlookBar [MFC], CanAcceptPane
- CMFCOutlookBar [MFC], CanSetCaptionTextToTabName
- CMFCOutlookBar [MFC], Create
- CMFCOutlookBar [MFC], CreateCustomPage
- CMFCOutlookBar [MFC], DoesAllowDynInsertBefore
- CMFCOutlookBar [MFC], FloatTab
- CMFCOutlookBar [MFC], GetButtonsFont
- CMFCOutlookBar [MFC], GetTabArea
- CMFCOutlookBar [MFC], IsMode2003
- CMFCOutlookBar [MFC], OnAfterAnimation
- CMFCOutlookBar [MFC], OnBeforeAnimation
- CMFCOutlookBar [MFC], OnScroll
- CMFCOutlookBar [MFC], RemoveCustomPage
- CMFCOutlookBar [MFC], SetButtonsFont
- CMFCOutlookBar [MFC], SetMode2003
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
ms.openlocfilehash: e54e44e702aaf8d6883ada6be9c127f63ecee97d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265041"
---
# <a name="cmfcoutlookbar-class"></a>Klasa CMFCOutlookBar

Okienko z kartami z wyglądem **okienka nawigacji** w programie Microsoft Outlook 2000 lub Outlook 2003. `CMFCOutlookBar`Obiekt zawiera obiekt [klasy CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md) oraz serie kart. Karty mogą być obiektami [klasy CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) lub `CWnd` obiektami pochodnymi. Na użytkownika pasek programu Outlook pojawia się jako seria przycisków i obszar wyświetlania. Gdy użytkownik kliknie przycisk, zostanie wyświetlona odpowiednia kontrolka lub okienko przycisku.

## <a name="syntax"></a>Składnia

```cpp
class CMFCOutlookBar : public CBaseTabbedPane
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCOutlookBar::CMFCOutlookBar`|Konstruktor domyślny.|
|`CMFCOutlookBar::~CMFCOutlookBar`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Określa, czy puste okienko z kartami może zostać zniszczone. (Przesłania [CBaseTabbedPane:: AllowDestroyEmptyTabbedPane](../../mfc/reference/cbasetabbedpane-class.md#allowdestroyemptytabbedpane).)|
|[CMFCOutlookBar::CanAcceptPane](#canacceptpane)|Określa, czy do okienka paska programu Outlook można zadokować inne okienko. (Przesłania CDockablePane:: CanAcceptPane.)|
|[CMFCOutlookBar::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Określa, czy podpis okienka z kartami ma taki sam tekst jak karta aktywna. (Przesłania [CBaseTabbedPane:: CanSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#cansetcaptiontexttotabname))|
|[CMFCOutlookBar:: Create](#create)|Tworzy formant paska Outlook.|
|[CMFCOutlookBar::CreateCustomPage](#createcustompage)|Tworzy niestandardową kartę paska Outlook.|
|`CMFCOutlookBar::CreateObject`|Używane przez platformę do tworzenia wystąpienia dynamicznego tego typu klasy.|
|[CMFCOutlookBar::D oesAllowDynInsertBefore](#doesallowdyninsertbefore)|Określa, czy użytkownik może zadokować pasek sterowania na zewnętrznej krawędzi paska Outlook.|
|[CMFCOutlookBar::FloatTab](#floattab)|Przepływa z okienka, ale tylko wtedy, gdy okienko znajduje się obecnie na karcie odłączalnej. (Zastępuje [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|
|[CMFCOutlookBar::GetButtonsFont](#getbuttonsfont)|Zwraca czcionkę tekstu na przyciskach paska Outlook.|
|[CMFCOutlookBar::GetTabArea](#gettabarea)|Zwraca rozmiar i położenie obszarów kart na pasku Outlook. (Przesłania [CBaseTabbedPane:: GetTabArea](../../mfc/reference/cbasetabbedpane-class.md#gettabarea).)|
|`CMFCOutlookBar::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|
|[CMFCOutlookBar::IsMode2003](#ismode2003)|Określa, czy zachowanie paska Outlook śladuje Microsoft Office Outlook 2003 (Zobacz uwagi).|
|[CMFCOutlookBar::OnAfterAnimation](#onafteranimation)|Wywoływane przez [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) po ustawieniu aktywnej karty przy użyciu animacji.|
|[CMFCOutlookBar::OnBeforeAnimation](#onbeforeanimation)|Wywoływana przez [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) , zanim Strona karty zostanie ustawiona jako aktywna karta przy użyciu animacji.|
|[CMFCOutlookBar:: OnScroll](#onscroll)|Wywoływane przez platformę, jeśli pasek programu Outlook jest przewijany w górę lub w dół.|
|[CMFCOutlookBar::RemoveCustomPage](#removecustompage)|Usuwa niestandardową kartę paska Outlook.|
|[CMFCOutlookBar::SetButtonsFont](#setbuttonsfont)|Ustawia czcionkę tekstu na przyciskach paska Outlook.|
|[CMFCOutlookBar::SetMode2003](#setmode2003)|Określa, czy zachowanie paska Outlook jest widoczne dla programu Outlook 2003 (Zobacz uwagi).|

## <a name="remarks"></a>Uwagi

Aby zapoznać się z przykładem paska programu Outlook, zobacz przykład [OutlookDemo: MFC OutlookDemo Application](../../overview/visual-cpp-samples.md).

## <a name="implementing-the-outlook-bar"></a>Implementowanie paska programu Outlook

Aby użyć `CMFCOutlookBar` kontrolki w aplikacji, wykonaj następujące kroki:

1. Osadź `CMFCOutlookBar` obiekt w głównej klasie okna ramki.

    ```cpp
    class CMainFrame : public CMDIFrameWnd
    {
        // ...
        CMFCOutlookBar m_wndOutlookBar;
        CMFCOutlookBarPane m_wndOutlookPane;
        // ...
    };
    ```

1. Podczas przetwarzania komunikatu WM_CREATE w ramce głównej należy wywołać metodę [CMFCOutlookBar:: Create](#create) , aby utworzyć formant karty paska Outlook.

    ```cpp
    m_wndOutlookBar.Create (_T("Shortcuts"),
        this,
        CRect (0, 0, 100, 100),
        ID_VIEW_OUTLOOKBAR,
        WS_CHILD | WS_VISIBLE | CBRS_LEFT);
    ```

1. Uzyskaj wskaźnik do podstawowego przy `CMFCOutlookBarTabCtrl` użyciu [CBaseTabbedPane:: GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow).

    ```cpp
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();
    ```

1. Utwórz obiekt [klasy CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) dla każdej karty zawierającej przyciski.

    ```cpp
    m_wndOutlookPane.Create(&m_wndOutlookBar,
        AFX_DEFAULT_TOOLBAR_STYLE,
        ID_OUTLOOK_PANE_GENERAL,
        AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);

    // make the Outlook pane detachable (enable docking)
    m_wndOutlookPane.EnableDocking(CBRS_ALIGN_ANY);

    // add buttons
    m_wndOutlookPane.AddButton(theApp.LoadIcon (IDR_MAINFRAME),
        "About",
        ID_APP_ABOUT);

    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON),
        "Open",
        ID_FILE_OPEN);
    ```

1. Wywołanie [CMFCOutlookBarTabCtrl:: AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) w celu dodania każdej nowej karty. Ustaw parametr *bDetachable* na wartość false, aby strona nie mogła zostać odłączona. Lub Użyj [CMFCOutlookBarTabCtrl:: AddControl](../../mfc/reference/cmfcoutlookbartabctrl-class.md#addcontrol) , aby dodać strony, które można odłączyć.

    ```cpp
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);
    ```

1. Aby dodać `CWnd` kontrolkę pochodną (na przykład [Klasa CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)) jako kartę, Utwórz kontrolkę i Wywołaj [CMFCOutlookBarTabCtrl:: AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) , aby dodać ją do paska Outlook.

> [!NOTE]
> Należy używać unikatowych identyfikatorów formantów dla każdego obiektu [klasy CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md) i dla każdego `CWnd` obiektu pochodnego.

Aby dynamicznie dodawać lub usuwać nowe strony w czasie wykonywania, użyj [CMFCOutlookBar:: CreateCustomPage](#createcustompage) i [CMFCOutlookBar:: RemoveCustomPage](#removecustompage).

## <a name="outlook-2003-mode"></a>Tryb programu Outlook 2003

W trybie Outlook 2003 przyciski kart są umieszczane w dolnej części okienka paska programu Outlook. Gdy nie ma wystarczającej ilości miejsca, aby wyświetlić przyciski, są one wyświetlane jako ikony w obszarze podobnym do paska narzędzi wzdłuż dolnej części okienka.

Użyj [CMFCOutlookBar:: SetMode2003](#setmode2003) , aby włączyć tryb Outlook 2003. Użyj [CMFCOutlookBarTabCtrl:: SetToolbarImageList](../../mfc/reference/cmfcoutlookbartabctrl-class.md#settoolbarimagelist) , aby ustawić mapę bitową zawierającą ikony, które są wyświetlane w dolnej części paska Outlook. Ikony w mapie bitowej muszą być uporządkowane według indeksu karty.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxoutlookbar. h

## <a name="cmfcoutlookbarallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a> CMFCOutlookBar::AllowDestroyEmptyTabbedPane

Określa, czy puste okienko z kartami może zostać zniszczone.

```cpp
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli puste okienko z kartami może zostać zniszczone; w przeciwnym razie FALSE. Domyślna implementacja zawsze zwraca wartość TRUE.

### <a name="remarks"></a>Uwagi

Jeśli puste okienko z kartami nie może zostać zniszczone, struktura ukrywa je zamiast tego.

## <a name="cmfcoutlookbarcanacceptpane"></a><a name="canacceptpane"></a> CMFCOutlookBar::CanAcceptPane

Określa, czy do okienka paska programu Outlook można zadokować inne okienko.

```cpp
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parametry

*pBar*<br/>
podczas Wskaźnik do innego okienka, które jest zadokowane w tym okienku.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli można zadokować inne okienko w okienku paska Outlook. w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Jeśli pasek programu Outlook jest w trybie Outlook 2003, dokowanie nie jest obsługiwane, więc zwracana wartość to FALSE.

Jeśli parametr *pBar* ma wartość null, ta metoda zwraca wartość false.

W przeciwnym razie ta metoda zachowuje się jako metoda bazowa [CBasePane:: CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane), z tą różnicą, że nawet jeśli nie jest włączona funkcja Docking, pasek programu Outlook nadal będzie mógł zadokować inny pasek programu Outlook.

## <a name="cmfcoutlookbarcansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a> CMFCOutlookBar::CanSetCaptionTextToTabName

Określa, czy podpis okienka z kartami ma ten sam tekst, który jest wyświetlany na karcie aktywne.

```cpp
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli podpis okna paska Outlook jest automatycznie ustawiany na tekst aktywnej karty; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Użyj [CBaseTabbedPane:: EnableSetCaptionTextToTabName](../../mfc/reference/cbasetabbedpane-class.md#enablesetcaptiontexttotabname) , aby włączyć lub wyłączyć tę funkcję.

W trybie Outlook 2003 to ustawienie jest zawsze włączone.

## <a name="cmfcoutlookbarcreate"></a><a name="create"></a> CMFCOutlookBar:: Create

Tworzy formant paska Outlook.

```cpp
virtual BOOL Create(
    LPCTSTR lpszCaption,
    CWnd* pParentWnd,
    const RECT& rect,
    UINT nID,
    DWORD dwStyle,
    DWORD dwControlBarStyle=AFX_CBRS_RESIZE,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>Parametry

*lpszCaption*<br/>
podczas Określa podpis okna.

*pParentWnd*<br/>
podczas Określa wskaźnik do okna nadrzędnego. Nie może mieć wartości NULL.

*cinania*<br/>
podczas Określa rozmiar i położenie paska programu Outlook w pikselach.

*nID*<br/>
podczas Określa identyfikator kontrolki. Musi różnić się od innych identyfikatorów kontrolek używanych w aplikacji.

*dwStyle*<br/>
podczas Określa żądany styl paska kontroli. Aby uzyskać możliwe wartości, zobacz [Style okna](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*dwControlBarStyle*<br/>
podczas Określa specjalne style zdefiniowane w bibliotece.

*pContext*<br/>
podczas Utwórz kontekst.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli metoda zakończy się pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Obiekt jest konstruowany `CMFCOutlookBar` w dwóch krokach. Najpierw Wywołaj konstruktora, a następnie Wywołaj metodę `Create` , która tworzy formant paska Outlook i dołącza go do `CMFCOutlookBar` obiektu.

Zobacz [CBasePane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) , aby uzyskać listę dostępnych stylów zdefiniowanych w bibliotece, które mają być określone przez *dwControlBarStyle*.

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia `Create` metody `CMFCOutlookBar` klasy. Ten fragment kodu jest częścią [przykładu wiele widoków programu Outlook](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookMultiViews#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbar-class_2.cpp)]

## <a name="cmfcoutlookbarcreatecustompage"></a><a name="createcustompage"></a> CMFCOutlookBar::CreateCustomPage

Tworzy niestandardową kartę paska Outlook.

```cpp
CMFCOutlookBarPane* CreateCustomPage(
    LPCTSTR lpszPageName,
    BOOL bActivatePage=TRUE,
    DWORD dwEnabledDocking=CBRS_ALIGN_ANY,
    BOOL bEnableTextLabels=TRUE);
```

### <a name="parameters"></a>Parametry

*lpszPageName*<br/>
podczas Etykieta strony.

*bActivatePage*<br/>
podczas Jeśli wartość jest równa TRUE, Strona zostanie uaktywniona po utworzeniu.

*dwEnabledDocking*<br/>
podczas Kombinacja CBRS_ALIGN_ flag, która określa włączone zadokowane strony, gdy strona zostanie odłączona.

*bEnableTextLabels*<br/>
podczas W przypadku wartości TRUE etykiety tekstowe są włączane dla przycisków znajdujących się na stronie.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do nowo utworzonej strony lub wartość NULL, jeśli Tworzenie nie powiodło się.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby umożliwić użytkownikom tworzenie niestandardowych stron paska Outlook. Można utworzyć do 100 stron na aplikację. Identyfikatory kontrolek strony rozpoczynają się od 0xF000. Tworzenie kończy się niepowodzeniem, jeśli łączna liczba niestandardowych stron paska programu Outlook przekracza 100.

Użyj [CMFCOutlookBar:: RemoveCustomPage](#removecustompage) , aby usunąć strony niestandardowe.

## <a name="cmfcoutlookbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCOutlookBar::D oesAllowDynInsertBefore

Określa, czy użytkownik może zadokować okienko w zewnętrznej krawędzi paska Outlook.

```
DECLARE_MESSAGE_MAP virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Wartość zwracana

Domyślna implementacja zwraca wartość FALSE.

### <a name="remarks"></a>Uwagi

Struktura wywołuje metodę, `DoesAllowDynInsertBefore` gdy szuka lokalizacji w celu zadokowania okienka dynamicznego. Jeśli funkcja zwraca wartość FALSE, struktura nie zezwala na dokowanie dowolnego dynamicznego okienka na zewnętrznych krawędziach okienka.

Zazwyczaj można utworzyć pasek programu Outlook jako statyczną kontrolkę niezmiennoprzecinkową. Można zastąpić tę funkcję w klasie pochodnej i zwrócić wartość TRUE, aby zmienić to zachowanie.

> [!NOTE]
> Ponieważ okienka dynamiczne sprawdzają stan zadokowanych okienek statycznych podczas dokowania, należy zadokować okienka dynamiczne po każdym przypadku, gdy jest to możliwe.

## <a name="cmfcoutlookbarfloattab"></a><a name="floattab"></a> CMFCOutlookBar::FloatTab

Przepływa z okienka.

```cpp
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide);
```

### <a name="parameters"></a>Parametry

*pBar*<br/>
podczas Wskaźnik do okienka, które ma być zmiennoprzecinkowe.

*nTabID*<br/>
podczas Liczony od zera indeks karty do wartości zmiennoprzecinkowej.

*dockMethod*<br/>
podczas Określa metodę, która ma być używana do przesunięcia okienka.  Aby uzyskać więcej informacji, zobacz [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).

*bHide*<br/>
podczas Wartość TRUE powoduje ukrycie okienka przed liczbą zmiennoprzecinkową; w przeciwnym razie FALSE. W przeciwieństwie do wersji klasy bazowej tej metody, ten parametr nie ma wartości domyślnej.

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli okienko jest przepływane; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda jest taka sama jak [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab) , z tą różnicą, że nie jest włączona Ostatnia pozostała karta w formancie paska Outlook do wartości zmiennoprzecinkowych.

## <a name="cmfcoutlookbargetbuttonsfont"></a><a name="getbuttonsfont"></a> CMFCOutlookBar::GetButtonsFont

Zwraca czcionkę tekstu na kartach przycisków stron na pasku Outlook.

```cpp
CFont* GetButtonsFont() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu Font, który jest używany do wyświetlania tekstu na kartach przycisków stron paska Outlook.

### <a name="remarks"></a>Uwagi

Użyj tej funkcji, aby pobrać czcionkę używaną do wyświetlania tekstu na kartach przycisków stron programu Outlook. Można ustawić czcionkę przez wywołanie metody [CMFCOutlookBar:: SetButtonsFont](#setbuttonsfont).

## <a name="cmfcoutlookbargettabarea"></a><a name="gettabarea"></a> CMFCOutlookBar::GetTabArea

Określa rozmiar i położenie obszarów kart na pasku Outlook.

```cpp
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Parametry

*rectTabAreaTop*<br/>
określoną Zawiera rozmiar i położenie (we współrzędnych klienta) obszaru górnej karty, gdy funkcja zwraca wartość.

*rectTabAreaBottom*<br/>
określoną Zawiera rozmiar i położenie (we współrzędnych klienta) dolnego obszaru karty, gdy funkcja zwraca wartość.

### <a name="remarks"></a>Uwagi

Struktura wywołuje tę metodę, aby określić typ dokowania w okienku Target. Gdy struktura określi, że użytkownik przeciągnie okienko w celu zadokowania w obszarze karty okienka Target, próbuje dodać pierwsze okienko jako nową kartę w okienku Target. W przeciwnym razie próbuje zadokować pierwsze okienko na odpowiedniej stronie okienka Target. Struktura tworzy nowy kontener z suwakiem, aby pomieścić dodatkowe okienko zadokowane.

Domyślna implementacja funkcji `GetTabArea` zwraca cały obszar klienta paska Outlook, jeśli pasek programu Outlook jest statyczny, czyli jeśli pasek programu Outlook nie może być zmiennoprzecinkowy. W przeciwnym razie zwraca obszar, w którym przyciski strony przyjmują u góry i u dołu kontrolki paska Outlook.

Przesłoń tę metodę w klasie pochodnej z `CMFCOutlookBar` , aby zmienić to zachowanie.

## <a name="cmfcoutlookbarismode2003"></a><a name="ismode2003"></a> CMFCOutlookBar::IsMode2003

Określa, czy zachowanie paska Outlook jest śladem Microsoft Office Outlook 2003.

```cpp
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pasek programu Outlook jest uruchomiony w trybie Microsoft Office 2003; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Możesz włączyć ten tryb przy użyciu [CMFCOutlookBar:: SetMode2003](#setmode2003).

## <a name="cmfcoutlookbaronafteranimation"></a><a name="onafteranimation"></a> CMFCOutlookBar::OnAfterAnimation

Wywoływane przez [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) po ustawieniu aktywnej karty przy użyciu animacji.

```cpp
virtual void OnAfterAnimation(int nPage);
```

### <a name="parameters"></a>Parametry

*nPage*<br/>
podczas Indeks (liczony od zera) strony karty, która została uaktywniona.

### <a name="remarks"></a>Uwagi

Wizualny efekt Ustawienia aktywnej karty zależy od tego, czy włączono animację. Aby uzyskać więcej informacji, zobacz [CMFCOutlookBarTabCtrl:: EnableAnimation](../../mfc/reference/cmfcoutlookbartabctrl-class.md#enableanimation).

## <a name="cmfcoutlookbaronbeforeanimation"></a><a name="onbeforeanimation"></a> CMFCOutlookBar::OnBeforeAnimation

Wywoływana przez [CMFCOutlookBarTabCtrl:: SetActiveTab](../../mfc/reference/cmfcoutlookbartabctrl-class.md#setactivetab) , zanim Strona karty zostanie ustawiona jako aktywna karta przy użyciu animacji.

```cpp
virtual BOOL OnBeforeAnimation(int nPage);
```

### <a name="parameters"></a>Parametry

*nPage*<br/>
podczas Indeks (liczony od zera) strony karty, który ma zostać ustawiony jako aktywny.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, jeśli animacja powinna być używana w ustawieniu nowej aktywnej karty, lub FALSE, jeśli animacja powinna być wyłączona.

### <a name="remarks"></a>Uwagi

## <a name="cmfcoutlookbaronscroll"></a><a name="onscroll"></a> CMFCOutlookBar:: OnScroll

Wywoływane przez platformę, jeśli pasek programu Outlook jest przewijany w górę lub w dół.

```cpp
virtual void OnScroll(BOOL bDown);
```

### <a name="parameters"></a>Parametry

*bDown*<br/>
podczas Ma wartość TRUE, jeśli pasek programu Outlook jest przewijany w dół lub FAŁSZ, jeśli jest przewijany.

### <a name="remarks"></a>Uwagi

## <a name="cmfcoutlookbarremovecustompage"></a><a name="removecustompage"></a> CMFCOutlookBar::RemoveCustomPage

Usuwa niestandardową stronę karty paska Outlook.

```cpp
BOOL RemoveCustomPage(
    UINT uiPage,
    CMFCOutlookBarTabCtrl* pTargetWnd);
```

### <a name="parameters"></a>Parametry

*uiPage*<br/>
podczas Indeks strony w oknie nadrzędnym programu Outlook (liczony od zera).

*pTargetWnd*<br/>
podczas Pointerto okno nadrzędne programu Outlook.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli strona niestandardowa została pomyślnie usunięta; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby usunąć strony niestandardowe. Po usunięciu strony jego identyfikator kontrolki jest zwracany do puli dostępnych identyfikatorów.

Musisz podać wskaźnik do obiektu [klasy CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md) , w którym strona ma zostać usunięta. Należy zauważyć, że użytkownik może przenosić odłączalne strony między różnymi paskami programu Outlook, ale informacje o stronie niestandardowej znajdują się w obiekcie paska Outlook, dla którego wywołano [CMFCOutlookBar:: CreateCustomPage](#createcustompage).

Użyj [CBaseTabbedPane:: GetUnderlyingWindow](../../mfc/reference/cbasetabbedpane-class.md#getunderlyingwindow) , aby uzyskać wskaźnik do okna programu Outlook.

## <a name="cmfcoutlookbarsetbuttonsfont"></a><a name="setbuttonsfont"></a> CMFCOutlookBar::SetButtonsFont

Ustawia czcionkę tekstu na przyciskach paska Outlook.

```cpp
void SetButtonsFont(
    CFont* pFont,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametry

*pFont*<br/>
podczas Określa nową czcionkę.

*bRedraw*<br/>
podczas W przypadku wartości TRUE pasek programu Outlook zostanie narysowany ponownie.

### <a name="remarks"></a>Uwagi

Ta metoda służy do ustawiania czcionki dla tekstu wyświetlanego na przyciskach strony karty w programie Outlook.

## <a name="cmfcoutlookbarsetmode2003"></a><a name="setmode2003"></a> CMFCOutlookBar::SetMode2003

Określa, czy zachowanie paska Outlook jest śladem programu Outlook 2003.

```cpp
void SetMode2003(BOOL bMode2003=TRUE);
```

### <a name="parameters"></a>Parametry

*bMode2003*<br/>
podczas W przypadku wartości TRUE włączony jest tryb Office 2003.

### <a name="remarks"></a>Uwagi

Ta funkcja służy do włączania lub wyłączania trybu pakietu Office 2003. W tym trybie pasek Outlook ma dodatkowy pasek narzędzi z przyciskiem dostosowywania. Zachowanie paska Outlook jest zgodne z zachowaniem paska programu Outlook w Microsoft Office 2003.

Domyślnie ten tryb jest wyłączony.

> [!NOTE]
> Ta funkcja musi zostać wywołana przed [CMFCOutlookBar:: Create](#create).

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[Klasa CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)<br/>
[Klasa CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

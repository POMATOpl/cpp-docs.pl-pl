---
description: 'Dowiedz się więcej na temat: Klasa CMFCOutlookBarTabCtrl'
title: Klasa CMFCOutlookBarTabCtrl
ms.date: 10/18/2018
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
helpviewer_keywords:
- CMFCOutlookBarTabCtrl [MFC], AddControl
- CMFCOutlookBarTabCtrl [MFC], CanShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], CanShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], Create
- CMFCOutlookBarTabCtrl [MFC], EnableAnimation
- CMFCOutlookBarTabCtrl [MFC], EnableInPlaceEdit
- CMFCOutlookBarTabCtrl [MFC], EnableScrollButtons
- CMFCOutlookBarTabCtrl [MFC], GetBorderSize
- CMFCOutlookBarTabCtrl [MFC], GetVisiblePageButtons
- CMFCOutlookBarTabCtrl [MFC], IsAnimation
- CMFCOutlookBarTabCtrl [MFC], IsMode2003
- CMFCOutlookBarTabCtrl [MFC], OnShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowOptions
- CMFCOutlookBarTabCtrl [MFC], SetActiveTab
- CMFCOutlookBarTabCtrl [MFC], SetBorderSize
- CMFCOutlookBarTabCtrl [MFC], SetPageButtonTextAlign
- CMFCOutlookBarTabCtrl [MFC], SetToolbarImageList
- CMFCOutlookBarTabCtrl [MFC], SetVisiblePageButtons
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
ms.openlocfilehash: b969fbb592fc3098dc8d287004fab90da6f30111
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333497"
---
# <a name="cmfcoutlookbartabctrl-class"></a>Klasa CMFCOutlookBarTabCtrl

Kontrolka karta, która ma wygląd **okienka nawigacji** w programie Microsoft Outlook.
Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

## <a name="syntax"></a>Składnia

```
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Konstruktor domyślny.|
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCOutlookBarTabCtrl:: AddControl](#addcontrol)|Dodaje kontrolkę Windows w postaci nowej karty na pasku Outlook.|
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Wywoływane przez platformę, aby określić wymiary pola edycji, które pojawia się, gdy użytkownik zmienia nazwę karty. (Zastępuje `CMFCBaseTabCtrl::CalcRectEdit` ).|
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|Wywoływane przez platformę podczas operacji zmiany rozmiarów, aby określić, czy można wyświetlić mniej przycisków strony karty paska Outlook, niż jest to obecnie widoczne.|
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Wywoływane przez platformę podczas operacji zmiany rozmiarów, aby określić, czy można wyświetlić więcej przycisków stron kart paska Outlook, niż jest to obecnie widoczne.|
|[CMFCOutlookBarTabCtrl:: Create](#create)|Tworzy kontrolkę karta pasek Outlook.|
|`CMFCOutlookBarTabCtrl::CreateObject`|Używane przez platformę do tworzenia wystąpienia dynamicznego tego typu klasy.|
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|Określa, czy animacja, która występuje podczas przełączania między aktywnymi kartami jest włączona.|
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Określa, czy użytkownik może modyfikować etykiety tekstowe na przyciskach kart paska Outlook. (Przesłania [CMFCBaseTabCtrl:: EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|Wywoływane przez platformę, aby włączyć przyciski umożliwiające użytkownikowi przewijanie przycisków w okienku paska Outlook.|
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Identyfikuje okienko, które zawiera określony punkt. (Przesłania [CMFCBaseTabCtrl:: FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Zwraca rozmiar obramowania kontrolki karta programu Outlook.|
|`CMFCOutlookBarTabCtrl::GetTabArea`|Pobiera rozmiar i położenie obszaru karty kontrolki karta. (Przesłania [CMFCBaseTabCtrl:: GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|
|`CMFCOutlookBarTabCtrl::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||
|[CMFCOutlookBarTabCtrl:: isanimation](#isanimation)|Określa, czy animacja, która występuje podczas przełączania między kartami aktywnymi jest włączona.|
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Określa, czy formant karty pasek programu Outlook znajduje się w trybie, który emuluje program Microsoft Outlook 2003.|
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Określa, czy punkt znajduje się w obszarze karty. (Przesłania [CMFCBaseTabCtrl:: IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Określa, czy karta jest odłączana. (Przesłania [CMFCBaseTabCtrl:: IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Wywoływane przez platformę, gdy karta jest wstawiona lub usunięta. (Przesłania `CMFCBaseTabCtrl::OnChangeTabs`).|
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Wywoływane przez platformę, aby zmniejszyć liczbę przycisków strony karty, które są widoczne.|
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Wywoływane przez platformę, aby zwiększyć liczbę przycisków strony karty, które są widoczne.|
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|Wyświetla okno dialogowe **Opcje okienka nawigacji** .|
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Ponownie oblicza układ wewnętrzny kontrolki karta. (Przesłania [CMFCBaseTabCtrl:: RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Ustawia aktywną kartę. (Przesłania [CMFCBaseTabCtrl:: SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab))|
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Ustawia rozmiar obramowania kontrolki karta programu Outlook.|
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Ustawia wyrównanie etykiet tekstowych na przyciskach kart na pasku Outlook.|
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Ustawia mapę bitową zawierającą ikony, które są wyświetlane w dolnej części paska programu Outlook w trybie Outlook 2003 (zobacz [Klasa CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)).|
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||

## <a name="remarks"></a>Uwagi

Aby utworzyć pasek programu Outlook z obsługą dokowania, użyj `CMFCOutlookBar` obiektu do hostowania kontrolki karta pasek Outlook. Aby uzyskać więcej informacji, zobacz [Klasa CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób inicjowania `CMFCOutlookBarTabCtrl` obiektu i używania różnych metod w `CMFCOutlookBarTabCtrl` klasie. W przykładzie pokazano, jak włączyć edycję w miejscu etykiety tekst na przyciskach na stronie karty na pasku Outlook, włączyć animację, włączyć uchwyty przewijania, które umożliwiają użytkownikowi przewijanie przycisków w okienku Pasek programu Outlook, Ustawianie rozmiaru obramowania kontrolki karta programu Outlook i Ustawianie wyrównania etykiet tekstowych na przyciskach kart na pasku Outlook. Ten fragment kodu jest częścią [przykładu demonstracyjnego dla programu Outlook](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)

[CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxoutlookbartabctrl. h

## <a name="cmfcoutlookbartabctrladdcontrol"></a><a name="addcontrol"></a> CMFCOutlookBarTabCtrl:: AddControl

Dodaje kontrolkę Windows w postaci nowej karty na pasku Outlook.

```cpp
void AddControl(
    CWnd* pWndCtrl,
    LPCTSTR lpszName,
    int nImageID=-1,
    BOOL bDetachable=TRUE,
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```

### <a name="parameters"></a>Parametry

*pWndCtrl*<br/>
podczas Wskaźnik do kontrolki do dodania.

*lpszName*<br/>
podczas Określa nazwę karty.

*bDetachable*<br/>
podczas W przypadku wartości TRUE strona zostanie utworzona jako odłączona.

*nImageID*<br/>
podczas Indeks obrazu na liście obrazów wewnętrznych dla obrazu, który ma być wyświetlany na nowej karcie.

*dwControlBarStyle*<br/>
podczas Określa AFX_ CBRS_ * stylu dla opakowanych okienek dokowania.

### <a name="remarks"></a>Uwagi

Ta funkcja służy do dodawania kontrolki jako nowej strony paska Outlook.

Ta funkcja wewnętrznie wywołuje metodę [CMFCBaseTabCtrl:: AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).

Jeśli ustawisz *bDetachable* na true, `AddControl` wewnętrznie tworzy `CDockablePaneAdapter` obiekt i otacza dodany formant. Automatycznie ustawia klasę środowiska uruchomieniowego okna z kartami na klasę środowiska uruchomieniowego `CMFCOutlookBar` i klasę środowiska uruchomieniowego ramki zmiennoprzecinkowej na `CMultiPaneFrameWnd` .

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia `AddControl` metody w `CMFCOutlookBarTabCtrl` klasie. Ten fragment kodu jest częścią [przykładu demonstracyjnego dla programu Outlook](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]

## <a name="cmfcoutlookbartabctrlcanshowfewerpagebuttons"></a><a name="canshowfewerpagebuttons"></a> CMFCOutlookBarTabCtrl::CanShowFewerPageButtons

Wywoływane przez platformę podczas operacji zmiany rozmiarów, aby określić, czy można wyświetlić mniej przycisków stron kart paska Outlook, niż jest to obecnie widoczne.

```
virtual BOOL CanShowFewerPageButtons() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli istnieje więcej niż jeden przycisk; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Kontrolka karta pasek Outlook dynamicznie dodaje lub usuwa karty z ekranu w zależności od ilości dostępnego miejsca. Ta metoda jest używana przez platformę, aby pomóc w tym procesie.

## <a name="cmfcoutlookbartabctrlcanshowmorepagebuttons"></a><a name="canshowmorepagebuttons"></a> CMFCOutlookBarTabCtrl::CanShowMorePageButtons

Wywoływane przez platformę podczas operacji zmiany rozmiarów, aby określić, czy można wyświetlić więcej przycisków stron kart paska Outlook, niż jest to obecnie widoczne.

```
virtual BOOL CanShowMorePageButtons() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli istnieją przyciski, które nie są obecnie widoczne; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Kontrolka karta pasek Outlook dynamicznie dodaje lub usuwa karty z ekranu, w zależności od tego, ile miejsca jest dostępne. Ta metoda jest używana przez platformę, aby pomóc w tym procesie.

## <a name="cmfcoutlookbartabctrlcreate"></a><a name="create"></a> CMFCOutlookBarTabCtrl:: Create

Tworzy kontrolkę karta pasek Outlook.

```
virtual BOOL Create(
    const CRect& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametry

*cinania*<br/>
podczas Określa początkowy rozmiar i położenie (w pikselach).

*pParentWnd*<br/>
podczas Wskazuje okno nadrzędne. Nie może mieć wartości NULL.

*nID*<br/>
podczas Identyfikator formantu.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli formant został utworzony pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Zazwyczaj kontrolki karty pasek programu Outlook są tworzone, gdy [Klasa CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md) kontroluje komunikat WM_CREATE procesu.

## <a name="cmfcoutlookbartabctrlenableanimation"></a><a name="enableanimation"></a> CMFCOutlookBarTabCtrl::EnableAnimation

Określa, czy animacja, która występuje podczas przełączania między aktywnymi kartami jest włączona.

```
static void EnableAnimation(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*bEnable*<br/>
podczas Określa, czy animacja powinna być włączona, czy wyłączona.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby włączyć i wyłączyć animację. Gdy użytkownik otworzy stronę karty, tytuły stron w górę lub w dół, jeśli animacja jest włączona. Jeśli animacja jest wyłączona, Strona zostanie natychmiast uaktywniona.

Domyślnie animacja jest włączona.

## <a name="cmfcoutlookbartabctrlenableinplaceedit"></a><a name="enableinplaceedit"></a> CMFCOutlookBarTabCtrl::EnableInPlaceEdit

Określa, czy użytkownik może modyfikować etykiety tekstowe na przyciskach strony karty na pasku Outlook.

```
virtual void EnableInPlaceEdit(BOOL bEnable);
```

### <a name="parameters"></a>Parametry

*bEnable*<br/>
W przypadku opcji TRUE Włącz edytowanie etykiety tekstowej w miejscu. W przypadku wartości FALSE Wyłącz edytowanie w miejscu.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby włączyć lub wyłączyć Edytowanie etykiet tekstowych na przyciskach na kartach. Domyślnie edytowanie w miejscu jest wyłączone.

## <a name="cmfcoutlookbartabctrlenablescrollbuttons"></a><a name="enablescrollbuttons"></a> CMFCOutlookBarTabCtrl::EnableScrollButtons

Wywoływane przez platformę, aby włączyć uchwyty przewijania umożliwiające użytkownikowi przewijanie przycisków w okienku paska Outlook.

```cpp
void EnableScrollButtons(
    BOOL bEnable = TRUE,
    BOOL bIsUp = TRUE,
    BOOL bIsDown = TRUE);
```

### <a name="parameters"></a>Parametry

*bEnable*<br/>
podczas Określa, czy przyciski przewijania są wyświetlane.

*bIsUp*<br/>
podczas Określa, czy górny pasek przewijania jest wyświetlany.

*bIsDown*<br/>
podczas Określa, czy dolny pasek przewijania jest wyświetlany.

### <a name="remarks"></a>Uwagi

Włącza wyświetlanie przycisków przewijania. Ta metoda jest wywoływana przez platformę, gdy aktywna karta zmienia się, aby przywrócić przyciski przewijania.

## <a name="cmfcoutlookbartabctrlgetbordersize"></a><a name="getbordersize"></a> CMFCOutlookBarTabCtrl::GetBorderSize

Zwraca rozmiar obramowania kontrolki karta programu Outlook.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Rozmiar obramowania (w pikselach).

## <a name="cmfcoutlookbartabctrlgetvisiblepagebuttons"></a><a name="getvisiblepagebuttons"></a> CMFCOutlookBarTabCtrl::GetVisiblePageButtons

```
int GetVisiblePageButtons() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcoutlookbartabctrlisanimation"></a><a name="isanimation"></a> CMFCOutlookBarTabCtrl:: isanimation

Określa, czy animacja, która występuje podczas przełączania między aktywnymi kartami jest włączona.

```
static BOOL IsAnimation();
```

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli animacja jest włączona; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Wywołaj funkcję [CMFCOutlookBarTabCtrl:: EnableAnimation](#enableanimation) , aby włączyć lub wyłączyć animację.

## <a name="cmfcoutlookbartabctrlismode2003"></a><a name="ismode2003"></a> CMFCOutlookBarTabCtrl::IsMode2003

Określa, czy formant karty pasek programu Outlook znajduje się w trybie, który emuluje program Microsoft Outlook 2003.

```
BOOL IsMode2003() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, Jeśli kontrolka karta pasek Outlook jest w trybie Outlook 2003; w przeciwnym razie FALSE;

### <a name="remarks"></a>Uwagi

Ta wartość jest ustawiana przez [CMFCOutlookBar:: SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).

## <a name="cmfcoutlookbartabctrlonshowfewerpagebuttons"></a><a name="onshowfewerpagebuttons"></a> CMFCOutlookBarTabCtrl::OnShowFewerPageButtons

Wywoływane przez platformę, aby zmniejszyć liczbę przycisków strony karty, które są widoczne.

```
virtual void OnShowFewerPageButtons();
```

### <a name="remarks"></a>Uwagi

Ta metoda dostosowuje liczbę przycisków widocznej karty strony, gdy zmieniany jest rozmiar kontrolki.

## <a name="cmfcoutlookbartabctrlonshowmorepagebuttons"></a><a name="onshowmorepagebuttons"></a> CMFCOutlookBarTabCtrl::OnShowMorePageButtons

Wywoływane przez platformę, aby zwiększyć liczbę przycisków strony karty, które są widoczne.

```
virtual void OnShowMorePageButtons();
```

### <a name="remarks"></a>Uwagi

Ta metoda dostosowuje liczbę przycisków strony karty, które są widoczne, gdy zmieniany jest rozmiar kontrolki.

## <a name="cmfcoutlookbartabctrlonshowoptions"></a><a name="onshowoptions"></a> CMFCOutlookBarTabCtrl::OnShowOptions

Wyświetla okno dialogowe **Opcje okienka nawigacji** .

```
virtual void OnShowOptions();
```

### <a name="remarks"></a>Uwagi

Okno dialogowe **Opcje okienka nawigacji** umożliwia użytkownikowi wybranie przycisków kart strony, które mają być wyświetlane, oraz kolejności ich wyświetlania.

Ta metoda jest wywoływana przez platformę, gdy użytkownik wybierze element menu **Opcje okienka nawigacji** z menu dostosowywania kontrolki.

## <a name="cmfcoutlookbartabctrlsetactivetab"></a><a name="setactivetab"></a> CMFCOutlookBarTabCtrl::SetActiveTab

Ustawia aktywną kartę. Aktywna karta jest otwarty, a jego zawartość jest widoczna.

```
virtual BOOL SetActiveTab(int iTab);
```

### <a name="parameters"></a>Parametry

*iTab*<br/>
podczas Indeks (liczony od zera) karty, który ma zostać otwarty.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli określona karta została pomyślnie otwarta; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Wizualny efekt Ustawienia aktywnej karty zależy od tego, czy włączono animację. Aby uzyskać więcej informacji, zobacz [CMFCOutlookBarTabCtrl:: EnableAnimation](#enableanimation).

## <a name="cmfcoutlookbartabctrlsetbordersize"></a><a name="setbordersize"></a> CMFCOutlookBarTabCtrl::SetBorderSize

Ustawia rozmiar obramowania kontrolki karta programu Outlook.

```cpp
void SetBorderSize(int nBorderSize);
```

### <a name="parameters"></a>Parametry

*nBorderSize*<br/>
podczas Określa nowy rozmiar obramowania (w pikselach).

### <a name="remarks"></a>Uwagi

Ustawia nowy rozmiar obramowania i ponownie oblicza układ okna programu Outlook.

## <a name="cmfcoutlookbartabctrlsetpagebuttontextalign"></a><a name="setpagebuttontextalign"></a> CMFCOutlookBarTabCtrl::SetPageButtonTextAlign

Ustawia wyrównanie etykiet tekstowych na przyciskach kart na pasku Outlook.

```cpp
void SetPageButtonTextAlign(
    UINT uiAlign,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametry

*uiAlign*<br/>
podczas Określa wyrównanie tekstu.

*bRedraw*<br/>
podczas W przypadku wartości TRUE okno programu Outlook zostanie ponownie narysowane.

### <a name="remarks"></a>Uwagi

Ta funkcja służy do zmiany wyrównania tekstu dla przycisków strony.

*uiAlign* może być jedną z następujących wartości:

|Stała|Znaczenie|
|--------------|-------------|
|TA_LEFT|Wyrównanie do lewej|
|TA_CENTER|Wyrównanie do środka|
|TA_RIGHT|Wyrównanie do prawej|

Wartość domyślna to TA_CENTER.

## <a name="cmfcoutlookbartabctrlsettoolbarimagelist"></a><a name="settoolbarimagelist"></a> CMFCOutlookBarTabCtrl::SetToolbarImageList

Ustawia mapę bitową zawierającą ikony, które są wyświetlane w dolnej części paska programu Outlook w trybie Outlook 2003.

```
BOOL SetToolbarImageList(
    UINT uiID,
    int cx,
    COLORREF clrTransp=RGB(255, 0, 255));
```

### <a name="parameters"></a>Parametry

*uiID*<br/>
podczas Określa identyfikator zasobu do załadowania.

*CX*<br/>
podczas Określa szerokość obrazu na liście obrazów (w pikselach).

*clrTransp*<br/>
podczas Wartość RGB, która określa kolor przezroczysty.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość PRAWDA, jeśli powodzenie; w przeciwnym razie zwraca wartość FALSE.

### <a name="remarks"></a>Uwagi

Użyj tej funkcji, aby dołączyć listę obrazów, której obrazy będą wyświetlane na przyciskach paska narzędzi w trybie Microsoft Office 2003. Indeksy obrazu powinny odpowiadać indeksom strony.

Nie należy wywoływać tej metody, jeśli nie jest w trybie Microsoft Office 2003. Aby uzyskać więcej informacji, zobacz [Klasa CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).

## <a name="cmfcoutlookbartabctrlsetvisiblepagebuttons"></a><a name="setvisiblepagebuttons"></a> CMFCOutlookBarTabCtrl::SetVisiblePageButtons

```cpp
void SetVisiblePageButtons(int nVisiblePageButtons);
```

### <a name="parameters"></a>Parametry

podczas *nVisiblePageButtons*<br/>

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)<br/>
[Klasa CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[Klasa CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

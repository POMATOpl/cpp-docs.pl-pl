---
description: 'Dowiedz się więcej na temat: Klasa CMFCColorMenuButton'
title: Klasa CMFCColorMenuButton
ms.date: 11/04/2016
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
ms.openlocfilehash: 4ba0934e872adc4e4b33c2ae5700ecb0fc46e6d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327672"
---
# <a name="cmfccolormenubutton-class"></a>Klasa CMFCColorMenuButton

`CMFCColorMenuButton`Klasa obsługuje polecenie menu lub przycisk paska narzędzi, który uruchamia okno dialogowe selektora kolorów.

## <a name="syntax"></a>Składnia

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Konstruuje `CMFCColorMenuButton` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Włącza i wyłącza przycisk "automatyczny" umieszczony powyżej przycisków zwykłych kolorów. (Standardowy przycisk systemowy jest **automatycznie** oznaczony etykietą).|
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Umożliwia wyświetlanie kolorów specyficznych dla dokumentu zamiast kolorów systemu.|
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Włącza i wyłącza przycisk "inne", który jest umieszczony poniżej zwykłych przycisków kolorów. (Standardowy przycisk "inny" ma etykietę **więcej kolorów**).|
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Umożliwia odrywanie okienka koloru.|
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Pobiera bieżący automatyczny kolor.|
|[CMFCColorMenuButton:: GetColor](#getcolor)|Pobiera kolor bieżącego przycisku.|
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Pobiera kolor odnoszący się do określonego identyfikatora polecenia.|
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Wywoływane przez platformę, gdy zmieni się okno nadrzędne.|
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Otwiera okno dialogowe wyboru koloru.|
|[CMFCColorMenuButton:: SetColor](#setcolor)|Ustawia kolor bieżącego przycisku koloru.|
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Ustawia kolor określonego przycisku menu koloru.|
|[CMFCColorMenuButton:: SetColorName](#setcolorname)|Ustawia nową nazwę dla podanego koloru.|
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Ustawia liczbę kolumn wyświetlanych przez `CMFCColorBar` obiekt.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Kopiuje kolejny przycisk paska narzędzi do bieżącego przycisku.|
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Tworzy okno dialogowe selektora kolorów.|
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Wskazuje, czy są obsługiwane puste menu.|
|[CMFCColorMenuButton:: OnDraw](#ondraw)|Wywoływane przez platformę, aby wyświetlić obraz na przycisku.|
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Wywoływane przez platformę, zanim `CMFCColorMenuButton` obiekt zostanie wyświetlony na liście okna dialogowego dostosowywania paska narzędzi.|

## <a name="remarks"></a>Uwagi

Aby zastąpić oryginalne polecenie menu lub przycisk paska narzędzi `CMFCColorMenuButton` obiektem, Utwórz `CMFCColorMenuButton` obiekt, ustaw odpowiednie style [klasy CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) , a następnie Wywołaj `ReplaceButton` metodę klasy [klasy CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md) . Jeśli dostosowujesz pasek narzędzi, wywołaj metodę [CMFCToolBarsCustomizeDialog:: ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) .

Okno dialogowe selektora kolorów jest tworzone podczas przetwarzania procedury obsługi zdarzeń [CMFCColorMenuButton:: CreatePopupMenu](#createpopupmenu) . Program obsługi zdarzeń powiadamia ramkę nadrzędną z komunikatem WM_COMMAND. `CMFCColorMenuButton`Obiekt wysyła identyfikator formantu, który jest przypisany do oryginalnego polecenia menu lub przycisk paska narzędzi.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano, jak utworzyć i skonfigurować przycisk menu koloru przy użyciu różnych metod w `CMFCColorMenuButton` klasie. W tym przykładzie `CPalette` obiekt jest najpierw tworzony, a następnie używany do konstruowania obiektu `CMFCColorMenuButton` klasy. `CMFCColorMenuButton`Obiekt jest następnie konfigurowany przez włączenie jego automatycznych i innych przycisków oraz ustawienie jego koloru i liczby kolumn. Ten kod jest częścią [przykładu Notatnika programu Word](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcolormenubutton. h

## <a name="cmfccolormenubuttoncmfccolormenubutton"></a><a name="cmfccolormenubutton"></a> CMFCColorMenuButton::CMFCColorMenuButton

Konstruuje `CMFCColorMenuButton` obiekt.

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>Parametry

*uiCmdID*<br/>
podczas Identyfikator polecenia przycisku.

*lpszText*<br/>
podczas Tekst przycisku.

*pPalette*<br/>
podczas Wskaźnik do palety kolorów przycisku.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Pierwszy Konstruktor jest konstruktorem domyślnym. Bieżący kolor i automatyczny kolor obiektu są inicjowane do czerni (RGB (0, 0, 0)).

Drugi Konstruktor inicjuje przycisk do koloru, który odnosi się do określonego identyfikatora polecenia.

## <a name="cmfccolormenubuttoncopyfrom"></a><a name="copyfrom"></a> CMFCColorMenuButton::CopyFrom

Kopiuje jeden obiekt pochodny [klasy CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)do innego.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametry

*src*<br/>
podczas Przycisk źródła do skopiowania.

### <a name="remarks"></a>Uwagi

Zastąp tę metodę, aby skopiować obiekty pochodzące z `CMFCColorMenuButton` obiektu.

## <a name="cmfccolormenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a> CMFCColorMenuButton::CreatePopupMenu

Tworzy okno dialogowe selektora kolorów.

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Wartość zwracana

Obiekt, który reprezentuje okno dialogowe selektora kolorów.

### <a name="remarks"></a>Uwagi

Ta metoda jest wywoływana przez platformę, gdy użytkownik naciśnie przycisk menu koloru.

## <a name="cmfccolormenubuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCColorMenuButton::EnableAutomaticButton

Włącza i wyłącza przycisk "automatyczny" umieszczony powyżej przycisków zwykłych kolorów. (Standardowy przycisk systemowy jest **automatycznie** oznaczony etykietą).

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
podczas Określa tekst przycisku, który jest wyświetlany, gdy przycisk zostanie automatycznie ustawiony.

*colorAutomatic*<br/>
podczas Określa nowy automatyczny kolor.

*bEnable*<br/>
podczas Określa, czy przycisk jest automatyczny, czy nie.

### <a name="remarks"></a>Uwagi

Przycisk Automatyczne stosuje bieżący kolor domyślny.

## <a name="cmfccolormenubuttonenabledocumentcolors"></a><a name="enabledocumentcolors"></a> CMFCColorMenuButton::EnableDocumentColors

Umożliwia wyświetlanie kolorów specyficznych dla dokumentu zamiast kolorów systemu.

```cpp
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
podczas Określa tekst przycisku.

*bEnable*<br/>
podczas TRUE, aby wyświetlić kolory specyficzne dla dokumentu lub FAŁSZ, aby wyświetlić kolory systemowe.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby wyświetlić bieżące kolory dokumentu lub kolory palety systemu, gdy użytkownik kliknie przycisk menu koloru.

## <a name="cmfccolormenubuttonenableotherbutton"></a><a name="enableotherbutton"></a> CMFCColorMenuButton::EnableOtherButton

Włącza i wyłącza przycisk "inne", który jest umieszczony poniżej zwykłych przycisków kolorów. (Standardowy przycisk "inny" ma etykietę **więcej kolorów**).

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
podczas Określa tekst przycisku.

*bAltColorDlg*<br/>
podczas Określ wartość TRUE, aby wyświetlić okno `CMFCColorDialog` dialogowe, lub wartość FAŁSZ, aby wyświetlić okno dialogowe standardowy kolor systemu.

*bEnable*<br/>
podczas Określ wartość TRUE, aby wyświetlić przycisk "inne"; w przeciwnym razie FALSE. Wartość domyślna to TRUE.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolormenubuttonenabletearoff"></a><a name="enabletearoff"></a> CMFCColorMenuButton::EnableTearOff

Umożliwia odrywanie okienka koloru.

```cpp
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>Parametry

*uiID*<br/>
podczas Określa identyfikator okienka odrywania.

*nVertDockColumns*<br/>
podczas Określa liczbę kolumn w okienku kolor zadokowane w pionie w stanie odrywania.

*nHorzDockRows*<br/>
podczas Określa liczbę wierszy w okienku kolor przewidzianym w poziomie w trybie odrywania.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby włączyć funkcję "odrywanie" dla okienka kolorów, które pojawia się po `CMFCColorMenuButton` naciśnięciu przycisku.

## <a name="cmfccolormenubuttongetautomaticcolor"></a><a name="getautomaticcolor"></a> CMFCColorMenuButton::GetAutomaticColor

Pobiera bieżący automatyczny kolor.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość koloru RGB, która reprezentuje bieżący automatyczny kolor.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby uzyskać automatyczny kolor ustawiany przez [CMFCColorMenuButton:: EnableAutomaticButton](#enableautomaticbutton).

## <a name="cmfccolormenubuttongetcolor"></a><a name="getcolor"></a> CMFCColorMenuButton:: GetColor

Pobiera kolor bieżącego przycisku.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Kolor przycisku.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolormenubuttongetcolorbycmdid"></a><a name="getcolorbycmdid"></a> CMFCColorMenuButton::GetColorByCmdID

Pobiera kolor odnoszący się do określonego identyfikatora polecenia.

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>Parametry

*uiCmdID*<br/>
podczas Identyfikator polecenia.

### <a name="return-value"></a>Wartość zwracana

Kolor, który odnosi się do określonego identyfikatora polecenia.

### <a name="remarks"></a>Uwagi

Użyj tej metody, jeśli masz kilka przycisków kolorów w aplikacji. Gdy użytkownik kliknie przycisk koloru, przycisk wyśle identyfikator polecenia w wiadomości WM_COMMAND do jego elementu nadrzędnego. `GetColorByCmdID`Metoda używa identyfikatora polecenia, aby pobrać odpowiedni kolor.

## <a name="cmfccolormenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a> CMFCColorMenuButton::IsEmptyMenuAllowed

Wskazuje, czy są obsługiwane puste menu.

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli są dozwolone puste menu; w przeciwnym razie zero.

### <a name="remarks"></a>Uwagi

Domyślnie są obsługiwane puste menu. Zastąp tę metodę, aby zmienić to zachowanie w klasie pochodnej.

## <a name="cmfccolormenubuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a> CMFCColorMenuButton::OnChangeParentWnd

Wywoływane przez platformę, gdy zmieni się okno nadrzędne.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametry

*pWndParent*<br/>
podczas Wskaźnik do nowego okna nadrzędnego.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolormenubuttonondraw"></a><a name="ondraw"></a> CMFCColorMenuButton:: OnDraw

Wywoływane przez platformę, aby wyświetlić obraz na przycisku.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz=TRUE,
    BOOL bCustomizeMode=FALSE,
    BOOL bHighlight=FALSE,
    BOOL bDrawBorder=TRUE,
    BOOL bGrayDisabledButtons=TRUE);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

*cinania*<br/>
podczas Prostokąt, który jest powiązany z obszarem do narysowania.

*pImages*<br/>
podczas Wskazuje listę obrazów pasków narzędzi.

*bHorz*<br/>
podczas Wartość TRUE, aby określić, że pasek narzędzi znajduje się w stanie zadokowanym w poziomie. w przeciwnym razie FALSE. Wartość domyślna to TRUE.

*bCustomizeMode*<br/>
podczas Wartość TRUE, aby określić, że aplikacja jest w trybie dostosowywania; w przeciwnym razie FALSE. Wartość domyślna to FALSE.

*bHighlight*<br/>
podczas PRAWDA, aby określić, że przycisk jest wyróżniony; w przeciwnym razie FALSE. Wartość domyślna to FALSE.

*bDrawBorder*<br/>
podczas PRAWDA, aby określić, że zostanie wyświetlone obramowanie przycisku; w przeciwnym razie FALSE. Wartość domyślna to TRUE.

*bGrayDisabledButtons*<br/>
podczas PRAWDA, aby określić, że wyłączone przyciski są wyszarzone (wygaszone); w przeciwnym razie FALSE. Wartość domyślna to TRUE.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolormenubuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a> CMFCColorMenuButton::OnDrawOnCustomizeList

Wywoływane przez platformę, zanim `CMFCColorMenuButton` obiekt zostanie wyświetlony na liście okna dialogowego dostosowywania paska narzędzi.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

*cinania*<br/>
podczas Prostokąt, który jest powiązany z przyciskiem do narysowania.

*bSelected*<br/>
podczas TRUE określa, że przycisk jest w wybranym stanie; w przeciwnym razie FALSE.

### <a name="return-value"></a>Wartość zwracana

Szerokość przycisku.

### <a name="remarks"></a>Uwagi

Ta metoda jest wywoływana przez platformę, gdy `CMFCColorMenuButton` obiekt jest wyświetlany w polu listy podczas procesu dostosowywania paska narzędzi.

## <a name="cmfccolormenubuttonopencolordialog"></a><a name="opencolordialog"></a> CMFCColorMenuButton::OpenColorDialog

Otwiera okno dialogowe wyboru koloru.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Parametry

*colorDefault*<br/>
podczas Domyślny kolor wybrany w oknie dialogowym koloru.

*colorRes*<br/>
określoną Zwraca kolor wybrany przez użytkownika z okna dialogowego kolor.

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli użytkownik wybierze nowy kolor; w przeciwnym razie zero.

### <a name="remarks"></a>Uwagi

Po kliknięciu przycisku menu Wywołaj tę metodę, aby otworzyć okno dialogowe koloru. Jeśli wartość zwracana jest różna od zera, kolor wybierany przez użytkownika jest przechowywany w parametrze *colorRes* . Użyj metody [CMFCColorMenuButton:: EnableOtherButton](#enableotherbutton) , aby przełączać się między oknem dialogowym standardowego koloru a oknem dialogowym [CMFCColorDialog Class (Klasa](../../mfc/reference/cmfccolordialog-class.md) ).

## <a name="cmfccolormenubuttonsetcolor"></a><a name="setcolor"></a> CMFCColorMenuButton:: SetColor

Ustawia kolor bieżącego przycisku koloru.

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>Parametry

*CLR*<br/>
podczas Wartość koloru RGB.

*bNotify*<br/>
podczas TRUE, aby zastosować kolor parametru *CLR* do dowolnego skojarzonego przycisku menu lub przycisku paska narzędzi; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby zmienić kolor przycisku bieżącego koloru. Jeśli parametr *bNotify* ma wartość różną od zera, kolor odpowiadającego przycisku na dowolnym skojarzonym menu podręcznym lub pasku narzędzi zostanie zmieniony na kolor określony przez parametr *CLR* .

## <a name="cmfccolormenubuttonsetcolorbycmdid"></a><a name="setcolorbycmdid"></a> CMFCColorMenuButton::SetColorByCmdID

Ustawia kolor określonego przycisku menu koloru.

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>Parametry

*uiCmdID*<br/>
podczas Identyfikator zasobu przycisku menu koloru.

*Kolor*<br/>
podczas Wartość koloru RGB.

## <a name="cmfccolormenubuttonsetcolorname"></a><a name="setcolorname"></a> CMFCColorMenuButton:: SetColorName

Ustawia nową nazwę dla podanego koloru.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
podczas Wartość RGB koloru, którego nazwa zmienia się.

*strName*<br/>
podczas Nowa nazwa koloru.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolormenubuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a> CMFCColorMenuButton::SetColumnsNumber

Ustawia liczbę kolumn do wyświetlenia w kontrolce wyboru koloru (obiekt [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) ).

```cpp
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Parametry

*nColumns*<br/>
podczas Liczba kolumn do wyświetlenia.

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)<br/>
[Klasa CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Klasa CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[Klasa CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)

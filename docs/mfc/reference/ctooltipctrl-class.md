---
description: 'Dowiedz się więcej na temat: Klasa CToolTipCtrl'
title: Klasa CToolTipCtrl
ms.date: 11/04/2016
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
ms.openlocfilehash: bd263d0ada7ad85169eb551dd136f81b480534e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345033"
---
# <a name="ctooltipctrl-class"></a>Klasa CToolTipCtrl

Hermetyzuje funkcjonalność "kontrolki etykietki narzędzia", czyli małego podręcznego okna, które wyświetla pojedynczy wiersz tekstu opisujący przeznaczenie narzędzia w aplikacji.

## <a name="syntax"></a>Składnia

```
class CToolTipCtrl : public CWnd
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CToolTipCtrl:: CToolTipCtrl](#ctooltipctrl)|Konstruuje `CToolTipCtrl` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CToolTipCtrl:: Activate](#activate)|Aktywuje i dezaktywuje formant etykietki narzędzia.|
|[CToolTipCtrl:: Add— narzędzie](#addtool)|Rejestruje narzędzie z kontrolką etykietki narzędzia.|
|[CToolTipCtrl:: AdjustRect](#adjustrect)|Konwertuje między prostokątem wyświetlania tekstu kontrolki etykietki narzędzia a jego prostokątem okna.|
|[CToolTipCtrl:: Create](#create)|Tworzy formant etykietki narzędzia i dołącza go do `CToolTipCtrl` obiektu.|
|[CToolTipCtrl:: CreateEx](#createex)|Tworzy formant etykietki narzędzia z określonymi stylami rozszerzonymi systemu Windows i dołącza go do `CToolTipCtrl` obiektu.|
|[CToolTipCtrl::D elTool](#deltool)|Usuwa narzędzie z kontrolki etykietki narzędzia.|
|[CToolTipCtrl:: GetBubbleSize](#getbubblesize)|Pobiera rozmiar etykietki narzędzia.|
|[CToolTipCtrl:: GetCurrentTool](#getcurrenttool)|Pobiera informacje, takie jak rozmiar, położenie i tekst, okna etykietki narzędzia wyświetlanego przez bieżącą kontrolkę ToolTip.|
|[CToolTipCtrl:: GetDelayTime](#getdelaytime)|Pobiera początkowe, wyskakujące okienka i ponownie pokazuj czasy trwania, które są obecnie ustawione dla kontrolki etykietki narzędzia.|
|[CToolTipCtrl:: GetMargin](#getmargin)|Pobiera górny, lewy, dolny i prawy margines ustawiony dla okna etykietki narzędzia.|
|[CToolTipCtrl:: GetMaxTipWidth](#getmaxtipwidth)|Pobiera maksymalną szerokość okna etykietki narzędzia.|
|[CToolTipCtrl:: gettext](#gettext)|Pobiera tekst, który jest utrzymywany przez kontrolkę etykietki narzędzia dla narzędzia.|
|[CToolTipCtrl:: GetTipBkColor](#gettipbkcolor)|Pobiera kolor tła w oknie etykietki narzędzia.|
|[CToolTipCtrl:: GetTipTextColor](#gettiptextcolor)|Pobiera kolor tekstu w oknie etykietki narzędzia.|
|[CToolTipCtrl:: getTitle](#gettitle)|Pobiera tytuł bieżącej kontrolki ToolTip.|
|[CToolTipCtrl:: GetToolCount](#gettoolcount)|Pobiera liczbę narzędzi obsługiwanych przez kontrolkę etykietki narzędzia.|
|[CToolTipCtrl:: GetToolInfo](#gettoolinfo)|Pobiera informacje o narzędziu utrzymywane przez kontrolkę etykietki narzędzia.|
|[CToolTipCtrl:: HitTest](#hittest)|Testuje punkt, aby określić, czy znajduje się on w obrębie obwiedni danego narzędzia. Jeśli tak, program pobiera informacje o narzędziu.|
|[CToolTipCtrl::P op](#pop)|Usuwa wyświetlone okno etykietki narzędzi z widoku.|
|[CToolTipCtrl::P opup](#popup)|Powoduje, że bieżąca kontrolka ToolTip jest wyświetlana na współrzędnej ostatniej wiadomości myszy.|
|[CToolTipCtrl:: RelayEvent](#relayevent)|Przekazuje komunikat myszy do kontrolki etykietki narzędzia do przetworzenia.|
|[CToolTipCtrl:: SetDelayTime](#setdelaytime)|Ustawia początkowy, podręczny i ponownie Pokazuj czas trwania kontrolki etykietki narzędzia.|
|[CToolTipCtrl:: SetMargin](#setmargin)|Ustawia górny, lewy, dolny i prawy margines dla okna etykietki narzędzia.|
|[CToolTipCtrl:: SetMaxTipWidth](#setmaxtipwidth)|Ustawia maksymalną szerokość okna etykietki narzędzia.|
|[CToolTipCtrl:: SetTipBkColor](#settipbkcolor)|Ustawia kolor tła w oknie etykietki narzędzia.|
|[CToolTipCtrl:: SetTipTextColor](#settiptextcolor)|Ustawia kolor tekstu w oknie etykietki narzędzia.|
|[CToolTipCtrl:: settitle](#settitle)|Dodaje standardową ikonę i ciąg tytułu do etykietki narzędzia.|
|[CToolTipCtrl:: SetToolInfo](#settoolinfo)|Ustawia informacje, które są przechowywane w etykietce narzędzia dla narzędzia.|
|[CToolTipCtrl:: SetToolRect](#settoolrect)|Ustawia nowy prostokąt ograniczający dla narzędzia.|
|[CToolTipCtrl:: SetWindowTheme](#setwindowtheme)|Ustawia styl wizualizacji okna etykietki narzędzia.|
|[CToolTipCtrl:: Update](#update)|Wymusza Odrysowanie bieżącego narzędzia.|
|[CToolTipCtrl:: UpdateTipText](#updatetiptext)|Ustawia tekst etykietki narzędzia dla narzędzia.|

## <a name="remarks"></a>Uwagi

"Narzędzie" to okno, takie jak okno podrzędne lub kontrolka, lub prostokątny obszar zdefiniowany przez aplikację w obszarze klienta okna. Etykietka narzędzia jest ukryta w większości czasu, pojawia się tylko wtedy, gdy użytkownik umieści kursor na narzędziu i pozostawia go przez około pół sekundy. Etykietka narzędzia pojawia się blisko kursora i znika, gdy użytkownik kliknie przycisk myszy lub przesunie kursor z narzędzia.

`CToolTipCtrl` Program udostępnia funkcje sterujące początkową godziną i czasem trwania etykietki narzędzia, szerokości marginesów otaczających tekst etykietki narzędzia, szerokości okna etykietki narzędzia oraz koloru tła i tekstu etykietki narzędzia. Pojedyncza kontrolka etykietka narzędzia zawiera informacje dla więcej niż jednego narzędzia.

`CToolTipCtrl`Klasa oferuje funkcje formantu etykietki narzędzia typowego dla systemu Windows. Ten formant (i w związku z tym `CToolTipCtrl` Klasa) jest dostępny tylko dla programów uruchomionych w systemach windows 95/98 i Windows NT w wersji 3,51 i nowszych.

Aby uzyskać więcej informacji na temat włączania etykietek narzędzi, zobacz [porady dotyczące narzędzi w systemie Windows niepochodzące od obiektu CFrameWnd](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).

Aby uzyskać więcej informacji na temat korzystania z programu `CToolTipCtrl` , zobacz [kontrolki](../../mfc/controls-mfc.md) i [Używanie CToolTipCtrl](../../mfc/using-ctooltipctrl.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CToolTipCtrl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcmn. h

## <a name="ctooltipctrlactivate"></a><a name="activate"></a> CToolTipCtrl:: Activate

Wywołaj tę funkcję, aby uaktywnić lub dezaktywować formant etykietki narzędzia.

```cpp
void Activate(BOOL bActivate);
```

### <a name="parameters"></a>Parametry

*bActivate*<br/>
Określa, czy formant etykietki narzędzia ma być aktywowany, czy zdezaktywowany.

### <a name="remarks"></a>Uwagi

Jeśli *bActivate* ma wartość true, formant jest aktywowany; Jeśli wartość jest równa FALSE, zostanie zdezaktywowana.

Gdy formant etykietki narzędzia jest aktywny, informacje etykietki narzędzia pojawiają się, gdy kursor znajduje się na narzędziu zarejestrowanym w kontrolce; gdy jest nieaktywny, informacje etykietki narzędzia nie są wyświetlane, nawet gdy kursor znajduje się w narzędziu.

### <a name="example"></a>Przykład

  Zobacz przykład dla [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrladdtool"></a><a name="addtool"></a> CToolTipCtrl:: Add— narzędzie

Rejestruje narzędzie z kontrolką etykietki narzędzia.

```
BOOL AddTool(
    CWnd* pWnd,
    UINT nIDText,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);

BOOL AddTool(
    CWnd* pWnd,
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Parametry

*pWnd*<br/>
Wskaźnik do okna, które zawiera narzędzie.

*nIDText*<br/>
Identyfikator zasobu ciągu, który zawiera tekst dla narzędzia.

*lpRectTool*<br/>
Wskaźnik do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) zawierający współrzędne prostokąta obwiedni narzędzia. Współrzędne są względne w lewym górnym rogu obszaru klienta okna identyfikowanego przez *pWnd*.

*nIDTool*<br/>
Identyfikator narzędzia.

*lpszText*<br/>
Wskaźnik na tekst narzędzia. Jeśli ten parametr zawiera wartość LPSTR_TEXTCALLBACK, TTN_NEEDTEXT komunikaty powiadomień przejdą do elementu nadrzędnego okna, do którego wskazuje *pWnd* .

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Parametry *lpRectTool* i *nIDTool* muszą być prawidłowe lub jeśli *lpRectTool* ma wartość null, *nIDTool* musi mieć wartość 0.

Kontrolka etykietki narzędzia może być skojarzona z więcej niż jednym narzędziem. Wywołaj tę funkcję, aby zarejestrować narzędzie z kontrolką etykietki narzędzia, tak aby informacje przechowywane w etykietce narzędzia były wyświetlane po umieszczeniu kursora w narzędziu.

> [!NOTE]
> Nie można ustawić etykietki narzędzia do kontrolki statycznej przy użyciu `AddTool` .

### <a name="example"></a>Przykład

  Zobacz przykład dla [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrladjustrect"></a><a name="adjustrect"></a> CToolTipCtrl:: AdjustRect

Konwertuje między prostokątem wyświetlania tekstu kontrolki ToolTip a jego prostokątem okna.

```
BOOL AdjustRect(
    LPRECT lprc,
    BOOL bLarger = TRUE);
```

### <a name="parameters"></a>Parametry

*lprc*<br/>
Wskaźnik do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) , która zawiera prostokąt okna etykietki narzędzia lub prostokąt wyświetlania tekstu.

*bLarger*<br/>
Jeśli wartość jest równa TRUE, *lprc* służy do określania prostokąta wyświetlania tekstu i otrzymuje odpowiedni prostokąt okna. W przypadku wartości FALSE *lprc* jest używany do określania prostokąta okna i odbiera odpowiedni prostokąt wyświetlania tekstu.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli prostokąt został pomyślnie dostosowany; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska oblicza prostokąt wyświetlania tekstu kontrolki etykietki narzędzia z jego prostokąta okna lub prostokąt okna etykietki narzędzia, który jest wymagany do wyświetlenia określonego prostokąta wyświetlania tekstu.

Ta funkcja członkowska implementuje zachowanie [TTM_ADJUSTRECT](/windows/win32/Controls/ttm-adjustrect)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlcreate"></a><a name="create"></a> CToolTipCtrl:: Create

Tworzy formant etykietki narzędzia i dołącza go do `CToolTipCtrl` obiektu.

```
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```

### <a name="parameters"></a>Parametry

*pParentWnd*<br/>
Określa okno nadrzędne kontrolki etykietki narzędzia, zazwyczaj a `CDialog` . Nie może mieć wartości NULL.

*dwStyle*<br/>
Określa styl kontrolki etykietki narzędzia. Zobacz sekcję **uwagi** , aby uzyskać więcej informacji.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli `CToolTipCtrl` obiekt został pomyślnie utworzony; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Tworzysz `CToolTipCtrl` dwa kroki. Najpierw Wywołaj konstruktora, aby skonstruować `CToolTipCtrl` obiekt, a następnie Wywołaj polecenie, `Create` Aby utworzyć formant etykietki narzędzia i dołączyć go do `CToolTipCtrl` obiektu.

Parametr *dwStyle* może być dowolną kombinacją [stylów okna](../../mfc/reference/styles-used-by-mfc.md#window-styles). Ponadto kontrolka etykietki narzędzi ma dwie style specyficzne dla klasy: TTS_ALWAYSTIP i TTS_NOPREFIX.

|Styl|Znaczenie|
|-----------|-------------|
|TTS_ALWAYSTIP|Określa, że etykietka narzędzia będzie wyświetlana po umieszczeniu kursora na narzędziu, niezależnie od tego, czy okno właściciela kontrolki etykietki narzędzia jest aktywne, czy nieaktywne. Bez tego stylu formant etykietki narzędzia pojawia się, gdy okno właściciela narzędzia jest aktywne, ale nie gdy jest nieaktywne.|
|TTS_NOPREFIX|Ten styl uniemożliwia systemowi odcięcie znaku handlowego "i" (&) od ciągu. Jeśli kontrolka etykietki narzędzia nie ma TTS_NOPREFIX stylu, system automatycznie przydzieli znaki handlowe "i", dzięki czemu aplikacja może używać tego samego ciągu zarówno jako elementu menu, jak i jako tekstu w kontrolce etykietki narzędzia.|

Kontrolka etykietki narzędzia ma style okna WS_POPUP i WS_EX_TOOLWINDOW, niezależnie od tego, czy są one określone podczas tworzenia formantu.

Aby utworzyć kontrolkę etykietki narzędzi z rozszerzonymi stylami systemu Windows, wywołaj [CToolTipCtrl:: CreateEx](#createex) zamiast `Create` .

### <a name="example"></a>Przykład

  Zobacz przykład dla [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrlcreateex"></a><a name="createex"></a> CToolTipCtrl:: CreateEx

Tworzy kontrolkę (okno podrzędne) i kojarzy ją z `CToolTipCtrl` obiektem.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwStyle = 0,
    DWORD dwStyleEx = 0);
```

### <a name="parameters"></a>Parametry

*pParentWnd*<br/>
Wskaźnik do okna, które jest elementem nadrzędnym formantu.

*dwStyle*<br/>
Określa styl kontrolki etykietki narzędzia. Aby uzyskać więcej informacji, zobacz sekcję **uwagi** w temacie [Tworzenie](#create) .

*dwStyleEx*<br/>
Określa rozszerzony styl formantu, który jest tworzony. Aby zapoznać się z listą rozszerzonych stylów systemu Windows, zobacz *dwExStyle* parametru [elementu CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) w Windows SDK.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli w przeciwnym razie określono wartość 0.

### <a name="remarks"></a>Uwagi

Użyj `CreateEx` zamiast `Create` , aby zastosować rozszerzone style systemu Windows, określone przez **WS_EX_** wstępny styl systemu Windows.

## <a name="ctooltipctrlctooltipctrl"></a><a name="ctooltipctrl"></a> CToolTipCtrl:: CToolTipCtrl

Konstruuje `CToolTipCtrl` obiekt.

```
CToolTipCtrl();
```

### <a name="remarks"></a>Uwagi

Należy wywołać `Create` po konstrukcji obiektu.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]

## <a name="ctooltipctrldeltool"></a><a name="deltool"></a> CToolTipCtrl::D elTool

Usuwa narzędzie określone przez *pWnd* i *nIDTool* z kolekcji narzędzi obsługiwanych przez kontrolkę etykietki narzędzia.

```cpp
void DelTool(
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Parametry

*pWnd*<br/>
Wskaźnik do okna, które zawiera narzędzie.

*nIDTool*<br/>
Identyfikator narzędzia.

## <a name="ctooltipctrlgetbubblesize"></a><a name="getbubblesize"></a> CToolTipCtrl:: GetBubbleSize

Pobiera rozmiar etykietki narzędzia.

```
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Parametry

*lpToolInfo*<br/>
Wskaźnik do struktury [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) etykietki narzędzia.

### <a name="return-value"></a>Wartość zwracana

Rozmiar etykietki narzędzia.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_GETBUBBLESIZE](/windows/win32/Controls/ttm-getbubblesize)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlgetcurrenttool"></a><a name="getcurrenttool"></a> CToolTipCtrl:: GetCurrentTool

Pobiera informacje, takie jak rozmiar, położenie i tekst okna etykietki narzędzia wyświetlanego przez bieżącą kontrolkę ToolTip.

```
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Parametry

*lpToolInfo*\
określoną Wskaźnik na strukturę [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) , która otrzymuje informacje o bieżącym oknie etykietki narzędzia.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli informacje są pobierane pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [TTM_GETCURRENTTOOL](/windows/win32/Controls/ttm-getcurrenttool) , który jest opisany w Windows SDK.

### <a name="example"></a>Przykład

Poniższy przykład kodu pobiera informacje o bieżącym oknie etykietki narzędzia.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]

## <a name="ctooltipctrlgetdelaytime"></a><a name="getdelaytime"></a> CToolTipCtrl:: GetDelayTime

Pobiera początkowe, wyskakujące okienka i ponownie pokazuj bieżące ustawienia dla kontrolki etykietki narzędzia.

```
int GetDelayTime(DWORD dwDuration) const;
```

### <a name="parameters"></a>Parametry

*dwDuration*<br/>
Flaga określająca, która wartość czasu trwania zostanie pobrana. Ten parametr może mieć jedną z następujących wartości:

- TTDT_AUTOPOP pobrać czas, przez jaki okno etykietki narzędzia pozostanie widoczne, jeśli wskaźnik jest ruchomy w obrębie prostokąta z obwiednią narzędzia.

- TTDT_INITIAL pobrać długość czasu, przez jaki wskaźnik musi pozostać nieruchomy w obrębie prostokąta ograniczonego narzędzia, zanim zostanie wyświetlone okno etykietki narzędzia.

- TTDT_RESHOW pobrać długość czasu, przez który kolejne okna etykietki narzędzi będą wyświetlane, gdy wskaźnik przesuwa się z jednego narzędzia do innego.

### <a name="return-value"></a>Wartość zwracana

Określony czas opóźnienia (w milisekundach)

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_GETDELAYTIME](/windows/win32/Controls/ttm-getdelaytime)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlgetmargin"></a><a name="getmargin"></a> CToolTipCtrl:: GetMargin

Pobiera górny, lewy, dolny i prawy margines ustawiony dla okna etykietki narzędzia.

```cpp
void GetMargin(LPRECT lprc) const;
```

### <a name="parameters"></a>Parametry

*lprc*<br/>
Adres `RECT` struktury, która będzie otrzymywać informacje o marginesie. Elementy członkowskie struktury [Rect](/windows/win32/api/windef/ns-windef-rect) nie definiują prostokąta ograniczenia. Na potrzeby tego komunikatu elementy członkowskie struktury są interpretowane w następujący sposób:

|Członek|Reprezentowana|
|------------|--------------------|
|`top`|Odległość między górną krawędzią a górną częścią tekstu etykietki narzędzia (w pikselach).|
|`left`|Odległość między lewą krawędzią a lewym końcem tekstu porady (w pikselach).|
|`bottom`|Odległość między dolną krawędzią a dolną częścią tekstu porady (w pikselach).|
|`right`|Odległość między prawą krawędzią i prawą końcówką tekstu porady (w pikselach).|

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_GETMARGIN](/windows/win32/Controls/ttm-getmargin)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlgetmaxtipwidth"></a><a name="getmaxtipwidth"></a> CToolTipCtrl:: GetMaxTipWidth

Pobiera maksymalną szerokość okna etykietki narzędzia.

```
int GetMaxTipWidth() const;
```

### <a name="return-value"></a>Wartość zwracana

Maksymalna szerokość okna etykietki narzędzia.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_GETMAXTIPWIDTH](/windows/win32/Controls/ttm-getmaxtipwidth)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlgettext"></a><a name="gettext"></a> CToolTipCtrl:: gettext

Pobiera tekst, który jest utrzymywany przez kontrolkę etykietki narzędzia dla narzędzia.

```cpp
void GetText(
    CString& str,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Parametry

*str*<br/>
Odwołanie do `CString` obiektu, który odbiera tekst narzędzia.

*pWnd*<br/>
Wskaźnik do okna, które zawiera narzędzie.

*nIDTool*<br/>
Identyfikator narzędzia.

### <a name="remarks"></a>Uwagi

Parametry *pWnd* i *nIDTool* identyfikują narzędzie. Jeśli to narzędzie zostało wcześniej zarejestrowane przy użyciu kontrolki etykietki narzędzia przez poprzednie wywołanie do `CToolTipCtrl::AddTool` , obiekt, do którego odwołuje się parametr *str* , ma przypisany tekst narzędzia.

## <a name="ctooltipctrlgettipbkcolor"></a><a name="gettipbkcolor"></a> CToolTipCtrl:: GetTipBkColor

Pobiera kolor tła w oknie etykietki narzędzia.

```
COLORREF GetTipBkColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość [COLORREF](/windows/win32/gdi/colorref) , która reprezentuje kolor tła.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_GETTIPBKCOLOR](/windows/win32/Controls/ttm-gettipbkcolor)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlgettiptextcolor"></a><a name="gettiptextcolor"></a> CToolTipCtrl:: GetTipTextColor

Pobiera kolor tekstu w oknie etykietki narzędzia.

```
COLORREF GetTipTextColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość [COLORREF](/windows/win32/gdi/colorref) , która reprezentuje kolor tekstu.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_GETTIPTEXTCOLOR](/windows/win32/Controls/ttm-gettiptextcolor)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlgettitle"></a><a name="gettitle"></a> CToolTipCtrl:: getTitle

Pobiera tytuł bieżącej kontrolki ToolTip.

```cpp
void GetTitle(PTTGETTITLE pttgt) const;
```

### <a name="parameters"></a>Parametry

*pttgt*\
określoną Wskaźnik do struktury [TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) , która zawiera informacje o kontrolce etykietki narzędzia. Gdy ta metoda zwraca, składowa *pszTitle* struktury [TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) wskazuje na tekst tytułu.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [TTM_GETTITLE](/windows/win32/Controls/ttm-gettitle) , który jest opisany w Windows SDK.

## <a name="ctooltipctrlgettoolcount"></a><a name="gettoolcount"></a> CToolTipCtrl:: GetToolCount

Pobiera liczbę narzędzi zarejestrowanych przy użyciu kontrolki etykietki narzędzia.

```
int GetToolCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba narzędzi zarejestrowanych w kontrolce etykietki narzędzia.

## <a name="ctooltipctrlgettoolinfo"></a><a name="gettoolinfo"></a> CToolTipCtrl:: GetToolInfo

Pobiera informacje o narzędziu utrzymywane przez kontrolkę etykietki narzędzia.

```
BOOL GetToolInfo(
    CToolInfo& ToolInfo,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>Parametry

*ToolInfo*<br/>
Odwołanie do `TOOLINFO` obiektu, który odbiera tekst narzędzia.

*pWnd*<br/>
Wskaźnik do okna, które zawiera narzędzie.

*nIDTool*<br/>
Identyfikator narzędzia.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

`hwnd` `uId` Elementy członkowskie struktury [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) , do których odwołuje się *CToolInfo* , identyfikują narzędzie. Jeśli to narzędzie zostało zarejestrowane za pomocą kontrolki etykietki narzędzia przez poprzednie wywołanie do `AddTool` , `TOOLINFO` Struktura jest wypełniana informacjami o narzędziu.

## <a name="ctooltipctrlhittest"></a><a name="hittest"></a> CToolTipCtrl:: HitTest

Testuje punkt, aby określić, czy znajduje się w granicach prostokąta danego narzędzia i, jeśli tak, pobierze informacje o narzędziu.

```
BOOL HitTest(
    CWnd* pWnd,
    CPoint pt,
    LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>Parametry

*pWnd*<br/>
Wskaźnik do okna, które zawiera narzędzie.

*zmiennoprzecinkow*<br/>
Wskaźnik do `CPoint` obiektu zawierającego współrzędne punktu do przetestowania.

*lpToolInfo*<br/>
Wskaźnik do struktury [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) , który zawiera informacje o narzędziu.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli punkt określony przez informacje o teście trafień znajduje się w prostokącie obwiedni narzędzia; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Jeśli ta funkcja zwróci wartość różną od zera, struktura wskazywana przez *lpToolInfo* jest wypełniana informacjami o narzędziu, w których znajduje się punkt.

`TTHITTESTINFO`Struktura jest zdefiniowana w następujący sposób:

```cpp
typedef struct _TT_HITTESTINFO { // tthti
    HWND hwnd;   // handle of tool or window with tool
    POINT pt;    // client coordinates of point to test
    TOOLINFO ti; // receives information about the tool
} TTHITTESTINFO, FAR * LPHITTESTINFO;
```

- `hwnd`

   Określa uchwyt narzędzia.

- `pt`

   Określa współrzędne punktu, jeśli punkt znajduje się w prostokącie obwiedni narzędzia.

- `ti`

   Informacje o narzędziu. Aby uzyskać więcej informacji na temat `TOOLINFO` struktury, zobacz [CToolTipCtrl:: GetToolInfo](#gettoolinfo).

## <a name="ctooltipctrlpop"></a><a name="pop"></a> CToolTipCtrl::P op

Usuwa wyświetlone okno etykietki narzędzi z widoku.

```cpp
void Pop();
```

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_POP](/windows/win32/Controls/ttm-pop)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlpopup"></a><a name="popup"></a> CToolTipCtrl::P opup

Powoduje, że bieżąca kontrolka tooltip jest wyświetlana na współrzędnej ostatniej wiadomości myszy.

```cpp
void Popup();
```

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [TTM_POPUP](/windows/win32/Controls/ttm-popup) , który jest opisany w Windows SDK.

### <a name="example"></a>Przykład

Poniższy przykład kodu wyświetla okno etykietki narzędzia.

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]

## <a name="ctooltipctrlrelayevent"></a><a name="relayevent"></a> CToolTipCtrl:: RelayEvent

Przekazuje komunikat myszy do kontrolki etykietki narzędzia do przetworzenia.

```cpp
void RelayEvent(LPMSG lpMsg);
```

### <a name="parameters"></a>Parametry

*lpMsg*<br/>
Wskaźnik do struktury [MSG](/windows/win32/api/winuser/ns-winuser-msg) , która zawiera komunikat do przekazania.

### <a name="remarks"></a>Uwagi

Kontrolka etykietki narzędzia przetwarza tylko następujące komunikaty, które są do niego wysyłane przez `RelayEvent` :

|WM_LBUTTONDOWN|WM_MOUSEMOVE|
|---------------------|-------------------|
|WM_LBUTTONUP|WM_RBUTTONDOWN|
|WM_MBUTTONDOWN|WM_RBUTTONUP|
|WM_MBUTTONUP||

### <a name="example"></a>Przykład

  Zobacz przykład dla [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).

## <a name="ctooltipctrlsetdelaytime"></a><a name="setdelaytime"></a> CToolTipCtrl:: SetDelayTime

Ustawia czas opóźnienia dla kontrolki etykietki narzędzia.

```cpp
void SetDelayTime(UINT nDelay);

void SetDelayTime(
    DWORD dwDuration,
    int iTime);
```

### <a name="parameters"></a>Parametry

*nDelay*<br/>
Określa nowy czas opóźnienia (w milisekundach).

*dwDuration*<br/>
Flaga określająca, która wartość czasu trwania zostanie pobrana. Aby uzyskać opis prawidłowych wartości, zobacz [CToolTipCtrl:: GetDelayTime](#getdelaytime) .

*iTime*<br/>
Określony czas opóźnienia (w milisekundach).

### <a name="remarks"></a>Uwagi

Czas opóźnienia to czas, przez jaki kursor musi pozostawać w narzędziu, zanim pojawi się okno etykietki narzędzia. Domyślny czas opóźnienia wynosi 500 milisekund.

## <a name="ctooltipctrlsetmargin"></a><a name="setmargin"></a> CToolTipCtrl:: SetMargin

Ustawia górny, lewy, dolny i prawy margines dla okna etykietki narzędzia.

```cpp
void SetMargin(LPRECT lprc);
```

### <a name="parameters"></a>Parametry

*lprc*<br/>
Adres `RECT` struktury zawierającej informacje o marginesie, które mają zostać ustawione. Elementy członkowskie `RECT` struktury nie definiują prostokąta ograniczenia. Aby uzyskać opis informacji o marginesie, zobacz [CToolTipCtrl:: GetMargin](#getmargin) .

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_SETMARGIN](/windows/win32/Controls/ttm-setmargin)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlsetmaxtipwidth"></a><a name="setmaxtipwidth"></a> CToolTipCtrl:: SetMaxTipWidth

Ustawia maksymalną szerokość okna etykietki narzędzia.

```
int SetMaxTipWidth(int iWidth);
```

### <a name="parameters"></a>Parametry

*iWidth*<br/>
Maksymalna szerokość okna etykietki narzędzia, która ma zostać ustawiona.

### <a name="return-value"></a>Wartość zwracana

Poprzednia Maksymalna szerokość porady.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_SETMAXTIPWIDTH](/windows/win32/Controls/ttm-setmaxtipwidth)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlsettipbkcolor"></a><a name="settipbkcolor"></a> CToolTipCtrl:: SetTipBkColor

Ustawia kolor tła w oknie etykietki narzędzia.

```cpp
void SetTipBkColor(COLORREF clr);
```

### <a name="parameters"></a>Parametry

*CLR*<br/>
Nowy kolor tła.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_SETTIPBKCOLOR](/windows/win32/Controls/ttm-settipbkcolor)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlsettiptextcolor"></a><a name="settiptextcolor"></a> CToolTipCtrl:: SetTipTextColor

Ustawia kolor tekstu w oknie etykietki narzędzia.

```cpp
void SetTipTextColor(COLORREF clr);
```

### <a name="parameters"></a>Parametry

*CLR*<br/>
Nowy kolor tekstu.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_SETTIPTEXTCOLOR](/windows/win32/Controls/ttm-settiptextcolor)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlsettitle"></a><a name="settitle"></a> CToolTipCtrl:: settitle

Dodaje standardową ikonę i ciąg tytułu do etykietki narzędzia.

```
BOOL SetTitle(
    UINT uIcon,
    LPCTSTR lpstrTitle);
```

### <a name="parameters"></a>Parametry

*uIcon*<br/>
Zobacz *ikonę* w [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle) w Windows SDK.

*lpstrTitle*<br/>
Wskaźnik do ciągu tytułu.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska implementuje zachowanie [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle)komunikatu Win32, zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlsettoolinfo"></a><a name="settoolinfo"></a> CToolTipCtrl:: SetToolInfo

Ustawia informacje, które są przechowywane w etykietce narzędzia dla narzędzia.

```cpp
void SetToolInfo(LPTOOLINFO lpToolInfo);
```

### <a name="parameters"></a>Parametry

*lpToolInfo*<br/>
Wskaźnik do struktury [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) , który określa informacje do ustawienia.

## <a name="ctooltipctrlsettoolrect"></a><a name="settoolrect"></a> CToolTipCtrl:: SetToolRect

Ustawia nowy prostokąt ograniczający dla narzędzia.

```cpp
void SetToolRect(
    CWnd* pWnd,
    UINT_PTR nIDTool,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Parametry

*pWnd*<br/>
Wskaźnik do okna, które zawiera narzędzie.

*nIDTool*<br/>
Identyfikator narzędzia.

*lpRect*<br/>
Wskaźnik do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) , który określa nowy prostokąt ograniczający.

## <a name="ctooltipctrlsetwindowtheme"></a><a name="setwindowtheme"></a> CToolTipCtrl:: SetWindowTheme

Ustawia styl wizualizacji okna etykietki narzędzia.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parametry

*pszSubAppName*<br/>
Wskaźnik do ciągu Unicode, który zawiera styl wizualizacji do ustawienia.

### <a name="return-value"></a>Wartość zwracana

Wartość zwracana nie jest używana.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska emuluje funkcjonalność komunikatu [TTM_SETWINDOWTHEME](/windows/win32/Controls/ttm-setwindowtheme) , zgodnie z opisem w Windows SDK.

## <a name="ctooltipctrlupdate"></a><a name="update"></a> CToolTipCtrl:: Update

Wymusza Odrysowanie bieżącego narzędzia.

```cpp
void Update();
```

## <a name="ctooltipctrlupdatetiptext"></a><a name="updatetiptext"></a> CToolTipCtrl:: UpdateTipText

Aktualizuje tekst etykietki narzędzia dla narzędzi tego formantu.

```cpp
void UpdateTipText(
    LPCTSTR lpszText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);

void UpdateTipText(
    UINT nIDText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>Parametry

*lpszText*<br/>
Wskaźnik na tekst narzędzia.

*pWnd*<br/>
Wskaźnik do okna, które zawiera narzędzie.

*nIDTool*<br/>
Identyfikator narzędzia.

*nIDText*<br/>
Identyfikator zasobu ciągu, który zawiera tekst dla narzędzia.

## <a name="see-also"></a>Zobacz też

[Klasa CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CToolBar](../../mfc/reference/ctoolbar-class.md)

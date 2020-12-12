---
description: 'Dowiedz się więcej na temat: Klasa korzystanie CReBarCtrl'
title: Klasa korzystanie CReBarCtrl
ms.date: 11/19/2018
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
ms.openlocfilehash: 75caee2fb0b6bb883ecb421325d41b25c38252b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301233"
---
# <a name="crebarctrl-class"></a>Klasa korzystanie CReBarCtrl

Hermetyzuje funkcjonalność formantu paska pomocniczego, który jest kontenerem dla okna podrzędnego.

## <a name="syntax"></a>Składnia

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Korzystanie CReBarCtrl:: Korzystanie CReBarCtrl](#crebarctrl)|Konstruuje `CReBarCtrl` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Korzystanie CReBarCtrl:: BeginDrag](#begindrag)|Umieszcza formant paska pomocniczego w trybie przeciągania i upuszczania.|
|[Korzystanie CReBarCtrl:: Create](#create)|Tworzy formant paska pomocniczego i dołącza go do `CReBarCtrl` obiektu.|
|[Korzystanie CReBarCtrl:: CreateEx](#createex)|Tworzy formant paska pomocniczego z określonymi stylami rozszerzonymi systemu Windows i dołącza go do `CReBarCtrl` obiektu.|
|[Korzystanie CReBarCtrl::D eleteBand](#deleteband)|Usuwa przedział z kontrolki paska pomocniczego.|
|[Korzystanie CReBarCtrl::D ragMove](#dragmove)|Aktualizuje pozycję przeciągania w kontrolce paska pomocniczego po wywołaniu `BeginDrag` .|
|[Korzystanie CReBarCtrl:: EndDrag](#enddrag)|Kończy operację przeciągania i upuszczania kontrolki paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetBandBorders](#getbandborders)|Pobiera obramowania pasma.|
|[Korzystanie CReBarCtrl:: GetBandCount](#getbandcount)|Pobiera liczbę pasm znajdujących się obecnie w kontrolce paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetBandInfo](#getbandinfo)|Pobiera informacje o określonym paśmie w kontrolce paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetBandMargins](#getbandmargins)|Pobiera marginesy pasma.|
|[Korzystanie CReBarCtrl:: GetBarHeight](#getbarheight)|Pobiera wysokość formantu paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetBarInfo](#getbarinfo)|Pobiera informacje o kontrolce paska pomocniczego i liście obrazów, których używa.|
|[Korzystanie CReBarCtrl:: GetBkColor](#getbkcolor)|Pobiera domyślny kolor tła formantu paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetColorScheme](#getcolorscheme)|Pobiera strukturę [ColorScheme](/windows/win32/api/commctrl/ns-commctrl-colorscheme) skojarzoną z kontrolką paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetDropTarget](#getdroptarget)|Pobiera wskaźnik interfejsu formantu paska pomocniczego `IDropTarget` .|
|[Korzystanie CReBarCtrl:: getextendeds](#getextendedstyle)|Pobiera rozszerzony styl bieżącej kontrolki paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetImageList](#getimagelist)|Pobiera listę obrazów skojarzoną z kontrolką paska pomocniczego.|
|[Korzystanie CReBarCtrl:: getpaleta](#getpalette)|Pobiera bieżącą paletę kontrolki paska pomocniczego.|
|[Korzystanie CReBarCtrl:: getRect](#getrect)|Pobiera prostokąt ograniczenia dla danego pasma w kontrolce paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetRowCount](#getrowcount)|Pobiera liczbę wierszy pasma w kontrolce paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetRowHeight](#getrowheight)|Pobiera wysokość określonego wiersza w kontrolce paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetTextColor](#gettextcolor)|Pobiera domyślny kolor tekstu formantu paska pomocniczego.|
|[Korzystanie CReBarCtrl:: GetToolTips](#gettooltips)|Pobiera dojście do kontrolki etykietki narzędzia skojarzonej z kontrolką paska pomocniczego.|
|[Korzystanie CReBarCtrl:: HitTest](#hittest)|Określa, która część pasma paska pomocniczego znajduje się w danym punkcie na ekranie, jeśli na tym etapie istnieje pasmo paska pomocniczego.|
|[Korzystanie CReBarCtrl:: IDToIndex](#idtoindex)|Konwertuje identyfikator pasma (ID) na indeks pasma w kontrolce paska pomocniczego.|
|[Korzystanie CReBarCtrl:: InsertBand](#insertband)|Wstawia nowy pasek w kontrolce paska pomocniczego.|
|[Korzystanie CReBarCtrl:: MaximizeBand](#maximizeband)|Zmienia rozmiar pasma w kontrolce paska pomocniczego na jej największy rozmiar.|
|[Korzystanie CReBarCtrl:: MinimizeBand](#minimizeband)|Zmienia rozmiar pasma w kontrolce paska pomocniczego na najmniejszy rozmiar.|
|[Korzystanie CReBarCtrl:: MoveBand](#moveband)|Przenosi pasmo z jednego indeksu do innego.|
|[Korzystanie CReBarCtrl::P ushChevron](#pushchevron)|Program programowo wypycha cudzysłów ostrokątny.|
|[Korzystanie CReBarCtrl:: RestoreBand](#restoreband)|Zmienia rozmiar pasma w kontrolce paska pomocniczego na jego idealny rozmiar.|
|[Korzystanie CReBarCtrl:: SetBandInfo](#setbandinfo)|Ustawia charakterystykę istniejącego pasma w kontrolce paska pomocniczego.|
|[Korzystanie CReBarCtrl:: setbandwidth](#setbandwidth)|Ustawia szerokość określonego zadokowanego pasma w bieżącym formancie paska pomocniczego.|
|[Korzystanie CReBarCtrl:: SetBarInfo](#setbarinfo)|Ustawia charakterystykę formantu paska pomocniczego.|
|[Korzystanie CReBarCtrl:: SetBkColor](#setbkcolor)|Ustawia domyślny kolor tła formantu paska pomocniczego.|
|[Korzystanie CReBarCtrl:: SetColorScheme](#setcolorscheme)|Ustawia schemat kolorów dla przycisków w kontrolce paska pomocniczego.|
|[Korzystanie CReBarCtrl:: setextended](#setextendedstyle)|Ustawia rozszerzone style dla bieżącej kontrolki paska pomocniczego.|
|[Korzystanie CReBarCtrl:: SetImageList](#setimagelist)|Ustawia listę obrazów kontrolki paska pomocniczego.|
|[Korzystanie CReBarCtrl:: SetOwner](#setowner)|Ustawia okno właściciela kontrolki paska pomocniczego.|
|[Korzystanie CReBarCtrl:: setpaleta](#setpalette)|Ustawia bieżącą paletę kontrolki paska pomocniczego.|
|[Korzystanie CReBarCtrl:: SetTextColor](#settextcolor)|Ustawia domyślny kolor tekstu formantu paska pomocniczego.|
|[Korzystanie CReBarCtrl:: setetykietki narzędzi](#settooltips)|Kojarzy formant etykietki narzędzia z kontrolką paska pomocniczego.|
|[Korzystanie CReBarCtrl:: SetWindowTheme](#setwindowtheme)|Ustawia styl wizualizacji formantu paska pomocniczego.|
|[Korzystanie CReBarCtrl:: ShowBand](#showband)|Pokazuje lub ukrywa dany pasek w kontrolce paska pomocniczego.|
|[Korzystanie CReBarCtrl:: SizeToRect](#sizetorect)|Dopasowuje formant paska pomocniczego do określonego prostokąta.|

## <a name="remarks"></a>Uwagi

Aplikacja, w której znajduje się formant paska pomocniczego, przypisuje okno potomne zawarte przez formant paska pomocniczego do pasma paska pomocniczego. Okno podrzędne jest zwykle inną wspólną kontrolką.

Kontrolki paska pomocniczego zawierają co najmniej jedną podgrupę. Każda grupa może zawierać kombinację paska uchwytu, mapy bitowej, etykiety tekstowej i okna podrzędnego. Pasmo może zawierać tylko jeden z tych elementów.

Kontrolka paska pomocniczego może wyświetlać okno podrzędne nad określoną mapą bitową w tle. Można zmienić rozmiar wszystkich paska pomocniczego formantów, z wyjątkiem tych, które używają stylu RBBS_FIXEDSIZE. W miarę zmieniania położenia lub zmiany rozmiaru pasma formantu paska pomocniczego, kontrolka paska pomocniczego zarządza rozmiarem i położeniem okna podrzędnego przypisanego do tego pasma. Aby zmienić rozmiar lub zmianę kolejności pasków w kontrolce, kliknij i przeciągnij pasek uchwytu pasma.

Na poniższej ilustracji przedstawiono kontrolkę paska pomocniczego, która ma trzy pasma:

- Pasmo 0 zawiera płaski, przezroczysty formant paska narzędzi.

- Pasmo 1 zawiera przezroczyste, standardowe i przezroczyste przyciski rozwijane.

- Pasmo 2 zawiera pole kombi i cztery przyciski standardowe.

   ![Przykład menu paska pomocniczego](../../mfc/reference/media/vc4scc1.gif "Przykład menu paska pomocniczego")

## <a name="rebar-control"></a>Paska pomocniczego — formant

Obsługa formantów paska pomocniczego:

- Listy obrazów.

- Obsługa komunikatów.

- Niestandardowe funkcje rysowania.

- Różne style formantów oprócz standardowych stylów okien. Aby uzyskać listę tych stylów, zobacz [Style formantu paska pomocniczego](/windows/win32/Controls/rebar-control-styles) w Windows SDK.

Aby uzyskać więcej informacji, zobacz [using korzystanie CReBarCtrl](../../mfc/using-crebarctrl.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcmn. h

## <a name="crebarctrlbegindrag"></a><a name="begindrag"></a> Korzystanie CReBarCtrl:: BeginDrag

Implementuje zachowanie [RB_BEGINDRAG](/windows/win32/Controls/rb-begindrag)komunikatu Win32, zgodnie z opisem w Windows SDK.

```cpp
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Indeks (liczony od zera) pasma, którego będzie dotyczyć operacja przeciągania i upuszczania.

*dwPos*<br/>
Wartość typu DWORD, która zawiera współrzędne myszy początkowej. Współrzędne poziome są zawarte w LOWORD, a Współrzędna pionowa jest zawarta w HIWORD. Jeśli przejdziesz (DWORD)-1, formant paska pomocniczego będzie używać pozycji myszy przy ostatnim wywołaniu wątku kontrolki `GetMessage` lub `PeekMessage` .

## <a name="crebarctrlcreate"></a><a name="create"></a> Korzystanie CReBarCtrl:: Create

Tworzy formant paska pomocniczego i dołącza go do `CReBarCtrl` obiektu.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametry

*dwStyle*<br/>
Określa kombinację stylów formantu paska pomocniczego zastosowanych do kontrolki. Zobacz [Style formantów paska pomocniczego](/windows/win32/Controls/rebar-control-styles) w Windows SDK, aby uzyskać listę obsługiwanych stylów.

*cinania*<br/>
Odwołanie do obiektu [CRect](../../atl-mfc-shared/reference/crect-class.md) lub struktury [Rect](/windows/win32/api/windef/ns-windef-rect) , który jest pozycją i rozmiarem kontrolki paska pomocniczego.

*pParentWnd*<br/>
Wskaźnik do obiektu [CWnd](../../mfc/reference/cwnd-class.md) , który jest oknem nadrzędnym kontrolki paska pomocniczego. Nie może mieć wartości NULL.

*nID*<br/>
Określa identyfikator formantu paska pomocniczego formantu.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli obiekt został utworzony pomyślnie; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Utwórz kontrolkę paska pomocniczego w dwóch krokach:

1. Wywołaj [Korzystanie CReBarCtrl](#crebarctrl) w celu skonstruowania `CReBarCtrl` obiektu.

1. Wywołaj tę funkcję elementu członkowskiego, która tworzy formant paska pomocniczego systemu Windows i dołącza go do `CReBarCtrl` obiektu.

Po wywołaniu `Create` , są inicjowane typowe formanty.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

## <a name="crebarctrlcreateex"></a><a name="createex"></a> Korzystanie CReBarCtrl:: CreateEx

Tworzy kontrolkę (okno podrzędne) i kojarzy ją z `CReBarCtrl` obiektem.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametry

*dwExStyle*<br/>
Określa rozszerzony styl formantu, który jest tworzony. Aby zapoznać się z listą rozszerzonych stylów systemu Windows, zobacz *dwExStyle* parametru [elementu CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) w Windows SDK.

*dwStyle*<br/>
Określa kombinację stylów formantu paska pomocniczego zastosowanych do kontrolki. Aby zapoznać się z listą obsługiwanych stylów, zobacz [Style formantu paska pomocniczego](/windows/win32/Controls/rebar-control-styles) w Windows SDK.

*cinania*<br/>
Odwołanie do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) opisujące rozmiar i położenie okna, które ma zostać utworzone, we współrzędnych klienta *pParentWnd*.

*pParentWnd*<br/>
Wskaźnik do okna, które jest elementem nadrzędnym formantu.

*nID*<br/>
Identyfikator okna podrzędnego kontrolki.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Użyj `CreateEx` zamiast [tworzenia](#create) , aby zastosować rozszerzone style systemu Windows, które są określone przez **WS_EX_** przedniej stylu rozszerzonego systemu Windows.

## <a name="crebarctrlcrebarctrl"></a><a name="crebarctrl"></a> Korzystanie CReBarCtrl:: Korzystanie CReBarCtrl

Tworzy obiekt `CReBarCtrl`.

```
CReBarCtrl();
```

### <a name="example"></a>Przykład

  Zobacz przykład dla [Korzystanie CReBarCtrl:: Create](#create).

## <a name="crebarctrldeleteband"></a><a name="deleteband"></a> Korzystanie CReBarCtrl::D eleteBand

Implementuje zachowanie [RB_DELETEBAND](/windows/win32/Controls/rb-deleteband)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Liczony od zera indeks pasma do usunięcia.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pasek został usunięty pomyślnie; w przeciwnym razie zero.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

## <a name="crebarctrldragmove"></a><a name="dragmove"></a> Korzystanie CReBarCtrl::D ragMove

Implementuje zachowanie [RB_DRAGMOVE](/windows/win32/Controls/rb-dragmove)komunikatu Win32, zgodnie z opisem w Windows SDK.

```cpp
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>Parametry

*dwPos*<br/>
Wartość DWORD, która zawiera nowe Współrzędne myszy. Współrzędne poziome są zawarte w LOWORD, a Współrzędna pionowa jest zawarta w HIWORD. Jeśli przejdziesz (DWORD)-1, formant paska pomocniczego będzie używać pozycji myszy przy ostatnim wywołaniu wątku kontrolki `GetMessage` lub `PeekMessage` .

## <a name="crebarctrlenddrag"></a><a name="enddrag"></a> Korzystanie CReBarCtrl:: EndDrag

Implementuje zachowanie [RB_ENDDRAG](/windows/win32/Controls/rb-enddrag)komunikatu Win32, zgodnie z opisem w Windows SDK.

```cpp
void EndDrag();
```

## <a name="crebarctrlgetbandborders"></a><a name="getbandborders"></a> Korzystanie CReBarCtrl:: GetBandBorders

Implementuje zachowanie [RB_GETBANDBORDERS](/windows/win32/Controls/rb-getbandborders)komunikatu Win32, zgodnie z opisem w Windows SDK.

```cpp
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Indeks (liczony od zera) pasma, dla którego będą pobierane obramowania.

*Republika*<br/>
Wskaźnik do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) , która będzie odbierać obramowania pasma. Jeśli formant paska pomocniczego ma styl RBS_BANDBORDERS, każdy element członkowski tej struktury otrzyma liczbę pikseli na odpowiedniej stronie pasma, która stanowi obramowanie. Jeśli formant paska pomocniczego nie ma stylu RBS_BANDBORDERS, tylko lewa składowa tej struktury otrzymuje prawidłowe informacje. Aby uzyskać opis stylów formantu paska pomocniczego, zobacz [Style formantów paska pomocniczego](/windows/win32/Controls/rebar-control-styles) w Windows SDK.

## <a name="crebarctrlgetbandcount"></a><a name="getbandcount"></a> Korzystanie CReBarCtrl:: GetBandCount

Implementuje zachowanie [RB_GETBANDCOUNT](/windows/win32/Controls/rb-getbandcount)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba pasm przypisanych do kontrolki.

## <a name="crebarctrlgetbandinfo"></a><a name="getbandinfo"></a> Korzystanie CReBarCtrl:: GetBandInfo

Implementuje zachowanie komunikatu Win32 [RB_GETBANDINFO](/windows/win32/Controls/rb-getbandinfo) zgodnie z opisem w Windows SDK.

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Indeks (liczony od zera) pasma, dla którego zostaną pobrane informacje.

*prbbi*<br/>
Wskaźnik do struktury [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) , aby otrzymać informacje o paśmie. Należy ustawić `cbSize` element członkowski tej struktury do `sizeof(REBARBANDINFO)` i ustawić element `fMask` członkowski dla elementów, które mają zostać pobrane przed wysłaniem tej wiadomości.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

## <a name="crebarctrlgetbandmargins"></a><a name="getbandmargins"></a> Korzystanie CReBarCtrl:: GetBandMargins

Pobiera marginesy pasma.

```cpp
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>Parametry

*pMargins*<br/>
Wskaźnik do struktury [marginesów](/windows/win32/api/uxtheme/ns-uxtheme-margins), który będzie otrzymywał informacje.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska emuluje funkcjonalność komunikatu [RB_GETBANDMARGINS](/windows/win32/Controls/rb-getbandmargins) , zgodnie z opisem w Windows SDK.

## <a name="crebarctrlgetbarheight"></a><a name="getbarheight"></a> Korzystanie CReBarCtrl:: GetBarHeight

Pobiera wysokość paska paska pomocniczego.

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość, która reprezentuje wysokość formantu w pikselach.

## <a name="crebarctrlgetbarinfo"></a><a name="getbarinfo"></a> Korzystanie CReBarCtrl:: GetBarInfo

Implementuje zachowanie [RB_GETBARINFO](/windows/win32/Controls/rb-getbarinfo)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>Parametry

*prbi*<br/>
Wskaźnik do struktury [REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) , która będzie odbierać informacje kontrolne paska pomocniczego.  `sizeof(REBARINFO)` Przed wysłaniem tej wiadomości należy ustawić element członkowski cbSize tej struktury.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

## <a name="crebarctrlgetbkcolor"></a><a name="getbkcolor"></a> Korzystanie CReBarCtrl:: GetBkColor

Implementuje zachowanie [RB_GETBKCOLOR](/windows/win32/Controls/rb-getbkcolor)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość COLORREF, która reprezentuje bieżący domyślny kolor tła.

## <a name="crebarctrlgetcolorscheme"></a><a name="getcolorscheme"></a> Korzystanie CReBarCtrl:: GetColorScheme

Pobiera strukturę [ColorScheme](/windows/win32/api/commctrl/ns-commctrl-colorscheme) dla kontrolki paska pomocniczego.

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parametry

*lpcs*<br/>
Wskaźnik do struktury [ColorScheme](/windows/win32/api/commctrl/ns-commctrl-colorscheme) , zgodnie z opisem w Windows SDK.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

### <a name="remarks"></a>Uwagi

`COLORSCHEME`Struktura zawiera kolor wyróżnienia przycisku i kolor cienia przycisku.

## <a name="crebarctrlgetdroptarget"></a><a name="getdroptarget"></a> Korzystanie CReBarCtrl:: GetDropTarget

Implementuje zachowanie [RB_GETDROPTARGET](/windows/win32/Controls/rb-getdroptarget)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do interfejsu [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget) .

## <a name="crebarctrlgetextendedstyle"></a><a name="getextendedstyle"></a> Korzystanie CReBarCtrl:: getextendeds

Pobiera rozszerzone style bieżącego formantu paska pomocniczego.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>Wartość zwracana

Kombinacja bitowa (lub) flag wskazujących style rozszerzone. Możliwe flagi to RBS_EX_SPLITTER i RBS_EX_TRANSPARENT. Aby uzyskać więcej informacji, zobacz parametr *dwMask* metody [Korzystanie CReBarCtrl:: setextended](#setextendedstyle) .

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [RB_GETEXTENDEDSTYLE](/windows/win32/Controls/rb-dragmove) , który jest opisany w Windows SDK.

## <a name="crebarctrlgetimagelist"></a><a name="getimagelist"></a> Korzystanie CReBarCtrl:: GetImageList

Pobiera `CImageList` obiekt skojarzony z kontrolką paska pomocniczego.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu [Korzystanie CImageList](../../mfc/reference/cimagelist-class.md) . Zwraca wartość NULL, jeśli nie ustawiono żadnej listy obrazów dla kontrolki.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska używa informacji o rozmiarze i masce przechowywanych w strukturze [REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) , zgodnie z opisem w Windows SDK.

## <a name="crebarctrlgetpalette"></a><a name="getpalette"></a> Korzystanie CReBarCtrl:: getpaleta

Pobiera bieżącą paletę kontrolki paska pomocniczego.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu [CPalette](../../mfc/reference/cpalette-class.md) określający bieżącą paletę kontrolki paska pomocniczego.

### <a name="remarks"></a>Uwagi

Należy zauważyć, że ta funkcja członkowska używa `CPalette` obiektu jako wartości zwracanej, a nie elementu HPALETTE.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

## <a name="crebarctrlgetrect"></a><a name="getrect"></a> Korzystanie CReBarCtrl:: getRect

Implementuje zachowanie [RB_GETRECT](/windows/win32/Controls/rb-getrect)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Indeks (liczony od zera) pasma w kontrolce paska pomocniczego.

*Republika*<br/>
Wskaźnik do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) , która będzie odbierać granice pasma paska pomocniczego.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

## <a name="crebarctrlgetrowcount"></a><a name="getrowcount"></a> Korzystanie CReBarCtrl:: GetRowCount

Implementuje zachowanie [RB_GETROWCOUNT](/windows/win32/Controls/rb-getrowcount)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość UINT, która reprezentuje liczbę wierszy pasma w formancie.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

## <a name="crebarctrlgetrowheight"></a><a name="getrowheight"></a> Korzystanie CReBarCtrl:: GetRowHeight

Implementuje zachowanie [RB_GETROWHEIGHT](/windows/win32/Controls/rb-getrowheight)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>Parametry

*uRow*<br/>
Indeks przedziału liczony od zera, który zostanie pobrany.

### <a name="return-value"></a>Wartość zwracana

Wartość UINT, która reprezentuje wysokość wiersza (w pikselach).

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

## <a name="crebarctrlgettextcolor"></a><a name="gettextcolor"></a> Korzystanie CReBarCtrl:: GetTextColor

Implementuje zachowanie [RB_GETTEXTCOLOR](/windows/win32/Controls/rb-gettextcolor)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość COLORREF, która reprezentuje bieżący domyślny kolor tekstu.

## <a name="crebarctrlgettooltips"></a><a name="gettooltips"></a> Korzystanie CReBarCtrl:: GetToolTips

Implementuje zachowanie [RB_GETTOOLTIPS](/windows/win32/Controls/rb-gettooltips)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) .

### <a name="remarks"></a>Uwagi

Należy zauważyć, że implementacja MFC `GetToolTips` zwraca wskaźnik do elementu `CToolTipCtrl` , a nie jako HWND.

## <a name="crebarctrlhittest"></a><a name="hittest"></a> Korzystanie CReBarCtrl:: HitTest

Implementuje zachowanie [RB_HITTEST](/windows/win32/Controls/rb-hittest)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>Parametry

*prbht*<br/>
Wskaźnik do struktury [RBHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-rbhittestinfo) . Przed wysłaniem komunikatu `pt` element członkowski tej struktury musi być zainicjowany do punktu, który zostanie przetestowany w celu współrzędnych klienta.

### <a name="return-value"></a>Wartość zwracana

Indeks (liczony od zera) pasma w danym punkcie lub-1, jeśli w punkcie nie ma paska pomocniczego pasma.

## <a name="crebarctrlidtoindex"></a><a name="idtoindex"></a> Korzystanie CReBarCtrl:: IDToIndex

Implementuje zachowanie [RB_IDTOINDEX](/windows/win32/controls/rb-idtoindex)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>Parametry

*uBandID*<br/>
Zdefiniowany przez aplikację identyfikator określonego pasma, który został przeniesiony do `wID` elementu członkowskiego struktury [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) , gdy zostanie wstawiony pasek.

### <a name="return-value"></a>Wartość zwracana

Indeks pasma liczony od zera, jeśli zakończyło się pomyślnie, lub-1 w przeciwnym razie. W przypadku istnienia zduplikowanych indeksów pasma zwracana jest pierwsza z nich.

## <a name="crebarctrlinsertband"></a><a name="insertband"></a> Korzystanie CReBarCtrl:: InsertBand

Implementuje zachowanie [RB_INSERTBAND](/windows/win32/Controls/rb-insertband)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parametry

*uIndex*<br/>
Indeks w lokalizacji, w której zostanie wstawiony pasmo (liczony od zera). Jeśli ustawisz ten parametr na wartość-1, formant doda nowy punkt w ostatniej lokalizacji.

*prbbi*<br/>
Wskaźnik do struktury [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) , który definiuje pasmo do wstawienia.  `sizeof(REBARBANDINFO)` Przed wywołaniem tej funkcji należy ustawić element członkowski cbSize tej struktury.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

## <a name="crebarctrlmaximizeband"></a><a name="maximizeband"></a> Korzystanie CReBarCtrl:: MaximizeBand

Zmienia rozmiar pasma w kontrolce paska pomocniczego na jej największy rozmiar.

```cpp
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Indeks (liczony od zera) pasma do zmaksymalizowania.

### <a name="remarks"></a>Uwagi

Implementuje zachowanie komunikatu Win32 [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) z `fIdeal` ustawioną na 0, zgodnie z opisem w Windows SDK.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

## <a name="crebarctrlminimizeband"></a><a name="minimizeband"></a> Korzystanie CReBarCtrl:: MinimizeBand

Zmienia rozmiar pasma w kontrolce paska pomocniczego na najmniejszy rozmiar.

```cpp
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Indeks przedziału (liczony od zera), który ma zostać zminimalizowany.

### <a name="remarks"></a>Uwagi

Implementuje zachowanie [RB_MINIMIZEBAND](/windows/win32/Controls/rb-minimizeband)komunikatu Win32, zgodnie z opisem w Windows SDK.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

## <a name="crebarctrlmoveband"></a><a name="moveband"></a> Korzystanie CReBarCtrl:: MoveBand

Implementuje zachowanie [RB_MOVEBAND](/windows/win32/Controls/rb-moveband)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>Parametry

*uFrom*<br/>
Liczony od zera indeks przedziału, który ma zostać przeniesiony.

*matyczna*<br/>
Indeks (liczony od zera) nowej pozycji pasma. Wartość tego parametru nie może być większa niż liczba przedziałów równa 1. Aby uzyskać liczbę pasm, wywołaj [GetBandCount](#getbandcount).

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

## <a name="crebarctrlpushchevron"></a><a name="pushchevron"></a> Korzystanie CReBarCtrl::P ushChevron

Implementuje zachowanie [RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron)komunikatu Win32, zgodnie z opisem w Windows SDK.

```cpp
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Indeks (liczony od zera) pasma, którego ma dotyczyć wypychanie.

*lAppValue*<br/>
Zdefiniowana przez aplikację 32-bitową wartość. Zobacz *lAppValue* w [RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron) w Windows SDK.

## <a name="crebarctrlrestoreband"></a><a name="restoreband"></a> Korzystanie CReBarCtrl:: RestoreBand

Zmienia rozmiar pasma w kontrolce paska pomocniczego na jego idealny rozmiar.

```cpp
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Indeks (liczony od zera) pasma do zmaksymalizowania.

### <a name="remarks"></a>Uwagi

Implementuje zachowanie [RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband) komunikatu Win32 z `fIdeal` ustawioną na 1, zgodnie z opisem w Windows SDK.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

## <a name="crebarctrlsetbandinfo"></a><a name="setbandinfo"></a> Korzystanie CReBarCtrl:: SetBandInfo

Implementuje zachowanie [RB_SETBANDINFO](/windows/win32/Controls/rb-setbandinfo)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Liczony od zera indeks pasma, który ma otrzymywać nowe ustawienia.

*prbbi*<br/>
Wskaźnik do struktury [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) , która definiuje pasmo do wstawienia. `cbSize`Przed wysłaniem tej wiadomości należy ustawić element członkowski tej struktury `sizeof(REBARBANDINFO)` .

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

## <a name="crebarctrlsetbandwidth"></a><a name="setbandwidth"></a> Korzystanie CReBarCtrl:: setbandwidth

Ustawia szerokość określonego zadokowanego pasma w bieżącym formancie paska pomocniczego.

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>Parametry

*uBand*\
podczas Indeks paska pomocniczego pasma liczony od zera.

*cxWidth*\
podczas Nowa szerokość pasma paska pomocniczego (w pikselach).

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli metoda zakończy się pomyślnie. w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [RB_SETBANDWIDTH](/windows/win32/Controls/rb-setbandwidth) , który jest opisany w Windows SDK.

### <a name="example"></a>Przykład

Poniższy przykład kodu definiuje zmienną, `m_rebar` , która jest używana do uzyskiwania dostępu do bieżącej kontrolki paska pomocniczego. Ta zmienna jest używana w następnym przykładzie.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>Przykład

Poniższy przykład kodu ustawia, że każdy paska pomocniczego przedziału ma taką samą szerokość.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

## <a name="crebarctrlsetbarinfo"></a><a name="setbarinfo"></a> Korzystanie CReBarCtrl:: SetBarInfo

Implementuje zachowanie [RB_SETBARINFO](/windows/win32/Controls/rb-setbarinfo)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>Parametry

*prbi*<br/>
Wskaźnik do struktury [REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo) , która zawiera informacje, które mają zostać ustawione. Musisz ustawić `cbSize` element członkowski tej struktury na `sizeof(REBARINFO)` przed wysłaniem tej wiadomości

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

## <a name="crebarctrlsetbkcolor"></a><a name="setbkcolor"></a> Korzystanie CReBarCtrl:: SetBkColor

Implementuje zachowanie [RB_SETBKCOLOR](/windows/win32/Controls/rb-setbkcolor)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>Parametry

*CLR*<br/>
Wartość COLORREF, która reprezentuje nowy domyślny kolor tła.

### <a name="return-value"></a>Wartość zwracana

Wartość [COLORREF](/windows/win32/gdi/colorref) , która reprezentuje poprzedni domyślny kolor tła.

### <a name="remarks"></a>Uwagi

Zapoznaj się z tym tematem, aby uzyskać więcej informacji na temat momentu ustawienia koloru tła i ustawienia wartości domyślnej.

## <a name="crebarctrlsetcolorscheme"></a><a name="setcolorscheme"></a> Korzystanie CReBarCtrl:: SetColorScheme

Ustawia schemat kolorów dla przycisków w kontrolce paska pomocniczego.

```cpp
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>Parametry

*lpcs*<br/>
Wskaźnik do struktury [ColorScheme](/windows/win32/api/commctrl/ns-commctrl-colorscheme) , zgodnie z opisem w Windows SDK.

### <a name="remarks"></a>Uwagi

`COLORSCHEME`Struktura zawiera zarówno kolor wyróżnienia przycisku, jak i kolor cienia przycisku.

## <a name="crebarctrlsetextendedstyle"></a><a name="setextendedstyle"></a> Korzystanie CReBarCtrl:: setextended

Ustawia rozszerzone style dla bieżącej kontrolki paska pomocniczego.

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>Parametry

*dwMask*\
podczas Kombinacja bitowa (lub) flag, które określają, które flagi w parametrze *dwStyleEx* mają zastosowanie. Użyj co najmniej jednej z następujących wartości:

- `RBS_EX_SPLITTER`: Domyślnie Pokaż rozdzielacz u dołu w trybie poziomym i w prawo w trybie pionowym.
- `RBS_EX_TRANSPARENT`: Przekaż komunikat [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) do okna nadrzędnego.

*dwStyleEx*\
podczas Kombinacja bitowa (lub) flag, które określają style, które mają zostać zastosowane. Aby ustawić styl, należy określić tę samą flagę, która jest używana w parametrze *dwMask* . Aby zresetować styl, określ wartość binarną zero.

### <a name="return-value"></a>Wartość zwracana

Poprzedni rozszerzony styl.

### <a name="remarks"></a>Uwagi

Ta metoda wysyła komunikat [RB_SETEXTENDEDSTYLE](/windows/win32/Controls/rb-setextendedstyle) , który jest opisany w Windows SDK.

## <a name="crebarctrlsetimagelist"></a><a name="setimagelist"></a> Korzystanie CReBarCtrl:: SetImageList

Przypisuje listę obrazów do kontrolki paska pomocniczego.

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>Parametry

*pImageList*<br/>
Wskaźnik do obiektu [Korzystanie CImageList](../../mfc/reference/cimagelist-class.md) zawierającego listę obrazów, która ma zostać przypisana do kontrolki paska pomocniczego.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

## <a name="crebarctrlsetowner"></a><a name="setowner"></a> Korzystanie CReBarCtrl:: SetOwner

Implementuje zachowanie [RB_SETPARENT](/windows/win32/Controls/rb-setparent)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Parametry

*pWnd*<br/>
Wskaźnik do obiektu, `CWnd` który ma zostać ustawiony jako właściciel formantu paska pomocniczego.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu [CWnd](../../mfc/reference/cwnd-class.md) , który jest bieżącym właścicielem kontrolki paska pomocniczego.

### <a name="remarks"></a>Uwagi

Należy zauważyć, że ta funkcja członkowska używa wskaźników do `CWnd` obiektów zarówno dla bieżącego, jak i wybranego właściciela kontrolki paska pomocniczego, a nie uchwytów do systemu Windows.

> [!NOTE]
> Ta funkcja członkowska nie zmienia rzeczywistego elementu nadrzędnego, który został ustawiony podczas tworzenia kontrolki; Zamiast tego wysyła komunikaty powiadomień do określonego okna.

## <a name="crebarctrlsetpalette"></a><a name="setpalette"></a> Korzystanie CReBarCtrl:: setpaleta

Implementuje zachowanie [RB_SETPALETTE](/windows/win32/Controls/rb-setpalette)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>Parametry

*hPal*<br/>
Element HPALETTE, który określa nową paletę, która będzie używana przez formant paska pomocniczego.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do obiektu [CPalette](../../mfc/reference/cpalette-class.md) , który określa poprzednią paletę kontrolki paska pomocniczego.

### <a name="remarks"></a>Uwagi

Należy zauważyć, że ta funkcja członkowska używa `CPalette` obiektu jako wartości zwracanej, a nie elementu HPALETTE.

## <a name="crebarctrlsettextcolor"></a><a name="settextcolor"></a> Korzystanie CReBarCtrl:: SetTextColor

Implementuje zachowanie [RB_SETTEXTCOLOR](/windows/win32/Controls/rb-settextcolor)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>Parametry

*CLR*<br/>
Wartość COLORREF, która reprezentuje nowy kolor tekstu w `CReBarCtrl` obiekcie.

### <a name="return-value"></a>Wartość zwracana

Wartość [COLORREF](/windows/win32/gdi/colorref) reprezentująca poprzedni kolor tekstu skojarzony z `CReBarCtrl` obiektem.

### <a name="remarks"></a>Uwagi

Zapewnia obsługę elastyczności koloru tekstu w kontrolce paska pomocniczego.

## <a name="crebarctrlsettooltips"></a><a name="settooltips"></a> Korzystanie CReBarCtrl:: setetykietki narzędzi

Kojarzy formant etykietki narzędzia z kontrolką paska pomocniczego.

```cpp
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>Parametry

*pToolTip*<br/>
Wskaźnik do obiektu [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)

### <a name="remarks"></a>Uwagi

`CToolTipCtrl`Gdy wszystko będzie gotowe, należy zniszczyć obiekt.

## <a name="crebarctrlsetwindowtheme"></a><a name="setwindowtheme"></a> Korzystanie CReBarCtrl:: SetWindowTheme

Ustawia styl wizualizacji formantu paska pomocniczego.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>Parametry

*pszSubAppName*<br/>
Wskaźnik do ciągu Unicode, który zawiera styl wizualizacji paska pomocniczego do ustawienia.

### <a name="return-value"></a>Wartość zwracana

Wartość zwracana nie jest używana.

### <a name="remarks"></a>Uwagi

Ta funkcja członkowska emuluje funkcjonalność komunikatu [RB_SETWINDOWTHEME](/windows/win32/Controls/rb-setwindowtheme) , zgodnie z opisem w Windows SDK.

## <a name="crebarctrlshowband"></a><a name="showband"></a> Korzystanie CReBarCtrl:: ShowBand

Implementuje zachowanie [RB_SHOWBAND](/windows/win32/Controls/rb-showband)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>Parametry

*uBand*<br/>
Indeks (liczony od zera) pasma w kontrolce paska pomocniczego.

*fShow*<br/>
Wskazuje, czy pasmo ma być pokazywany czy ukryty. Jeśli ta wartość jest RÓWNa TRUE, zostanie wyświetlona Grupa. W przeciwnym razie pasek zostanie ukryty.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

## <a name="crebarctrlsizetorect"></a><a name="sizetorect"></a> Korzystanie CReBarCtrl:: SizeToRect

Implementuje zachowanie [RB_SIZETORECT](/windows/win32/Controls/rb-sizetorect)komunikatu Win32, zgodnie z opisem w Windows SDK.

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>Parametry

*cinania*<br/>
Odwołanie do obiektu [CRect](../../atl-mfc-shared/reference/crect-class.md) , który określa prostokąt, do którego należy określić rozmiar kontrolki paska pomocniczego.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli pomyślne; w przeciwnym razie zero.

### <a name="remarks"></a>Uwagi

Należy zauważyć, że ta funkcja członkowska używa `CRect` obiektu jako parametru, a nie `RECT` struktury.

## <a name="see-also"></a>Zobacz też

[Klasa CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)

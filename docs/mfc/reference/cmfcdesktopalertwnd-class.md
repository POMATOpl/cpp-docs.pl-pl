---
description: 'Dowiedz się więcej na temat: Klasa CMFCDesktopAlertWnd'
title: Klasa CMFCDesktopAlertWnd
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
ms.openlocfilehash: 45b75bdbd24a88a7eacff124bb07ac81e7703c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330097"
---
# <a name="cmfcdesktopalertwnd-class"></a>Klasa CMFCDesktopAlertWnd

`CMFCDesktopAlertWnd`Klasa implementuje funkcje niemodalnego okna dialogowego, które pojawia się na ekranie, aby poinformować użytkownika o zdarzeniu.

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

## <a name="syntax"></a>Składnia

```
class CMFCDesktopAlertWnd : public CWnd
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCDesktopAlertWnd:: Create](#create)|Tworzy i inicjuje okno alertu pulpitu.|
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|Zwraca szybkość animacji.|
|[CMFCDesktopAlertWnd:: getanimationtype](#getanimationtype)|Zwraca typ animacji.|
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|Zwraca limit czasu Autozamykania.|
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|Zwraca wysokość podpisu.|
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|Zwraca ostatnią poprawną pozycję okna alertu pulpitu na ekranie.|
|[CMFCDesktopAlertWnd:: gettransparent](#gettransparency)|Zwraca poziom przezroczystości.|
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|Określa, czy okno alertu pulpitu jest wyświetlane z niewielkim podpisem.|
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|Wywoływane przez platformę, gdy użytkownik kliknie przycisk link znajdujący się w menu alertu na pulpicie.|
|[CMFCDesktopAlertWnd:: OnCommand](#oncommand)|Struktura wywołuje tę funkcję elementu członkowskiego, gdy użytkownik wybierze element z menu, gdy kontrolka podrzędna wysyła komunikat z powiadomieniem lub gdy zostanie przetłumaczone naciśnięcie klawisza skrótu. (Przesłania [CWnd:: OnCommand](../../mfc/reference/cwnd-class.md#oncommand).)|
|[CMFCDesktopAlertWnd:: OnDraw](#ondraw)||
|[CMFCDesktopAlertWnd::P rocessCommand](#processcommand)||
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|Ustawia nową szybkość animacji.|
|[CMFCDesktopAlertWnd:: SetAnimationType](#setanimationtype)|Ustawia typ animacji.|
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|Ustawia limit czasu Autozamykania.|
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|Przełącza między małymi a zwykłymi napisami.|
|[CMFCDesktopAlertWnd:: SetTransparency](#settransparency)|Ustawia poziom przezroczystości.|

## <a name="remarks"></a>Uwagi

Okno alertu pulpitu może być przezroczyste, może być wyświetlane z efektami animacji i może zniknąć (po określonym opóźnieniu lub po odrzuceniu przez użytkownika przez kliknięcie przycisku Zamknij).

Okno alertu pulpitu może również zawierać domyślne okno dialogowe, które z kolei zawiera ikonę, tekst komunikatu (etykietę) i link. Alternatywnie okno alertu pulpitu może zawierać niestandardowe okno dialogowe z zasobów aplikacji.

Okno alertu pulpitu jest tworzone w dwóch krokach. Najpierw Wywołaj konstruktora w celu skonstruowania `CMFCDesktopAlertWnd` obiektu. Następnie wywołaj funkcję [CMFCDesktopAlertWnd:: Create](#create) member, aby utworzyć okno i dołączyć je do `CMFCDesktopAlertWnd` obiektu.

`CMFCDesktopAlertWnd`Obiekt tworzy specjalne podrzędne okno dialogowe, które wypełnia obszar klienta okna alertu pulpitu. To okno dialogowe jest właścicielem wszystkich formantów, które są umieszczone na nim.

Aby wyświetlić niestandardowe okno dialogowe w oknie podręcznym, wykonaj następujące kroki:

1. Utwórz klasę z `CMFCDesktopAlertDialog` .

1. Utwórz podrzędny szablon okna dialogowego w zasobach.

1. Wywołanie [CMFCDesktopAlertWnd:: Create](#create) przy użyciu identyfikatora zasobu szablonu okna dialogowego i wskaźnika do informacji o klasie środowiska uruchomieniowego klasy pochodnej.

1. Zaprogramowanie niestandardowego okna dialogowego do obsługi wszystkich powiadomień pochodzących z formantów hostowanych lub programowe kontrolki obsługiwane do obsługi tych powiadomień bezpośrednio.

Użyj następujących funkcji, aby kontrolować zachowanie okna alertu pulpitu:

- Ustaw typ animacji przez wywołanie [CMFCDesktopAlertWnd:: SetAnimationType](#setanimationtype). Prawidłowe opcje to: unfold, slajd i zanik.

- Ustaw szybkość klatek animacji przez wywołanie [CMFCDesktopAlertWnd:: SetAnimationSpeed](#setanimationspeed).

- Ustaw poziom przezroczystości przez wywołanie [CMFCDesktopAlertWnd:: SetTransparency](#settransparency).

- Zmień rozmiar podpisu na mały przez wywołanie [CMFCDesktopAlertWnd:: SetSmallCaption](#setsmallcaption). Mały podpis ma wysokość 7 pikseli.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCDesktopAlertWnd` klasie w celu skonfigurowania `CMFCDesktopAlertWnd` obiektu. W przykładzie pokazano, jak ustawić typ animacji, ustawić przezroczystość okna podręcznego, określić, że okno alertu wyświetla mały podpis i ustawić czas, jaki upłynie przed automatycznym zamknięciem okna alertu. W przykładzie pokazano również, jak utworzyć i zainicjować okno alertu pulpitu. Ten fragment kodu jest częścią [przykładu pokazu alertu na pulpicie](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxDesktopAlertWnd. h

## <a name="cmfcdesktopalertwndcreate"></a><a name="create"></a> CMFCDesktopAlertWnd:: Create

Tworzy i inicjuje okno alertu pulpitu.

```
virtual BOOL Create(
    CWnd* pWndOwner,
    UINT uiDlgResID,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1),
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

virtual BOOL Create(
    CWnd* pWndOwner,
    CMFCDesktopAlertWndInfo& params,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1));
```

### <a name="parameters"></a>Parametry

*pWndOwner*<br/>
[in. out] Określa właściciela okna alertu. Ten właściciel otrzyma następnie wszystkie powiadomienia dla okna alertu pulpitu. Ta wartość nie może być RÓWNa NULL.

*uiDlgResID*<br/>
podczas Określa identyfikator zasobu okna alertu.

*hMenu*<br/>
podczas Określa menu, które jest wyświetlane, gdy użytkownik kliknie przycisk menu. Jeśli wartość jest równa NULL, przycisk menu nie jest wyświetlany.

*ptPos*<br/>
podczas Określa początkową pozycję, w której wyświetlane jest okno alertu przy użyciu współrzędnych ekranu. Jeśli ten parametr ma wartość (-1,-1), okno alertu jest wyświetlane w prawym dolnym rogu ekranu.

*pRTIDlgBar*<br/>
podczas Informacje o klasie środowiska uruchomieniowego dla niestandardowej klasy okien dialogowych, która obejmuje obszar klienta okna alertu.

*params*<br/>
podczas Określa parametry, które są używane do tworzenia okna alertu.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli okno alertu zostało utworzone pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby utworzyć okno alertu. Obszar klienta okna alertu zawiera podrzędne okno dialogowe, które obsługuje wszystkie kontrolki, które są wyświetlane użytkownikowi.

Pierwsze Przeciążenie metody tworzy okno alertu zawierające podrzędne okno dialogowe, które jest ładowane z zasobów aplikacji. Pierwsze Przeciążenie metody może również określać informacje o klasie środowiska uruchomieniowego dla niestandardowej klasy okna dialogowego.

Drugie Przeciążenie metody tworzy okno alertu, które zawiera domyślne kontrolki. Możesz określić, które kontrolki mają być wyświetlane, modyfikując [klasę CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md).

## <a name="cmfcdesktopalertwndgetanimationspeed"></a><a name="getanimationspeed"></a> CMFCDesktopAlertWnd::GetAnimationSpeed

Zwraca szybkość animacji.

```
UINT GetAnimationSpeed() const;
```

### <a name="return-value"></a>Wartość zwracana

Szybkość animacji okna alertu (w milisekundach).

### <a name="remarks"></a>Uwagi

Szybkość animacji opisuje, jak szybko otwiera się i zamyka okno alertu.

## <a name="cmfcdesktopalertwndgetanimationtype"></a><a name="getanimationtype"></a> CMFCDesktopAlertWnd:: getanimationtype

Zwraca typ animacji.

```
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```

### <a name="return-value"></a>Wartość zwracana

Jeden z następujących typów animacji:

- NO_ANIMATION

- UNFOLD

- Odtwarzanie

- ZNIK

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndgetautoclosetime"></a><a name="getautoclosetime"></a> CMFCDesktopAlertWnd::GetAutoCloseTime

Zwraca limit czasu Autozamykania.

```
int GetAutoCloseTime() const;
```

### <a name="return-value"></a>Wartość zwracana

Czas (w milisekundach), po którym okno alertu zostanie automatycznie zamknięte.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby określić, ile czasu powinno upłynąć, zanim okno alertu zostanie automatycznie zamknięte.

## <a name="cmfcdesktopalertwndgetcaptionheight"></a><a name="getcaptionheight"></a> CMFCDesktopAlertWnd::GetCaptionHeight

Zwraca wysokość podpisu.

```
virtual int GetCaptionHeight();
```

### <a name="return-value"></a>Wartość zwracana

Wysokość (w pikselach) podpisu.

### <a name="remarks"></a>Uwagi

Ta metoda może zostać przesłonięta w klasie pochodnej. Domyślna implementacja: zwraca niewielką wartość wysokości napisu (7 pikseli), jeśli okno podręczne powinno wyświetlać mały podpis lub wartość uzyskaną z funkcji interfejsu API systemu Windows `GetSystemMetrics(SM_CYSMCAPTION)` .

## <a name="cmfcdesktopalertwndgetlastpos"></a><a name="getlastpos"></a> CMFCDesktopAlertWnd::GetLastPos

Zwraca ostatnią pozycję okna alertu pulpitu na ekranie.

```
CPoint GetLastPos() const;
```

### <a name="return-value"></a>Wartość zwracana

Punkt, we współrzędnych ekranu.

### <a name="remarks"></a>Uwagi

Ta metoda zwraca ostatnią poprawną pozycję okna alertu na ekranie.

## <a name="cmfcdesktopalertwndgettransparency"></a><a name="gettransparency"></a> CMFCDesktopAlertWnd:: gettransparent

Zwraca poziom przezroczystości.

```
BYTE GetTransparency() const;
```

### <a name="return-value"></a>Wartość zwracana

Poziom przezroczystości z zakresu od 0 do 255 włącznie. Im większa wartość, tym bardziej nieprzezroczyste okno.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby pobrać bieżący poziom przezroczystości okna alertu.

## <a name="cmfcdesktopalertwndhassmallcaption"></a><a name="hassmallcaption"></a> CMFCDesktopAlertWnd::HasSmallCaption

Określa, czy okno alertu pulpitu ma mały podpis, czy zwykły podpis.

```
BOOL HasSmallCaption() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli okno podręczne jest wyświetlane z małym podpisem; FAŁSZ, jeśli okno podręczne jest wyświetlane z podpisem regularnym.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby określić, czy okno podręczne ma mały podpis, czy zwykły podpis. Domyślnie mały podpis ma wysokość 7 pikseli. Możesz uzyskać wysokość stałego rozmiaru podpisu, wywołując funkcję interfejsu API systemu Windows `GetSystemMetrics(SM_CYCAPTION)` .

## <a name="cmfcdesktopalertwndonbeforeshow"></a><a name="onbeforeshow"></a> CMFCDesktopAlertWnd::OnBeforeShow

```
virtual BOOL OnBeforeShow(CPoint&);
```

### <a name="parameters"></a>Parametry

podczas *CPoint&*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcdesktopalertwndonclicklinkbutton"></a><a name="onclicklinkbutton"></a> CMFCDesktopAlertWnd::OnClickLinkButton

Wywoływane przez platformę, gdy użytkownik kliknie przycisk link znajdujący się w menu alertu na pulpicie.

```
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```

### <a name="parameters"></a>Parametry

*uiCmdID*<br/>
podczas Ten parametr nie jest używany.

### <a name="return-value"></a>Wartość zwracana

Zawsze FALSE.

### <a name="remarks"></a>Uwagi

Zastąp tę metodę w klasie pochodnej, jeśli chcesz otrzymywać powiadomienia, gdy użytkownik kliknie link w oknie alertu.

## <a name="cmfcdesktopalertwndoncommand"></a><a name="oncommand"></a> CMFCDesktopAlertWnd:: OnCommand

```
virtual BOOL OnCommand(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametry

podczas *wParam*<br/>

podczas *lParam*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcdesktopalertwndondraw"></a><a name="ondraw"></a> CMFCDesktopAlertWnd:: OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametry

podczas *kontroler PDC*<br/>

### <a name="remarks"></a>Uwagi

## <a name="cmfcdesktopalertwndprocesscommand"></a><a name="processcommand"></a> CMFCDesktopAlertWnd::P rocessCommand

```
BOOL ProcessCommand(HWND hwnd);
```

### <a name="parameters"></a>Parametry

podczas *Właściwość HWND*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcdesktopalertwndsetanimationspeed"></a><a name="setanimationspeed"></a> CMFCDesktopAlertWnd::SetAnimationSpeed

Ustawia nową szybkość animacji.

```cpp
void SetAnimationSpeed(UINT nSpeed);
```

### <a name="parameters"></a>Parametry

*nSpeed*<br/>
podczas Określa nową szybkość animacji w milisekundach.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby ustawić szybkość animacji okna alertu. Domyślna szybkość animacji wynosi 30 milisekund.

## <a name="cmfcdesktopalertwndsetanimationtype"></a><a name="setanimationtype"></a> CMFCDesktopAlertWnd:: SetAnimationType

Ustawia typ animacji.

```cpp
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```

### <a name="parameters"></a>Parametry

*Wprowadź*<br/>
podczas Określa typ animacji.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby ustawić typ animacji. Można określić jedną z następujących wartości:

- NO_ANIMATION

- UNFOLD

- Odtwarzanie

- ZNIK

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndsetautoclosetime"></a><a name="setautoclosetime"></a> CMFCDesktopAlertWnd::SetAutoCloseTime

Ustawia limit czasu Autozamykania.

```cpp
void SetAutoCloseTime(int nTime);
```

### <a name="parameters"></a>Parametry

*nTime*<br/>
podczas Czas (w milisekundach), który upłynął przed automatycznym zamknięciem okna alertu.

### <a name="remarks"></a>Uwagi

Okno alertu jest automatycznie zamykane po określonym czasie, jeśli użytkownik nie współdziała z oknem.

## <a name="cmfcdesktopalertwndsetsmallcaption"></a><a name="setsmallcaption"></a> CMFCDesktopAlertWnd::SetSmallCaption

Przełącza między napisami o małym i regularnym rozmiarze.

```cpp
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```

### <a name="parameters"></a>Parametry

*bSmallCaption*<br/>
podczas Wartość TRUE, aby określić, że okno alertu wyświetla mały podpis; w przeciwnym razie, FAŁSZ, aby określić, że okno alertu Wyświetla zwykły podpis.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, aby wyświetlić napis o małym lub regularnym rozmiarze. Domyślnie mały podpis ma wysokość 7 pikseli. Możesz uzyskać rozmiar zwykłego podpisu, wywołując funkcję interfejsu API systemu Windows `GetSystemMetrics(SM_CYCAPTION)` .

## <a name="cmfcdesktopalertwndsettransparency"></a><a name="settransparency"></a> CMFCDesktopAlertWnd:: SetTransparency

Ustawia poziom przezroczystości okna podręcznego.

```cpp
void SetTransparency(BYTE nTransparency);
```

### <a name="parameters"></a>Parametry

*nTransparency*<br/>
podczas Określa poziom przezroczystości. Ta wartość musi należeć do przedziału od 0 do 255 włącznie. Im większa wartość, tym bardziej nieprzezroczyste okno.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby ustawić poziom przezroczystości okna podręcznego.

## <a name="cmfcdesktopalertwndgetdialogsize"></a><a name="getdialogsize"></a> CMFCDesktopAlertWnd::GetDialogSize

```
virtual CSize GetDialogSize();
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[Klasa CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)<br/>
[Klasa CWnd](../../mfc/reference/cwnd-class.md)

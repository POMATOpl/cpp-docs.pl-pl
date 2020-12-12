---
description: 'Dowiedz się więcej na temat: Klasa CMFCCaptionBar'
title: Klasa CMFCCaptionBar
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
ms.openlocfilehash: a5dd5f968c52268935b6176115e8723a9d82e8a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327738"
---
# <a name="cmfccaptionbar-class"></a>Klasa CMFCCaptionBar

`CMFCCaptionBar`Obiekt jest paskiem sterowania, który może wyświetlać trzy elementy: przycisk, etykietę tekstową i mapę bitową. Może wyświetlać tylko jeden element każdego typu naraz. Każdy element można wyrównać do lewej lub prawej krawędzi kontrolki lub do środka. Do górnego i dolnego obramowania paska podpisu można również zastosować styl płaski lub 3W.

## <a name="syntax"></a>Składnia

```
class CMFCCaptionBar : public CPane
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCCaptionBar:: Create](#create)|Tworzy kontrolkę pasek podpisu i dołącza ją do `CMFCCaptionBar` obiektu.|
|[CMFCCaptionBar::D oesAllowDynInsertBefore](#doesallowdyninsertbefore)|Wskazuje, czy można dynamicznie wstawiać inne okienka między paskiem podpisu i jego ramką nadrzędną. (Przesłania [CBasePane::D oesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCCaptionBar::EnableButton](#enablebutton)|Włącza lub wyłącza przycisk na pasku podpisu.|
|[CMFCCaptionBar:: getalignment](#getalignment)|Zwraca wyrównanie określonego elementu.|
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Zwraca rozmiar obramowania paska podpisu.|
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Pobiera prostokąt związany z przyciskiem na pasku podpisu.|
|[CMFCCaptionBar:: GetMargin](#getmargin)|Zwraca odległość między krawędzią elementów paska podpisu i krawędzią kontrolki paska tytułu.|
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Określa, czy pasek podpisu znajduje się w trybie paska komunikatów.|
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Usuwa obraz mapy bitowej z paska podpisu.|
|[CMFCCaptionBar::RemoveButton](#removebutton)|Usuwa przycisk z paska podpisu.|
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Usuwa ikonę z paska podpisu.|
|[CMFCCaptionBar::RemoveText](#removetext)|Usuwa etykietę tekstową z paska podpisu.|
|[CMFCCaptionBar:: setmap](#setbitmap)|Ustawia obraz mapy bitowej na pasku podpisu.|
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Ustawia rozmiar obramowania paska podpisu.|
|[CMFCCaptionBar:: SetButton](#setbutton)|Ustawia przycisk dla paska podpisu.|
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|Określa, czy przycisk zostanie naciśnięty.|
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Ustawia etykietkę narzędzia dla przycisku.|
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Ustawia styl obramowania paska podpisu.|
|[CMFCCaptionBar:: SetIcon](#seticon)|Ustawia ikonę dla paska podpisu.|
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Ustawia etykietkę narzędzia dla obrazu na pasku podpisu.|
|[CMFCCaptionBar:: SetMargin](#setmargin)|Ustawia odległość między krawędzią elementu paska podpisu i krawędzią kontrolki paska tytułu.|
|[CMFCCaptionBar::SetText](#settext)|Ustawia etykietę tekstową paska podpisu.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|Wywoływane przez platformę, aby wypełnić tło paska podpisu.|
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|Wywoływane przez platformę, by narysować obramowanie paska podpisu.|
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|Wywoływane przez platformę, aby narysować przycisk paska podpisu.|
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|Wywoływane przez platformę, by narysować obraz paska podpisu.|
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|Wywoływane przez platformę, by narysować tekst paska podpisu.|

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMFCCaptionBar:: m_clrBarBackground](#m_clrbarbackground)|Kolor tła paska podpisu.|
|[CMFCCaptionBar:: m_clrBarBorder](#m_clrbarborder)|Kolor obramowania paska podpisu.|
|[CMFCCaptionBar:: m_clrBarText](#m_clrbartext)|Kolor tekstu paska podpisu.|

## <a name="remarks"></a>Uwagi

Aby utworzyć pasek podpisu, wykonaj następujące kroki:

1. Konstruowanie `CMFCCaptionBar` obiektu. Zwykle pasek podpisu można dodać do klasy okna ramowego.

1. Wywołaj metodę [CMFCCaptionBar:: Create](#create) , aby utworzyć kontrolkę pasek podpisu i dołączyć ją do `CMFCCaptionBar` obiektu.

1. Call [CMFCCaptionBar:: SetButton](#setbutton), [CMFCCaptionBar:: SetText](#settext), [CMFCCaptionBar:: SetIcon](#seticon)i [CMFCCaptionBar:: setmap](#setbitmap) , aby ustawić elementy paska podpisu.

Po ustawieniu elementu Button, należy przypisać do przycisku identyfikator polecenia. Gdy użytkownik kliknie przycisk, pasek podpisu kieruje WM_COMMAND wiadomości, które mają ten identyfikator do okna ramki nadrzędnej.

Pasek podpisu może również współpracować z trybem paska komunikatów, który emuluje pasek komunikatów, który pojawia się w aplikacjach Microsoft Office 2007. W trybie paska komunikatów na pasku podpisu jest wyświetlana mapa bitowa, komunikat i przycisk (co powoduje zazwyczaj otwarcie okna dialogowego). Etykietkę narzędzia można przypisać do mapy bitowej.

Aby włączyć tryb paska komunikatów, wywołaj [CMFCCaptionBar:: Create](#create) i ustaw czwarty parametr (bIsMessageBarMode) na wartość true.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCCaptionBar` klasie. W przykładzie pokazano, jak utworzyć kontrolkę pasek podpisu, ustawić obramowanie 3W paska podpisu, ustawić odległość, w pikselach, między krawędzią elementów paska podpisu i krawędzią kontrolki pasek podpisu, ustawić przycisk dla paska podpisu, ustawić etykietkę narzędzia dla przycisku, ustawić etykietę tekstową na pasku podpisu, ustawić obraz mapy bitowej na pasku podpisu i ustaw etykietkę narzędzia dla obrazu na pasku podpisu. Ten fragment kodu jest częścią [przykładu demonstracyjnego pakietu MS Office 2007](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcaptionbar. h

## <a name="cmfccaptionbarcreate"></a><a name="create"></a> CMFCCaptionBar:: Create

Tworzy kontrolkę pasek podpisu i dołącza ją do `CMFCCaptionBar` obiektu.

```
BOOL Create(
    DWORD dwStyle,
    CWnd* pParentWnd,
    UINT uID,
    int nHeight=-1,
    BOOL bIsMessageBarMode=FALSE);
```

### <a name="parameters"></a>Parametry

*dwStyle*<br/>
Logiczne lub kombinacja stylów paska podpisu.

*pParentWnd*<br/>
Okno nadrzędne kontrolki pasek podpisu.

*uID*<br/>
Identyfikator kontrolki paska tytułu.

*nHeight*<br/>
Wysokość kontrolki paska podpisu (w pikselach). Jeśli wartość to-1, wysokość jest obliczana zgodnie z wysokością ikony, tekstem i przyciskiem wyświetlanym przez kontrolkę pasek podpisu.

*bIsMessageBarMode*<br/>
Ma wartość TRUE, jeśli pasek podpisu znajduje się w trybie paska komunikatów. W przeciwnym razie zwraca wartość FALSE.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, Jeśli kontrolka paska podpisu została utworzona pomyślnie. W przeciwnym razie zwraca wartość FALSE.

### <a name="remarks"></a>Uwagi

Obiekt jest konstruowany `CMFCCaptionBar` w dwóch krokach. Najpierw należy wywołać konstruktora, a następnie wywołać `Create` metodę, która tworzy formant systemu Windows i dołącza go do `CMFCCaptionBar` obiektu.

## <a name="cmfccaptionbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCCaptionBar::D oesAllowDynInsertBefore

Wskazuje, czy można dynamicznie wstawiać inne okienka między paskiem podpisu i jego ramką nadrzędną.

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość FALSE, chyba że zostanie zastąpiona.

### <a name="remarks"></a>Uwagi

## <a name="cmfccaptionbarenablebutton"></a><a name="enablebutton"></a> CMFCCaptionBar::EnableButton

Włącza lub wyłącza przycisk na pasku podpisu.

```cpp
void EnableButton(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*bEnable*<br/>
podczas Wartość TRUE, aby włączyć przycisk, wartość FALSE powoduje wyłączenie przycisku.

## <a name="cmfccaptionbargetalignment"></a><a name="getalignment"></a> CMFCCaptionBar:: getalignment

Zwraca wyrównanie określonego elementu.

```
BarElementAlignment GetAlignment(BarElement elem);
```

### <a name="parameters"></a>Parametry

*elem*<br/>
podczas Element paska podpisu, dla którego ma zostać pobrane wyrównanie.

### <a name="return-value"></a>Wartość zwracana

Wyrównanie elementu, takiego jak przycisk, mapa bitowa, tekst lub ikona.

### <a name="remarks"></a>Uwagi

Wyrównanie elementu może być jedną z następujących wartości:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbargetbordersize"></a><a name="getbordersize"></a> CMFCCaptionBar::GetBorderSize

Zwraca rozmiar obramowania paska podpisu.

```
int GetBorderSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Rozmiar obramowania (w pikselach).

## <a name="cmfccaptionbargetbuttonrect"></a><a name="getbuttonrect"></a> CMFCCaptionBar::GetButtonRect

Pobiera prostokąt związany z przyciskiem na pasku podpisu.

```
CRect GetButtonRect() const;
```

### <a name="return-value"></a>Wartość zwracana

`CRect`Obiekt, który zawiera współrzędne prostokąta granicy przycisku na pasku podpisu.

## <a name="cmfccaptionbargetmargin"></a><a name="getmargin"></a> CMFCCaptionBar:: GetMargin

Zwraca odległość między krawędzią elementów paska podpisu i krawędzią kontrolki paska tytułu.

```
int GetMargin() const;
```

### <a name="return-value"></a>Wartość zwracana

Odległość, w pikselach, między krawędzią elementów paska podpisu i krawędzią kontrolki paska tytułu.

## <a name="cmfccaptionbarismessagebarmode"></a><a name="ismessagebarmode"></a> CMFCCaptionBar::IsMessageBarMode

Określa, czy pasek podpisu znajduje się w trybie paska komunikatów.

```
BOOL IsMessageBarMode() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli pasek podpisu znajduje się w trybie paska komunikatów. W przeciwnym razie zwraca wartość FALSE.

### <a name="remarks"></a>Uwagi

W trybie paska komunikatów na pasku podpisu zostanie wyświetlony obraz z etykietką, tekstem wiadomości i przyciskiem.

## <a name="cmfccaptionbarm_clrbarbackground"></a><a name="m_clrbarbackground"></a> CMFCCaptionBar:: m_clrBarBackground

Kolor tła paska podpisu.

```
COLORREF m_clrBarBackground
```

## <a name="cmfccaptionbarm_clrbarborder"></a><a name="m_clrbarborder"></a> CMFCCaptionBar:: m_clrBarBorder

Kolor obramowania paska podpisu.

```
COLORREF m_clrBarBorder
```

## <a name="cmfccaptionbarm_clrbartext"></a><a name="m_clrbartext"></a> CMFCCaptionBar:: m_clrBarText

Kolor tekstu paska podpisu.

```
COLORREF m_clrBarText
```

## <a name="cmfccaptionbarondrawbackground"></a><a name="ondrawbackground"></a> CMFCCaptionBar::OnDrawBackground

Wywoływane przez platformę, aby wypełnić tło paska podpisu.

```
virtual void OnDrawBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia na pasku podpisu.

*cinania*<br/>
podczas Prostokąt ograniczający do wypełnienia.

### <a name="remarks"></a>Uwagi

`OnDrawBackground`Metoda jest wywoływana, gdy tło paska podpisu ma zostać wypełnione. Domyślna implementacja wypełnia tło przy użyciu koloru [CMFCCaptionBar:: m_clrBarBackground](#m_clrbarbackground) .

Zastąp tę metodę w `CMFCCaptionBar` klasie pochodnej, aby dostosować wygląd paska podpisu.

## <a name="cmfccaptionbarondrawborder"></a><a name="ondrawborder"></a> CMFCCaptionBar::OnDrawBorder

Wywoływane przez platformę, by narysować obramowanie paska podpisu.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Kontekst urządzenia, który jest używany do wyświetlania obramowań.

*cinania*<br/>
podczas Prostokąt ograniczający.

### <a name="remarks"></a>Uwagi

Domyślnie obramowanie ma styl płaski.

Zastąp tę metodę w `CMFCCaptionBar` klasie pochodnej, aby dostosować wygląd obramowania paska podpisu.

## <a name="cmfccaptionbarondrawbutton"></a><a name="ondrawbutton"></a> CMFCCaptionBar::OnDrawButton

Wywoływane przez platformę, aby narysować przycisk paska podpisu.

```
virtual void OnDrawButton(
    CDC* pDC,
    CRect rect,
    const CString& strButton,
    BOOL bEnabled);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia, który jest używany do wyświetlania przycisku.

*cinania*<br/>
podczas Prostokąt ograniczający przycisku.

*strButton*<br/>
podczas Etykieta tekstu przycisku.

*bEnabled*<br/>
podczas Ma wartość TRUE, jeśli przycisk jest włączony; W przeciwnym razie zwraca wartość FALSE.

### <a name="remarks"></a>Uwagi

Zastąp tę metodę w `CMFCCaptionBar` klasie pochodnej, aby dostosować wygląd przycisku paska podpisu.

## <a name="cmfccaptionbarondrawimage"></a><a name="ondrawimage"></a> CMFCCaptionBar::OnDrawImage

Wywoływane przez platformę, by narysować obraz paska podpisu.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia, który jest używany do wyświetlania obrazu.

*cinania*<br/>
podczas Określa prostokąt ograniczenia obrazu.

### <a name="remarks"></a>Uwagi

Zastąp tę metodę w `CMFCCaptionBar` klasie pochodnej, aby dostosować wygląd obrazu.

## <a name="cmfccaptionbarondrawtext"></a><a name="ondrawtext"></a> CMFCCaptionBar::OnDrawText

Wywoływane przez platformę, by narysować tekst paska podpisu.

```
virtual void OnDrawText(
    CDC* pDC,
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia, który jest używany do wyświetlania przycisku.

*cinania*<br/>
podczas Prostokąt ograniczający tekst.

*strText*<br/>
podczas Ciąg tekstowy do wyświetlenia.

### <a name="remarks"></a>Uwagi

Domyślna implementacja Wyświetla tekst przy użyciu `CDC::DrawText` i [CMFCCaptionBar:: m_clrBarText](#m_clrbartext) Color.

Zastąp tę metodę w `CMFCCaptionBar` klasie pochodnej, aby dostosować wygląd tekstu paska podpisu.

## <a name="cmfccaptionbarremovebitmap"></a><a name="removebitmap"></a> CMFCCaptionBar::RemoveBitmap

Usuwa obraz mapy bitowej z paska podpisu.

```cpp
void RemoveBitmap();
```

## <a name="cmfccaptionbarremovebutton"></a><a name="removebutton"></a> CMFCCaptionBar::RemoveButton

Usuwa przycisk z paska podpisu.

```cpp
void RemoveButton();
```

### <a name="remarks"></a>Uwagi

Układ elementów paska podpisu jest dostosowywany automatycznie.

## <a name="cmfccaptionbarremoveicon"></a><a name="removeicon"></a> CMFCCaptionBar::RemoveIcon

Usuwa ikonę z paska podpisu.

```cpp
void RemoveIcon();
```

## <a name="cmfccaptionbarremovetext"></a><a name="removetext"></a> CMFCCaptionBar::RemoveText

Usuwa etykietę tekstową z paska podpisu.

```cpp
void RemoveText();
```

## <a name="cmfccaptionbarsetbitmap"></a><a name="setbitmap"></a> CMFCCaptionBar:: setmap

Ustawia obraz mapy bitowej na pasku podpisu.

```cpp
void SetBitmap(
    HBITMAP hBitmap,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

void SetBitmap(
    UINT uiBmpResID,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Parametry

*hBitmap*<br/>
podczas Uchwyt do mapy bitowej do ustawienia.

*clrTransparent*<br/>
podczas Wartość RGB, która określa przezroczysty kolor mapy bitowej.

*bStretch*<br/>
podczas W przypadku opcji TRUE Mapa bitowa jest rozciągana, jeśli nie pasuje do prostokąta z obwiednią obrazu. W przeciwnym razie Mapa bitowa nie jest rozciągana.

*bmpAlignment*<br/>
podczas Wyrównanie mapy bitowej.

### <a name="remarks"></a>Uwagi

Ta metoda służy do ustawiania mapy bitowej na pasku podpisu.

Poprzednia mapa bitowa zostanie zniszczona automatycznie. Jeśli na pasku podpisu zostanie wyświetlona ikona, ponieważ wywołana została Metoda [CMFCCaptionBar:: SetIcon](#seticon) , mapa bitowa nie zostanie wyświetlona, chyba że zostanie usunięta ikona przez wywołanie [CMFCCaptionBar:: RemoveIcon](#removeicon).

Mapa bitowa jest wyrównana zgodnie z parametrem *bmpAlignment* .  Ten parametr może mieć jedną z następujących `BarElementAlignment` wartości:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetbordersize"></a><a name="setbordersize"></a> CMFCCaptionBar::SetBorderSize

Ustawia rozmiar obramowania paska podpisu.

```cpp
void SetBorderSize(int nSize);
```

### <a name="parameters"></a>Parametry

*nSize*<br/>
podczas Nowy rozmiar obramowania paska tytułu (w pikselach).

## <a name="cmfccaptionbarsetbutton"></a><a name="setbutton"></a> CMFCCaptionBar:: SetButton

Ustawia przycisk dla paska podpisu.

```cpp
void SetButton(
    LPCTSTR lpszLabel,
    UINT uiCmdUI,
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,
    BOOL bHasDropDownArrow=TRUE);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
Etykieta polecenia przycisku.

*uiCmdUI*<br/>
Identyfikator polecenia przycisku.

*btnAlignmnet*<br/>
Wyrównanie przycisku.

*bHasDropDownArrow*<br/>
TRUE, jeśli przycisk wyświetla strzałkę listy rozwijanej, w przeciwnym razie FALSE.

## <a name="cmfccaptionbarsetbuttonpressed"></a><a name="setbuttonpressed"></a> CMFCCaptionBar::SetButtonPressed

Określa, czy przycisk zostanie naciśnięty.

```cpp
void SetButtonPressed(BOOL bPresed=TRUE);
```

### <a name="parameters"></a>Parametry

*bPresed*<br/>
TRUE, jeśli przycisk utrzymuje swój stan naciśniętego, FAŁSZ w przeciwnym razie.

## <a name="cmfccaptionbarsetbuttontooltip"></a><a name="setbuttontooltip"></a> CMFCCaptionBar::SetButtonToolTip

Ustawia etykietkę narzędzia dla przycisku.

```cpp
void SetButtonToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Parametry

*lpszToolTip*<br/>
podczas Etykieta etykietki narzędzia.

*lpszDescription*<br/>
podczas Opis etykietki narzędzia.

## <a name="cmfccaptionbarsetflatborder"></a><a name="setflatborder"></a> CMFCCaptionBar::SetFlatBorder

Ustawia styl obramowania paska podpisu.

```cpp
void SetFlatBorder(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Parametry

*bFlat*<br/>
podczas PRAWDA, jeśli obramowanie paska podpisu jest płaskie. FAŁSZ, jeśli obramowanie jest 3W.

## <a name="cmfccaptionbarseticon"></a><a name="seticon"></a> CMFCCaptionBar:: SetIcon

Ustawia ikonę dla paska podpisu.

```cpp
void SetIcon(
    HICON hIcon,
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Parametry

*hIcon*<br/>
podczas Uchwyt do ikony, która ma zostać ustawiona.

*iconAlignment*<br/>
podczas Wyrównanie ikony.

### <a name="remarks"></a>Uwagi

Paski podpisu mogą wyświetlać ikony lub mapy bitowe. Zobacz [CMFCCaptionBar:: Setmapa bitowa](#setbitmap) , aby dowiedzieć się, jak wyświetlić mapę bitową. Jeśli ustawisz zarówno ikonę, jak i mapę bitową, ikona jest zawsze wyświetlana. Wywołaj [CMFCCaptionBar:: RemoveIcon](#removeicon) , aby usunąć ikonę z paska podpisu.

Ikona jest wyrównana zgodnie z parametrem *iconAlignment* . Może to być jedna z następujących `BarElementAlignment` wartości:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetimagetooltip"></a><a name="setimagetooltip"></a> CMFCCaptionBar::SetImageToolTip

Ustawia etykietkę narzędzia dla obrazu na pasku podpisu.

```cpp
void SetImageToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>Parametry

*lpszToolTip*<br/>
podczas Tekst etykietki narzędzia.

*lpszDescription*<br/>
podczas Opis etykietki narzędzia.

## <a name="cmfccaptionbarsetmargin"></a><a name="setmargin"></a> CMFCCaptionBar:: SetMargin

Ustawia odległość między krawędzią elementu paska podpisu i krawędzią kontrolki paska tytułu.

```cpp
void SetMargin(int nMargin);
```

### <a name="parameters"></a>Parametry

*nMargin*<br/>
podczas Odległość, w pikselach, między krawędzią elementów paska podpisu i krawędzią kontrolki paska tytułu.

## <a name="cmfccaptionbarsettext"></a><a name="settext"></a> CMFCCaptionBar::SetText

Ustawia etykietę tekstową paska podpisu.

```cpp
void SetText(
    const CString& strText,
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>Parametry

*strText*<br/>
podczas Ciąg tekstowy do ustawienia.

*TextAlignment*<br/>
podczas Wyrównanie tekstu.

### <a name="remarks"></a>Uwagi

Etykieta tekstowa jest wyrównana jak określono przez parametr *TextAlignment* . Może to być jedna z następujących `BarElementAlignment` wartości:

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)

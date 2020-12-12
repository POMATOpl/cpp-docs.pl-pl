---
description: 'Dowiedz się więcej na temat: Klasa CMFCCaptionButton'
title: Klasa CMFCCaptionButton
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
ms.openlocfilehash: 6c3c1cbeea4a548f2951276b3ad43cb598cf22a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327746"
---
# <a name="cmfccaptionbutton-class"></a>Klasa CMFCCaptionButton

`CMFCCaptionButton`Klasa implementuje przycisk, który jest wyświetlany na pasku podpisu dla okienka dokującego lub okna mini-frame. Zazwyczaj struktura tworzy przyciski podpisu automatycznie.

## <a name="syntax"></a>Składnia

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>Elementy członkowskie

### <a name="constructors"></a>Konstruktory

|Nazwa|Opis|
|----------|-----------------|
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|Konstruuje obiekt CMFCCaptionButton.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCCaptionButton::GetHit](#gethit)|Zwraca polecenie reprezentowane przez przycisk.|
|[CMFCCaptionButton::GetIconID](#geticonid)|Zwraca identyfikator obrazu skojarzony z przyciskiem.|
|[CMFCCaptionButton:: getRect](#getrect)|Zwraca prostokąt zajmowany przez przycisk.|
|[CMFCCaptionButton:: GetSize](#getsize)|Zwraca szerokość i wysokość przycisku.|
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Wskazuje, czy wysokość paska tytułu jest ustawiona na rozmiar minimalny.|
|[CMFCCaptionButton:: Move](#move)|Ustawia lokalizację rysowania przycisku i okna Pokaż stan.|
|[CMFCCaptionButton:: OnDraw](#ondraw)|Rysuje przycisk podpis.|
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Ustawia rozmiar mini paska tytułu.|

## <a name="remarks"></a>Uwagi

Można utworzyć klasę z [klasy CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) i użyć metody chronionej, `AddButton` Aby dodać przyciski podpisów do okna mini frame.

CPaneFrameWnd. h definiuje identyfikatory poleceń dla dwóch typów przycisków podpisów:

- AFX_CAPTION_BTN_PIN, w którym jest wyświetlany przycisk Przypnij, gdy okienko dokujące obsługuje tryb autoukrywania.

- AFX_CAPTION_BTN_CLOSE, który wyświetla przycisk **Zamknij** , gdy okienko może być zamknięte lub ukryte.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania `CMFCCaptionButton` obiektu i ustawiania rozmiaru minipaska na pasku tytułu.

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcaptionbutton. h

## <a name="cmfccaptionbuttoncmfccaptionbutton"></a><a name="cmfccaptionbutton"></a> CMFCCaptionButton::CMFCCaptionButton

Konstruuje `CMFCCaptionButton` obiekt.

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>Parametry

*nHit*<br/>
podczas Polecenie skojarzone z przyciskiem.

*bLeftAlign*<br/>
podczas Określa, czy przycisk jest wyrównany do lewej.

Poniższa tabela zawiera listę możliwych wartości parametru *nHit* .

|Wartość|Polecenie|
|-----------|-------------|
|AFX_HTCLOSE|Przycisk Zamknij.|
|HTMINBUTTON|Przycisk Minimalizuj.|
|HTMAXBUTTON|Przycisk Maksymalizuj.|
|AFX_HTLEFTBUTTON|Przycisk strzałki w lewo.|
|AFX_HTRIGHTBUTTON|Przycisk strzałki w prawo.|
|AFX_HTMENU|Przycisk menu Strzałka w dół.|
|HTNOWHERE|Wartość domyślna; reprezentuje polecenie No.|

### <a name="remarks"></a>Uwagi

Domyślnie przyciski podpisów nie są skojarzone z poleceniem.

Przyciski podpisu są wyrównane do prawej lub lewej.

## <a name="cmfccaptionbuttongethit"></a><a name="gethit"></a> CMFCCaptionButton::GetHit

Zwraca polecenie reprezentowane przez przycisk.

```
UINT GetHit() const;
```

### <a name="return-value"></a>Wartość zwracana

Polecenie reprezentowane przez przycisk.

Poniższa tabela zawiera listę możliwych wartości zwracanych.

|Wartość|Polecenie|
|-----------|-------------|
|AFX_HTCLOSE|Przycisk Zamknij.|
|HTMINBUTTON|Przycisk Minimalizuj.|
|HTMAXBUTTON|Przycisk Maksymalizuj.|
|AFX_HTLEFTBUTTON|Przycisk strzałki w lewo.|
|AFX_HTRIGHTBUTTON|Przycisk strzałki w prawo.|
|AFX_HTMENU|Przycisk menu Strzałka w dół.|
|HTNOWHERE|Wartość domyślna; reprezentuje polecenie No.|

## <a name="cmfccaptionbuttongeticonid"></a><a name="geticonid"></a> CMFCCaptionButton::GetIconID

Zwraca identyfikator obrazu skojarzony z przyciskiem.

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>Parametry

*bHorz*<br/>
podczas Wartość TRUE dla identyfikatora obrazu z lewej strony lub strzałki w prawo; Wartość FALSE dla identyfikatora obrazu strzałki w górę lub w dół.

*bMaximized*<br/>
podczas Wartość TRUE dla maksymalizowanego identyfikatora obrazu; Wartość FALSE dla identyfikatora obrazu minimalizowania.

### <a name="return-value"></a>Wartość zwracana

Identyfikator obrazu.

### <a name="remarks"></a>Uwagi

Parametry określają identyfikatory obrazu dla przycisków minimalizowania lub maksymalizowania podpisów.

## <a name="cmfccaptionbuttongetrect"></a><a name="getrect"></a> CMFCCaptionButton:: getRect

Zwraca prostokąt zajmowany przez przycisk.

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>Wartość zwracana

Prostokąt reprezentujący lokalizację przycisku.

### <a name="remarks"></a>Uwagi

Jeśli nie widzisz przycisku, zwracany rozmiar wynosi 0.

## <a name="cmfccaptionbuttongetsize"></a><a name="getsize"></a> CMFCCaptionButton:: GetSize

Zwraca szerokość i wysokość przycisku.

```
static CSize GetSize();
```

### <a name="return-value"></a>Wartość zwracana

Zewnętrzne wymiary przycisku.

### <a name="remarks"></a>Uwagi

Zwrócony rozmiar zawiera margines przycisku i obramowanie.

## <a name="cmfccaptionbuttonisminiframebutton"></a><a name="isminiframebutton"></a> CMFCCaptionButton::IsMiniFrameButton

Wskazuje, czy wysokość paska tytułu jest ustawiona na rozmiar minimalny.

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli podpis jest ustawiony na rozmiar mini; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

## <a name="cmfccaptionbuttonmove"></a><a name="move"></a> CMFCCaptionButton:: Move

Ustawia lokalizację rysowania przycisku i okna Pokaż stan.

```cpp
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametry

*ptTo*<br/>
podczas Nowa lokalizacja.

*bHide*<br/>
podczas Określa, czy przycisk ma być wyświetlany.

## <a name="cmfccaptionbuttonondraw"></a><a name="ondraw"></a> CMFCCaptionButton:: OnDraw

Rysuje przycisk podpis.

```
virtual void OnDraw(
    CDC* pDC,
    BOOL bActive,
    BOOL bHorz = TRUE,
    BOOL bMaximized = TRUE,
    BOOL bDisabled = FALSE);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia dla przycisku.

*bActive*<br/>
podczas Określa, czy ma być rysowany aktywny obraz przycisku.

*bHorz*<br/>
podczas Zarezerwowane do użycia w klasie pochodnej.

*bMaximized*<br/>
podczas Określa, czy ma być rysowany zmaksymalizowany obraz przycisku.

*Poddany*<br/>
podczas Określa, czy ma być rysowany aktywny obraz przycisku.

### <a name="remarks"></a>Uwagi

Parametr *bMaximized* jest używany, gdy przycisk jest przyciskiem Maksymalizuj lub Minimalizuj.

## <a name="cmfccaptionbuttonsetminiframebutton"></a><a name="setminiframebutton"></a> CMFCCaptionButton::SetMiniFrameButton

Ustawia rozmiar mini paska tytułu.

```cpp
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametry

*bSet*<br/>
podczas Wartość TRUE dla minimalnej wysokości paska tytułu; Wartość FALSE dla domyślnej wysokości paska tytułu.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)<br/>
[Klasa CDockablePane](../../mfc/reference/cdockablepane-class.md)

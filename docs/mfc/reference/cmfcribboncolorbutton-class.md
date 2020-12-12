---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonColorButton'
title: Klasa CMFCRibbonColorButton
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
ms.openlocfilehash: a350339559febdc9346dcf8b342d274d00bab391
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293719"
---
# <a name="cmfcribboncolorbutton-class"></a>Klasa CMFCRibbonColorButton

`CMFCRibbonColorButton`Klasa implementuje przycisk koloru, który można dodać do paska wstążki. Przycisk koloru wstążki wyświetla menu rozwijane zawierające co najmniej jedną paletę kolorów.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonColorButton : public CMFCRibbonGallery
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonColorButton:: addcolors](#addcolorsgroup)|Dodaje grupę kolorów do obszaru zwykłego koloru.|
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|Określa, czy przycisk **automatyczny** jest włączony.|
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|Włącza **inny** przycisk.|
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||
|[CMFCRibbonColorButton:: GetColor](#getcolor)|Zwraca aktualnie wybrany kolor.|
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Zwraca rozmiar elementów koloru, które są wyświetlane na pasku koloru.|
|[CMFCRibbonColorButton:: GetColumns](#getcolumns)||
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Zwraca kolor aktualnie zaznaczonego elementu w palecie kolorów menu podręcznego.|
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Usuwa wszystkie grupy kolorów z obszaru zwykłego koloru.|
|[CMFCRibbonColorButton:: SetColor](#setcolor)|Wybiera kolor z obszaru zwykłego koloru.|
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Ustawia rozmiar wszystkich elementów koloru, które są wyświetlane na pasku koloru.|
|[CMFCRibbonColorButton:: SetColorName](#setcolorname)||
|[CMFCRibbonColorButton:: SetColumns](#setcolumns)||
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|Określa listę wartości RGB do wyświetlenia w obszarze kolorów dokumentu.|
|[CMFCRibbonColorButton:: setpaleta](#setpalette)||
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||

## <a name="remarks"></a>Uwagi

Przycisk koloru wstążki wyświetla pasek koloru, gdy użytkownik naciśnie go. Domyślnie ten pasek koloru zawiera paletę wyboru koloru o nazwie obszar zwykłego koloru. Opcjonalnie na pasku koloru może być wyświetlany przycisk **automatyczny** , który umożliwia użytkownikowi wybranie koloru domyślnego, a także **inny** przycisk, który wyświetla podręczną paletę kolorów, która zawiera dodatkowe kolory.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCRibbonColorButton` klasie. W przykładzie przedstawiono sposób konstruowania `CMFCRibbonColorButton` obiektu, ustawiania dużego obrazu, włączania przycisku **automatycznego** , włączania **drugiego** przycisku, ustawiania liczby kolumn, ustawiania rozmiaru wszystkich elementów koloru, które są wyświetlane na pasku koloru, dodawania grupy kolorów do obszaru zwykłego koloru i określania listy wartości RGB do wyświetlenia w obszarze kolorów dokumentu. Ten fragment kodu jest częścią [przykładu rysowania klienta](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxribboncolorbutton. h

## <a name="cmfcribboncolorbuttonaddcolorsgroup"></a><a name="addcolorsgroup"></a> CMFCRibbonColorButton:: addcolors

Dodaje grupę kolorów do obszaru zwykłego koloru.

```cpp
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>Parametry

*lpszName*<br/>
podczas Nazwa grupy.

*lstColors*<br/>
podczas Lista kolorów.

*bContiguousColumns*<br/>
podczas Kontroluje, w jaki sposób elementy koloru są wyświetlane w grupie. W przypadku wartości TRUE elementy koloru są rysowane bez odstępów w pionie. W przypadku wartości FALSE elementy koloru są rysowane z pionowymi odstępami.

### <a name="remarks"></a>Uwagi

Użyj tej funkcji, aby wyskakujące okienko kolorów wyświetlało kilka grup kolorów. Możesz kontrolować sposób wyświetlania kolorów w grupie.

## <a name="cmfcribboncolorbuttoncmfcribboncolorbutton"></a><a name="cmfcribboncolorbutton"></a> CMFCRibbonColorButton::CMFCRibbonColorButton

Konstruuje `CMFCRibbonColorButton` obiekt.

```
CMFCRibbonColorButton();

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex,
    COLORREF color = RGB(0, 0, 0));

CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    BOOL bSimpleButtonLook,
    int nSmallImageIndex,
    int nLargeImageIndex,
    COLORREF color = RGB(0, 0, 0));
```

### <a name="parameters"></a>Parametry

*nID*<br/>
podczas Określa identyfikator polecenia, które ma zostać wykonane po kliknięciu przycisku przez użytkownika.

*lpszText*<br/>
podczas Określa tekst, który ma być wyświetlany na przycisku.

*nSmallImageIndex*<br/>
podczas Indeks (liczony od zera) małego obrazu, który ma być wyświetlany na przycisku.

*Kolor*<br/>
podczas Kolor przycisku (domyślnie czarny).

*bSimpleButtonLook*<br/>
podczas W przypadku wartości TRUE przycisk jest rysowany jako prosty prostokąt.

*nLargeImageIndex*<br/>
podczas Indeks (liczony od zera) dużego obrazu, który ma być wyświetlany na przycisku.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncolorbuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCRibbonColorButton::EnableAutomaticButton

Określa, czy przycisk **automatyczny** jest włączony.

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE,
    LPCTSTR lpszToolTip=NULL,
    BOOL bOnTop=TRUE,
    BOOL bDrawBorder=FALSE);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
podczas Etykieta przycisku **automatycznego** .

*colorAutomatic*<br/>
podczas Wartość RGB określająca domyślny kolor przycisku **automatycznego** .

*bEnable*<br/>
podczas Ma wartość TRUE, jeśli przycisk **automatyczny** jest włączony; Wartość FALSE, jeśli jest wyłączona.

*lpszToolTip*<br/>
podczas Etykietka narzędzia przycisku **automatycznego** .

*bOnTop*<br/>
podczas Określa, czy przycisk **automatyczny** znajduje się u góry, przed paletą kolorów.

*bDrawBorder*<br/>
podczas Ma wartość TRUE, jeśli aplikacja rysuje obramowanie wokół paska koloru na przycisku koloru wstążki. Pasek koloru Wyświetla aktualnie wybrany kolor. FAŁSZ, jeśli aplikacja nie rysuje obramowania

## <a name="cmfcribboncolorbuttonenableotherbutton"></a><a name="enableotherbutton"></a> CMFCRibbonColorButton::EnableOtherButton

Włącza **inny** przycisk.

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
Etykieta przycisku.

*lpszToolTip*<br/>
Tekst etykietki narzędzia dla **drugiego** przycisku.

### <a name="remarks"></a>Uwagi

**Drugim** przyciskiem jest przycisk, który jest wyświetlany poniżej grupy kolorów. Gdy użytkownik kliknie **inny** przycisk, wyświetli okno dialogowe koloru.

## <a name="cmfcribboncolorbuttongetautomaticcolor"></a><a name="getautomaticcolor"></a> CMFCRibbonColorButton::GetAutomaticColor

Pobiera bieżący kolor przycisku automatycznego.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość koloru RGB, która reprezentuje bieżący kolor przycisku automatycznego.

### <a name="remarks"></a>Uwagi

Kolor przycisku automatycznego jest ustawiany przez `colorAutomatic` parametr przesłany do `CMFCRibbonColorButton::EnableAutomaticButton` metody.

## <a name="cmfcribboncolorbuttongetcolor"></a><a name="getcolor"></a> CMFCRibbonColorButton:: GetColor

Zwraca aktualnie wybrany kolor.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Kolor wybrany przez kliknięcie przycisku.

## <a name="cmfcribboncolorbuttongetcolorboxsize"></a><a name="getcolorboxsize"></a> CMFCRibbonColorButton::GetColorBoxSize

Zwraca rozmiar elementów koloru, które są wyświetlane na pasku koloru.

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Rozmiar przycisków kolorów na palecie kolorów listy rozwijanej.

## <a name="cmfcribboncolorbuttongetcolumns"></a><a name="getcolumns"></a> CMFCRibbonColorButton:: GetColumns

Pobiera liczbę elementów w wierszu wyświetlania galerii przycisku koloru wstążki.

```
int GetColumns() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca liczbę ikon w każdym wierszu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncolorbuttongethighlightedcolor"></a><a name="gethighlightedcolor"></a> CMFCRibbonColorButton::GetHighlightedColor

Zwraca kolor aktualnie zaznaczonego elementu na wyskakującej palecie kolorów.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Kolor aktualnie zaznaczonego elementu na wyskakującej palecie kolorów.

## <a name="cmfcribboncolorbuttonremoveallcolorgroups"></a><a name="removeallcolorgroups"></a> CMFCRibbonColorButton::RemoveAllColorGroups

Usuwa wszystkie grupy kolorów z obszaru zwykłego koloru.

```cpp
void RemoveAllColorGroups();
```

## <a name="cmfcribboncolorbuttonsetcolor"></a><a name="setcolor"></a> CMFCRibbonColorButton:: SetColor

Wybiera kolor z obszaru zwykłego koloru.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
podczas Kolor do ustawienia.

## <a name="cmfcribboncolorbuttonsetcolorboxsize"></a><a name="setcolorboxsize"></a> CMFCRibbonColorButton::SetColorBoxSize

Ustawia rozmiar wszystkich elementów koloru, które są wyświetlane na pasku koloru.

```cpp
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>Parametry

*sizeBox*<br/>
podczas Nowy rozmiar przycisków koloru w palecie kolorów.

## <a name="cmfcribboncolorbuttonsetcolorname"></a><a name="setcolorname"></a> CMFCRibbonColorButton:: SetColorName

Ustawia nową nazwę określonego koloru.

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
podczas Wartość RGB koloru.

*strName*<br/>
podczas Nowa nazwa określonego koloru.

### <a name="remarks"></a>Uwagi

Ponieważ wywołuje `CMFCColorBar::SetColorName` tę metodę, ta metoda zmienia nazwę określonego koloru we wszystkich `CMFCColorBar` obiektach w aplikacji.

## <a name="cmfcribboncolorbuttonsetcolumns"></a><a name="setcolumns"></a> CMFCRibbonColorButton:: SetColumns

Ustawia liczbę kolumn wyświetlanych w tabeli kolorów prezentowanych użytkownikowi podczas procesu wyboru koloru użytkownika.

```cpp
void SetColumns(int nColumns);
```

### <a name="parameters"></a>Parametry

*nColumns*<br/>
podczas Liczba ikon koloru, które mają być wyświetlane w każdym wierszu.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncolorbuttonsetdocumentcolors"></a><a name="setdocumentcolors"></a> CMFCRibbonColorButton::SetDocumentColors

Określa listę wartości RGB do wyświetlenia w obszarze kolorów dokumentu.

```cpp
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Parametry

*lpszLabel*<br/>
podczas Tekst, który będzie wyświetlany z kolorami dokumentu.

*lstColors*<br/>
podczas Odwołanie do listy wartości RGB.

## <a name="cmfcribboncolorbuttonsetpalette"></a><a name="setpalette"></a> CMFCRibbonColorButton:: setpaleta

Określa kolory standardowe, które mają być wyświetlane w tabeli kolorów, która zostanie wyświetlona na przycisku kolorów.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parametry

*pPalette*<br/>
podczas Wskaźnik do palety kolorów.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncolorbuttonupdatecolor"></a><a name="updatecolor"></a> CMFCRibbonColorButton::UpdateColor

Wywoływane przez platformę, gdy użytkownik wybierze kolor z tabeli kolorów wyświetlanej, gdy użytkownik kliknie przycisk Color (kolor).

```cpp
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
podczas Kolor wybrany przez użytkownika.

### <a name="remarks"></a>Uwagi

`CMFCRibbonColorButton::UpdateColor`Metoda zmienia kolor aktualnie wybranego przycisku i powiadamia jego element nadrzędny przez wysłanie komunikatu WM_COMMAND za pomocą BN_CLICKED standardowego powiadomienia. Użyj metody [CMFCRibbonColorButton:: GetColor](#getcolor) , aby pobrać wybrany kolor.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

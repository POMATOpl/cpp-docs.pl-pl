---
description: 'Dowiedz się więcej na temat: Klasa CMFCColorPickerCtrl'
title: Klasa CMFCColorPickerCtrl
ms.date: 11/19/2018
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
helpviewer_keywords:
- CMFCColorPickerCtrl [MFC], CMFCColorPickerCtrl
- CMFCColorPickerCtrl [MFC], GetColor
- CMFCColorPickerCtrl [MFC], GetHLS
- CMFCColorPickerCtrl [MFC], GetHue
- CMFCColorPickerCtrl [MFC], GetLuminance
- CMFCColorPickerCtrl [MFC], GetSaturation
- CMFCColorPickerCtrl [MFC], SelectCellHexagon
- CMFCColorPickerCtrl [MFC], SetColor
- CMFCColorPickerCtrl [MFC], SetHLS
- CMFCColorPickerCtrl [MFC], SetHue
- CMFCColorPickerCtrl [MFC], SetLuminance
- CMFCColorPickerCtrl [MFC], SetLuminanceBarWidth
- CMFCColorPickerCtrl [MFC], SetOriginalColor
- CMFCColorPickerCtrl [MFC], SetPalette
- CMFCColorPickerCtrl [MFC], SetSaturation
- CMFCColorPickerCtrl [MFC], SetType
- CMFCColorPickerCtrl [MFC], DrawCursor
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
ms.openlocfilehash: e4363c08af86dee96df1492e9a029414d9902435
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313076"
---
# <a name="cmfccolorpickerctrl-class"></a>Klasa CMFCColorPickerCtrl

`CMFCColorPickerCtrl`Klasa zawiera funkcje kontrolki, która jest używana do wybierania kolorów.

## <a name="syntax"></a>Składnia

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Konstruuje `CMFCColorPickerCtrl` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCColorPickerCtrl:: GetColor](#getcolor)|Pobiera kolor wybrany przez użytkownika.|
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Pobiera wartości odcienia, Luminancja i nasycenie koloru wybieranego przez użytkownika.|
|[CMFCColorPickerCtrl::GetHue](#gethue)|Pobiera składnik odcienia koloru wybieranego przez użytkownika.|
|[CMFCColorPickerCtrl:: getluminancja](#getluminance)|Pobiera składnik luminancji koloru wybieranego przez użytkownika.|
|[CMFCColorPickerCtrl:: getnasycenie](#getsaturation)|Pobiera składnik nasycenia koloru wybieranego przez użytkownika.|
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Ustawia bieżący kolor na kolor zdefiniowany przez określone składniki koloru RGB lub określony sześciokąt komórki.|
|[CMFCColorPickerCtrl:: SetColor](#setcolor)|Ustawia bieżący kolor na określoną wartość koloru RGB.|
|[CMFCColorPickerCtrl::SetHLS](#sethls)|Ustawia bieżący kolor na określoną wartość koloru HLS.|
|[CMFCColorPickerCtrl::SetHue](#sethue)|Zmienia składnik odcienia aktualnie zaznaczonego koloru.|
|[CMFCColorPickerCtrl:: setluminancja](#setluminance)|Zmienia składnik luminancji aktualnie zaznaczonego koloru.|
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Ustawia szerokość paska luminancji w kontrolce selektora kolorów.|
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|Ustawia początkowy kolor wybrany.|
|[CMFCColorPickerCtrl:: setpaleta](#setpalette)|Ustawia bieżącą paletę kolorów.|
|[CMFCColorPickerCtrl:: setnasycenie](#setsaturation)|Zmienia składnik nasycenia aktualnie zaznaczonego koloru.|
|[CMFCColorPickerCtrl:: SetType](#settype)|Ustawia typ kontrolki selektora kolorów do wyświetlenia.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCColorPickerCtrl::D rawCursor](#drawcursor)|Wywoływane przez platformę przed wyświetleniem kursora wskazującego wybrany kolor.|

## <a name="remarks"></a>Uwagi

Kolory standardowe są wybierane z wielokolorowej palety kolorów, a kolory niestandardowe są wybierane z paska luminancja, gdzie kolory są określone przy użyciu notacji Red/Green/Blue lub barwa/satuaration/Luminancja.

Poniższa ilustracja przedstawia kilka `CMFCColorPickerCtrl` obiektów.

![CMFCColorPickerCtrl — okno dialogowe](../../mfc/reference/media/colorpicker.png "CMFCColorPickerCtrl — okno dialogowe")

`CMFCColorPickerCtrl`Obsługuje dwie pary stylów. Style SZESNASTKOWe i HEX_GREYSCALE są odpowiednie dla standardowego wyboru koloru. Style SELEKTORa i LUMINANCJi są odpowiednie dla niestandardowego wyboru kolorów.

Wykonaj następujące kroki, aby dołączyć `CMFCColorPickerCtrl` formant do okna dialogowego:

1. Jeśli używasz **ClassWizard**, Wstaw nową kontrolkę Button do szablonu okna dialogowego (ponieważ `CMFCColorPickerCtrl` Klasa jest dziedziczona z `CButton` klasy).

1. Wstaw zmienną członkowską skojarzoną z nowym kontrolką przycisku do klasy okna dialogowego. Następnie zmień typ zmiennej z `CButton` na `CMFCColorPickerCtrl` .

1. Wstaw `WM_INITDIALOG` procedurę obsługi komunikatów dla klasy okna dialogowego. W programie obsługi Ustaw typ, paletę i początkowy kolor zaznaczonego `CMFCColorPickerCtrl` formantu.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konfigurowania `CMFCColorPickerCtrl` obiektu przy użyciu różnych metod w `CMFCColorPickerCtrl` klasie. W przykładzie pokazano, jak ustawić typ formantu selektora i jak ustawić jego kolor, odcień, luminancję i nasycenie. Przykład jest częścią [nowych kontrolek](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcolorpickerctrl. h

## <a name="cmfccolorpickerctrlcmfccolorpickerctrl"></a><a name="cmfccolorpickerctrl"></a> CMFCColorPickerCtrl::CMFCColorPickerCtrl

Konstruuje `CMFCColorPickerCtrl` obiekt.

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrldrawcursor"></a><a name="drawcursor"></a> CMFCColorPickerCtrl::D rawCursor

Wywoływane przez platformę przed wyświetleniem kursora wskazującego wybrany kolor.

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

*cinania*<br/>
podczas Określa prostokątny obszar wokół zaznaczonego koloru.

### <a name="remarks"></a>Uwagi

Zastąp tę metodę, gdy zachodzi potrzeba zmiany kształtu kursora wskazującego na wybrany kolor.

## <a name="cmfccolorpickerctrlgetcolor"></a><a name="getcolor"></a> CMFCColorPickerCtrl:: GetColor

Pobiera kolor wybrany przez użytkownika.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość RGB wybranego koloru.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrlgethls"></a><a name="gethls"></a> CMFCColorPickerCtrl::GetHLS

Pobiera wartości odcienia, Luminancja i nasycenie koloru wybieranego przez użytkownika.

```cpp
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>Parametry

*spowoduje*<br/>
określoną Wskaźnik do zmiennej typu Double, która otrzymuje informacje o odcieniu.

*Jaskrawość*<br/>
określoną Wskaźnik do zmiennej typu Double, która otrzymuje informacje o jaskrawości.

*nasyceni*<br/>
określoną Wskaźnik do zmiennej typu Double, która otrzymuje informacje o nasyceniu.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrlgethue"></a><a name="gethue"></a> CMFCColorPickerCtrl::GetHue

Pobiera składnik odcienia koloru wybieranego przez użytkownika.

```
double GetHue() const;
```

### <a name="return-value"></a>Wartość zwracana

Składnik odcienia wybranego koloru.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrlgetluminance"></a><a name="getluminance"></a> CMFCColorPickerCtrl:: getluminancja

Pobiera składnik luminancji koloru wybieranego przez użytkownika.

```
double GetLuminance() const;
```

### <a name="return-value"></a>Wartość zwracana

Składnik luminancji wybranego koloru.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrlgetsaturation"></a><a name="getsaturation"></a> CMFCColorPickerCtrl:: getnasycenie

Pobiera wartość nasycenia koloru wybieranego przez użytkownika.

```
double GetSaturation() const;
```

### <a name="return-value"></a>Wartość zwracana

Składnik nasycenia wybranego koloru.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrlselectcellhexagon"></a><a name="selectcellhexagon"></a> CMFCColorPickerCtrl::SelectCellHexagon

Ustawia bieżący kolor na kolor zdefiniowany przez określone składniki koloru RGB lub określony sześciokąt komórki.

```cpp
void SelectCellHexagon(
    BYTE R,
    BYTE G,
    BYTE B);

BOOL SelectCellHexagon(
    int x,
    int y);
```

### <a name="parameters"></a>Parametry

*R*<br/>
podczas Składnik koloru czerwonego.

*G*<br/>
podczas Zielony składnik koloru.

*B*<br/>
podczas Niebieski składnik koloru.

*x*<br/>
podczas Współrzędna x kursora, która wskazuje na sześciokątkę komórki.

*Y*<br/>
podczas Współrzędna y kursora, która wskazuje na sześciokątkę komórki.

### <a name="return-value"></a>Wartość zwracana

Drugie Przeciążenie tej metody zawsze zwraca wartość FALSE.

### <a name="remarks"></a>Uwagi

Pierwsze Przeciążenie tej metody ustawia kolor bieżącego koloru na kolor odpowiadający określonemu kontrolce koloru kolor czerwony, zielony i niebieski.

Drugie Przeciążenie tej metody ustawia kolor bieżącego koloru na kolor sześciokątny komórki, który jest wskazywany przez określoną lokalizację kursora.

## <a name="cmfccolorpickerctrlsetcolor"></a><a name="setcolor"></a> CMFCColorPickerCtrl:: SetColor

Ustawia bieżący kolor na określoną wartość koloru RGB.

```cpp
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
podczas Wartość koloru RGB.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrlsethls"></a><a name="sethls"></a> CMFCColorPickerCtrl::SetHLS

Ustawia bieżący kolor na określoną wartość koloru HLS.

```cpp
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>Parametry

*spowoduje*<br/>
podczas Wartość odcienia.

*Jaskrawość*<br/>
podczas Wartość luminancji.

*nasyceni*<br/>
podczas Wartość nasycenia.

*bInvalidate*<br/>
podczas PRAWDA, aby wymusić natychmiastowe aktualizowanie nowego koloru okna. w przeciwnym razie FALSE. Wartość domyślna to TRUE.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrlsethue"></a><a name="sethue"></a> CMFCColorPickerCtrl::SetHue

Zmienia odcień aktualnie zaznaczonego koloru.

```cpp
void SetHue(double Hue);
```

### <a name="parameters"></a>Parametry

*Spowoduje*<br/>
podczas Wartość odcienia.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrlsetluminance"></a><a name="setluminance"></a> CMFCColorPickerCtrl:: setluminancja

Zmienia jaskrawość aktualnie zaznaczonego koloru.

```cpp
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>Parametry

*Jaskrawość*<br/>
podczas Wartość luminancji.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrlsetluminancebarwidth"></a><a name="setluminancebarwidth"></a> CMFCColorPickerCtrl::SetLuminanceBarWidth

Ustawia szerokość paska luminancji w kontrolce selektora kolorów.

```cpp
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>Parametry

*w*<br/>
podczas Szerokość paska luminancji mierzona w pikselach.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby zmienić rozmiar paska luminancji, który znajduje się na karcie **niestandardowe** kontrolki selektora kolorów. Parametr *w* określa nową szerokość paska Luminancja. Wartość Width jest ignorowana, jeśli przekracza trzy czwarte szerokości obszaru klienta.

## <a name="cmfccolorpickerctrlsetoriginalcolor"></a><a name="setoriginalcolor"></a> CMFCColorPickerCtrl::SetOriginalColor

Ustawia początkowy kolor wybrany.

```cpp
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>Parametry

*ref*<br/>
podczas Wartość koloru RGB.

### <a name="remarks"></a>Uwagi

Wywołaj tę metodę, gdy zostanie zainicjowana kontrolka selektora kolorów.

## <a name="cmfccolorpickerctrlsetpalette"></a><a name="setpalette"></a> CMFCColorPickerCtrl:: setpaleta

Ustawia bieżącą paletę kolorów.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parametry

*pPalette*<br/>
podczas Wskaźnik do palety kolorów.

### <a name="remarks"></a>Uwagi

Paleta kolorów definiuje tablicę kolorów, które są prezentowane w kontrolce selektora kolorów.

## <a name="cmfccolorpickerctrlsetsaturation"></a><a name="setsaturation"></a> CMFCColorPickerCtrl:: setnasycenie

Zmienia nasycenie aktualnie zaznaczonego koloru.

```cpp
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>Parametry

*Nasyceni*<br/>
podczas Wartość nasycenia.

### <a name="remarks"></a>Uwagi

## <a name="cmfccolorpickerctrlsettype"></a><a name="settype"></a> CMFCColorPickerCtrl:: SetType

Ustawia typ kontrolki selektora kolorów do wyświetlenia.

```cpp
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>Parametry

*COLORTYPE*<br/>
podczas Typ formantu selektora kolorów.

Typy są zdefiniowane przez `CMFCColorPickerCtrl::COLORTYPE` Wyliczenie. Możliwe typy to LUMINANCJa, SELEKTOR, SZESNASTKOWy i HEX_GREYSCALE. Domyślny typ to SELEKTOR.

### <a name="remarks"></a>Uwagi

Aby określić typ formantu koloru, Wywołaj tę metodę przed utworzeniem formantu systemu Windows.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)

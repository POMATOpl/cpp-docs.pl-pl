---
description: 'Dowiedz się więcej na temat: Klasa CMFCToolTipInfo'
title: Klasa CMFCToolTipInfo
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
ms.openlocfilehash: 06ceca500ad92d5f3a27e2740a298d9c1bbfe1cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143432"
---
# <a name="cmfctooltipinfo-class"></a>Klasa CMFCToolTipInfo

Przechowuje informacje o wyglądzie etykietek narzędzi.

## <a name="syntax"></a>Składnia

```
class CMFCToolTipInfo
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCToolTipInfo:: operator =](#operator_eq)||

### <a name="data-members"></a>Elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CMFCToolTipInfo:: m_bBalloonTooltip](#m_bballoontooltip)|Zmienna logiczna wskazująca, czy etykietka narzędzia ma wygląd dymka.|
|[CMFCToolTipInfo:: m_bBoldLabel](#m_bboldlabel)|Zmienna logiczna wskazująca, czy etykiety etykietki narzędzi są wyświetlane w postaci pogrubionej czcionki.|
|[CMFCToolTipInfo:: m_bDrawDescription](#m_bdrawdescription)|Zmienna logiczna wskazująca, czy etykietka narzędzia zawiera opis.|
|[CMFCToolTipInfo:: m_bDrawIcon](#m_bdrawicon)|Zmienna logiczna wskazująca, czy etykietka narzędzia zawiera ikonę.|
|[CMFCToolTipInfo:: m_bDrawSeparator](#m_bdrawseparator)|Zmienna logiczna wskazująca, czy separator jest wyświetlany między etykietą etykietki narzędzia a opisem etykietki narzędzia.|
|[CMFCToolTipInfo:: m_bRoundedCorners](#m_broundedcorners)|Zmienna logiczna wskazująca, czy etykietka narzędzia ma zaokrąglone rogi.|
|[CMFCToolTipInfo:: m_bVislManagerTheme](#m_bvislmanagertheme)|Zmienna logiczna wskazująca, czy wygląd etykietki narzędzia powinien być kontrolowany przez Menedżera wizualizacji (zobacz [Klasa CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)).|
|[CMFCToolTipInfo:: m_clrBorder](#m_clrborder)|Kolor obramowania etykietki narzędzia.|
|[CMFCToolTipInfo:: m_clrFill](#m_clrfill)|Kolor tła etykietki narzędzia.|
|[CMFCToolTipInfo:: m_clrFillGradient](#m_clrfillgradient)|Kolor wypełnienia gradientu w etykietce narzędzia.|
|[CMFCToolTipInfo:: m_clrText](#m_clrtext)|Kolor tekstu w etykietce narzędzia.|
|[CMFCToolTipInfo:: m_nGradientAngle](#m_ngradientangle)|Kąt wypełnienia gradientu w etykietce narzędzia.|
|[CMFCToolTipInfo:: m_nMaxDescrWidth](#m_nmaxdescrwidth)|Maksymalna możliwa Szerokość (w pikselach) opisu w etykietce narzędzia.|

## <a name="remarks"></a>Uwagi

[](../../mfc/reference/cmfctooltipctrl-class.md) `CMFCToolTipInfo` Aby zaimplementować niestandardowe etykietki narzędzi w aplikacji, należy użyć klasy CMFCToolTipCtrl, i [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) . Aby zapoznać się z przykładem sposobu korzystania z tych klas etykietek narzędzi, zobacz temat [Klasa CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md) .

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób ustawiania wartości różnych zmiennych składowych w `CMFCToolTipInfo` klasie.

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxToolTipCtrl. h

## <a name="cmfctooltipinfom_bballoontooltip"></a><a name="m_bballoontooltip"></a> CMFCToolTipInfo:: m_bBalloonTooltip

Określa styl wyświetlania wszystkich etykietek narzędzi.

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>Uwagi

Wartość TRUE wskazuje, że etykietki narzędzi używają stylu dymka, wartość FALSE wskazuje, że etykietki narzędzi używają stylu prostokątnego.

## <a name="cmfctooltipinfom_bboldlabel"></a><a name="m_bboldlabel"></a> CMFCToolTipInfo:: m_bBoldLabel

Określa, czy czcionka tekstu etykietki narzędzia jest pogrubiona.

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>Uwagi

Ustaw dla tego elementu członkowskiego wartość true, aby wyświetlić tekst etykietki narzędzia z czcionką pogrubioną, lub wartość FAŁSZ, aby wyświetlić etykiety etykietki narzędzi z czcionką bez

## <a name="cmfctooltipinfom_bdrawdescription"></a><a name="m_bdrawdescription"></a> CMFCToolTipInfo:: m_bDrawDescription

Określa, czy każda etykietka narzędzia wyświetla tekst opisu.

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>Uwagi

Ustaw dla tego elementu członkowskiego wartość TRUE, aby wyświetlić opis, lub wartość FALSE, aby ukryć opis. Możesz określić opis etykietki narzędzia przez wywołanie [CMFCToolTipCtrl:: SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)

## <a name="cmfctooltipinfom_bdrawicon"></a><a name="m_bdrawicon"></a> CMFCToolTipInfo:: m_bDrawIcon

Określa, czy wszystkie etykietki narzędzi są wyświetlane ikony.

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>Uwagi

Ustaw dla tego elementu członkowskiego wartość TRUE, aby wyświetlić ikonę w każdej etykietce narzędzia, lub wartość FAŁSZ, aby wyświetlić etykietki narzędzi bez ikon.

## <a name="cmfctooltipinfom_bdrawseparator"></a><a name="m_bdrawseparator"></a> CMFCToolTipInfo:: m_bDrawSeparator

Określa, czy każda etykietka narzędzia ma separator między etykietą a jego opisem.

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>Uwagi

Ustaw dla tego elementu członkowskiego wartość TRUE, aby wyświetlić separator między etykietą i opisem etykietki narzędzia, lub wartość FAŁSZ, aby wyświetlić etykietki narzędzi bez separatora.

## <a name="cmfctooltipinfom_broundedcorners"></a><a name="m_broundedcorners"></a> CMFCToolTipInfo:: m_bRoundedCorners

Określa, czy wszystkie etykietki narzędzi mają zaokrąglone rogi.

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>Uwagi

Ustaw dla tego elementu członkowskiego wartość TRUE, aby wyświetlić Zaokrąglone rogi w etykietkach narzędzi, lub wartość FAŁSZ, aby wyświetlić prostokątne narożniki etykietek narzędzi.

## <a name="cmfctooltipinfom_clrborder"></a><a name="m_clrborder"></a> CMFCToolTipInfo:: m_clrBorder

Określa kolor obramowań wszystkich etykietek narzędzi.

```
COLORREF m_clrBorder;
```

## <a name="cmfctooltipinfom_clrfill"></a><a name="m_clrfill"></a> CMFCToolTipInfo:: m_clrFill

Określa kolor tła etykietki narzędzia.

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>Uwagi

Jeśli [CMFCToolTipInfo:: m_clrFillGradient](#m_clrfillgradient) ma wartość-1, kolor tła etykietki narzędzia to `m_clrFill` . W przeciwnym razie `m_clrFill` określa kolor początku gradientu i `m_clrFillGradient` określa kolor końca gradientu. [CMFCToolTipInfo:: m_nGradientAngle](#m_ngradientangle) określa kierunek gradientu.

## <a name="cmfctooltipinfom_clrfillgradient"></a><a name="m_clrfillgradient"></a> CMFCToolTipInfo:: m_clrFillGradient

Określa kolor końcowy tła gradientu dla etykietek narzędzi.

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>Uwagi

Jeśli `m_clrFillGradient` jest-1, nie ma gradientu. W przeciwnym razie kolor początkowy gradientu jest określany przez [CMFCToolTipInfo:: m_clrFill](#m_clrfill) , a kolor zakończenia gradientu jest określany przez `m_clrFillGradient` . [CMFCToolTipInfo:: m_nGradientAngle](#m_ngradientangle) określa kierunek gradientu.

## <a name="cmfctooltipinfom_clrtext"></a><a name="m_clrtext"></a> CMFCToolTipInfo:: m_clrText

Określa kolor tekstu wszystkich etykietek narzędzi.

```
COLORREF m_clrText;
```

## <a name="cmfctooltipinfom_ngradientangle"></a><a name="m_ngradientangle"></a> CMFCToolTipInfo:: m_nGradientAngle

Określa kąt, w którym gradient jest rysowany w tle etykietek narzędzi.

```
int m_nGradientAngle;
```

### <a name="remarks"></a>Uwagi

`m_nGradientAngle` Określa kąt (w stopniach), w którym gradient w tle etykietek narzędzi jest przesunięty od poziomej. Jeśli `m_nGradientAngle` jest równa 0, gradient jest rysowany od lewej do prawej. Jeśli `m_nGradientAngle` jest z zakresu od 1 do 360, Gradient obraca się w prawo o tę liczbę stopni. Jeśli `m_nGradientAngle` jest wartość-1, która jest wartością domyślną, gradient jest rysowany od góry do dołu. Jest to takie samo jak ustawienie `m_nGradientAngle` 90.

[CMFCToolTipInfo:: m_clrFill](#m_clrfill) `clrFill` Określa kolor początku gradientu i [CMFCToolTipInfo:: m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` określa kolor końca gradientu. Jeśli `m_clrFillGradient` jest-1, nie ma gradientu.

## <a name="cmfctooltipinfom_nmaxdescrwidth"></a><a name="m_nmaxdescrwidth"></a> CMFCToolTipInfo:: m_nMaxDescrWidth

Określa maksymalną szerokość opisu wyświetlanego w każdej etykietce narzędzia. Jeśli szerokość opisu przekracza określoną wartość, tekst jest opakowany.

```
int m_nMaxDescrWidth;
```

## <a name="cmfctooltipinfom_bvislmanagertheme"></a><a name="m_bvislmanagertheme"></a> CMFCToolTipInfo:: m_bVislManagerTheme

Określa, czy Menedżer wizualizacji aplikacji steruje wyglądem wszystkich etykietek narzędzi.

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>Uwagi

Jeśli `m_bVislManagerTheme` ma wartość true, każda etykietka narzędzia żąda nowego [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) z Menedżera wizualizacji aplikacji przed wyświetleniem ich na ekranie i używa wartości w tym obiekcie do określenia ich wyglądu. Inne elementy członkowskie [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) są ignorowane.

## <a name="cmfctooltipinfooperator"></a><a name="operator_eq"></a> CMFCToolTipInfo:: operator =

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>Parametry

podczas *src*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)<br/>
[Klasa CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)

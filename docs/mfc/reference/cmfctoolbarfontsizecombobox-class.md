---
description: 'Dowiedz się więcej na temat: Klasa CMFCToolBarFontSizeComboBox'
title: Klasa CMFCToolBarFontSizeComboBox
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
ms.openlocfilehash: a355e62f2ef538372d70b9b2b393bc16bff2ef4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331749"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>Klasa CMFCToolBarFontSizeComboBox

Przycisk paska narzędzi zawierający formant pola kombi, który umożliwia użytkownikowi wybranie rozmiaru czcionki.

## <a name="syntax"></a>Składnia

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Elementy członkowskie

### <a name="protected-constructors"></a>Konstruktory chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Konstruuje `CMFCToolBarFontSizeComboBox` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Zwraca wybrany rozmiar czcionki w twipach.|
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Wypełnia listę pól kombi ze wszystkimi obsługiwanymi rozmiarami czcionek dla określonej czcionki.|
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Ustawia rozmiar czcionki w twipach.|

## <a name="remarks"></a>Uwagi

Można użyć `CMFCToolBarFontSizeComboBox` obiektu wraz z obiektem [klasy CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) , aby umożliwić użytkownikowi wybranie czcionki i rozmiaru czcionki.

Możesz dodać przycisk pola kombi rozmiaru czcionki do paska narzędzi, tak jak Dodaj przycisk pola kombi czcionki. Aby uzyskać więcej informacji, zobacz [Klasa CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md).

Gdy użytkownik wybierze nową czcionkę w `CMFCToolBarFontComboBox` obiekcie, można wypełnić pole kombi rozmiar czcionki o obsługiwanych rozmiarach dla tej czcionki przy użyciu metody [CMFCToolBarFontSizeComboBox:: RebuildFontSizes](#rebuildfontsizes) .

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCToolBarFontSizeComboBox` klasie w celu skonfigurowania `CMFCToolBarFontSizeComboBox` obiektu. W przykładzie pokazano, jak pobrać rozmiar czcionki (w twipach) z pola tekstowego, wypełnić pole kombi rozmiar czcionki ze wszystkimi prawidłowymi rozmiarach danej czcionki i określić rozmiar czcionki w twipach. Ten fragment kodu jest częścią [przykładu Notatnika programu Word](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxtoolbarfontcombobox. h

## <a name="cmfctoolbarfontsizecomboboxcmfctoolbarfontsizecombobox"></a><a name="cmfctoolbarfontsizecombobox"></a> CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox

Konstruuje `CMFCToolBarFontSizeComboBox` obiekt.

```
CMFCToolBarFontSizeComboBox();
```

## <a name="cmfctoolbarfontsizecomboboxgettwipsize"></a><a name="gettwipsize"></a> CMFCToolBarFontSizeComboBox::GetTwipSize

Pobiera rozmiar czcionki w twipach, w polu tekstowym pola kombi rozmiar czcionki.

```
int GetTwipSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Jeśli wartość zwracana jest dodatnia, jest to rozmiar czcionki w twipach. Jest to-1, jeśli pole tekstowe pola kombi jest puste. Jeśli wystąpi błąd, jest to-2.

## <a name="cmfctoolbarfontsizecomboboxrebuildfontsizes"></a><a name="rebuildfontsizes"></a> CMFCToolBarFontSizeComboBox::RebuildFontSizes

Wypełnia pole kombi rozmiaru czcionki ze wszystkimi prawidłowymi rozmiarach danej czcionki.

```cpp
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>Parametry

*strFontName*<br/>
podczas Określa nazwę czcionki.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, jeśli chcesz synchronizować między wyborem w polu kombi czcionki a polem kombi o rozmiarze czcionki, takim jak [Klasa CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md).

## <a name="cmfctoolbarfontsizecomboboxsettwipsize"></a><a name="settwipsize"></a> CMFCToolBarFontSizeComboBox::SetTwipSize

Zaokrągla określony rozmiar (w twipach) do najbliższego rozmiaru w punktach, a następnie ustawia wybrany rozmiar w polu kombi na tę wartość.

```cpp
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>Parametry

*nSize*<br/>
podczas Określa rozmiar czcionki (w twipach) do ustawienia.

### <a name="remarks"></a>Uwagi

Poprzedni prawidłowy rozmiar czcionki można pobrać później, wywołując metodę [CMFCToolBarFontSizeComboBox:: GetTwipSize](#gettwipsize) .

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Klasa CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Klasa CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[Klasa CMFCFontInfo](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Wskazówki: umieszczanie formantów na paskach narzędzi](../../mfc/walkthrough-putting-controls-on-toolbars.md)

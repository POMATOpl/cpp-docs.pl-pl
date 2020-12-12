---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonButtonsGroup'
title: Klasa CMFCRibbonButtonsGroup
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::AddButtons
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetButton
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetCount
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetImageSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::GetRegularSize
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::HasImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::OnDrawImage
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::RemoveAll
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetImages
- AFXRIBBONBUTTONSGROUP/CMFCRibbonButtonsGroup::SetParentCategory
helpviewer_keywords:
- CMFCRibbonButtonsGroup [MFC], CMFCRibbonButtonsGroup
- CMFCRibbonButtonsGroup [MFC], AddButton
- CMFCRibbonButtonsGroup [MFC], AddButtons
- CMFCRibbonButtonsGroup [MFC], GetButton
- CMFCRibbonButtonsGroup [MFC], GetCount
- CMFCRibbonButtonsGroup [MFC], GetImageSize
- CMFCRibbonButtonsGroup [MFC], GetRegularSize
- CMFCRibbonButtonsGroup [MFC], HasImages
- CMFCRibbonButtonsGroup [MFC], OnDrawImage
- CMFCRibbonButtonsGroup [MFC], RemoveAll
- CMFCRibbonButtonsGroup [MFC], SetImages
- CMFCRibbonButtonsGroup [MFC], SetParentCategory
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
ms.openlocfilehash: 0b86ce6ff21bd36daaac9d68ce511ae395141170
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293835"
---
# <a name="cmfcribbonbuttonsgroup-class"></a>Klasa CMFCRibbonButtonsGroup

`CMFCRibbonButtonsGroup`Klasa umożliwia organizowanie zestawu przycisków wstążki w grupę. Wszystkie przyciski w grupie są bezpośrednio sąsiadujące ze sobą w poziomie i ujęte w obramowanie.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](#cmfcribbonbuttonsgroup)|Konstruuje `CMFCRibbonButtonsGroup` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonButtonsGroup:: AddButton](#addbutton)|Dodaje przycisk do grupy.|
|[CMFCRibbonButtonsGroup:: AddButtons](#addbuttons)|Dodaje listę przycisków do grupy.|
|[CMFCRibbonButtonsGroup:: getbutton](#getbutton)|Zwraca wskaźnik do przycisku, który znajduje się w określonym indeksie.|
|[CMFCRibbonButtonsGroup:: GetCount](#getcount)|Zwraca liczbę przycisków w grupie.|
|[CMFCRibbonButtonsGroup::GetImageSize](#getimagesize)|Zwraca rozmiar obrazu zwykłych obrazów w grupie wstążki (Przesłania [CMFCRibbonBaseElement:: GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize)).|
|[CMFCRibbonButtonsGroup::GetRegularSize](#getregularsize)|Zwraca zwykły rozmiar elementu wstążki (Przesłania [CMFCRibbonBaseElement:: GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize)).|
|[CMFCRibbonButtonsGroup::HasImages](#hasimages)|Informuje, czy `CMFCRibbonButtonsGroup` obiekt zawiera obrazy pasków narzędzi.|
|[CMFCRibbonButtonsGroup::OnDrawImage](#ondrawimage)|Rysuje odpowiedni obraz dla określonego przycisku, w zależności od tego, czy przycisk jest normalny, wyróżniony czy wyłączony.|
|[CMFCRibbonButtonsGroup::](#removeall)|Usuwa wszystkie przyciski z `CMFCRibbonButtonsGroup` obiektu.|
|[CMFCRibbonButtonsGroup:: SetImages](#setimages)|Przypisuje obrazy do grupy.|
|[CMFCRibbonButtonsGroup::SetParentCategory](#setparentcategory)|Ustawia element nadrzędny `CMFCRibbonCategory` `CMFCRibbonButtonsGroup` obiektu i wszystkie znajdujące się w nim przyciski (Przesłania [CMFCRibbonBaseElement:: SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory)).|

## <a name="remarks"></a>Uwagi

Grupa pochodzi od [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) i może być manipulowana jako pojedyncza jednostka. Grupę można umieścić w dowolnym panelu lub menu podręcznym.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób użycia różnych metod w `CMFCRibbonButtonsGroup` klasie. W przykładzie pokazano sposób konstruowania `CMFCRibbonButtonsGroup` obiektu, przypisywania obrazów do grupy przycisków wstążki i Dodawanie przycisku do grupy przycisków wstążki. Ten fragment kodu jest częścią [przykładu rysowania klienta](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/cpp/cmfcribbonbuttonsgroup-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxribbonbuttonsgroup. h

## <a name="cmfcribbonbuttonsgroupaddbutton"></a><a name="addbutton"></a> CMFCRibbonButtonsGroup:: AddButton

Dodaje przycisk do grupy.

```cpp
void AddButton(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Parametry

*pButton*<br/>
podczas Wskaźnik do przycisku do dodania.

## <a name="cmfcribbonbuttonsgroupaddbuttons"></a><a name="addbuttons"></a> CMFCRibbonButtonsGroup:: AddButtons

Dodaje listę przycisków do grupy.

```cpp
void AddButtons(
    const CList<CMFCRibbonBaseElement*,CMFCRibbonBaseElement*>& lstButtons);
```

### <a name="parameters"></a>Parametry

*lstButtons*<br/>
podczas Lista wskaźników do przycisków, które chcesz dodać.

## <a name="cmfcribbonbuttonsgroupcmfcribbonbuttonsgroup"></a><a name="cmfcribbonbuttonsgroup"></a> CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup

Konstruuje `CMFCRibbonButtonsGroup` obiekt.

```
CMFCRibbonButtonsGroup();
CMFCRibbonButtonsGroup(CMFCRibbonBaseElement* pButton);
```

### <a name="parameters"></a>Parametry

*pButton*<br/>
podczas Określa przycisk, który ma zostać dodany do nowo utworzonego `CMFCRibbonButtonsGroup` obiektu.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonbuttonsgroupgetbutton"></a><a name="getbutton"></a> CMFCRibbonButtonsGroup:: getbutton

Zwraca wskaźnik do przycisku, który znajduje się w określonym indeksie.

```
CMFCRibbonBaseElement* GetButton(int i) const;
```

### <a name="parameters"></a>Parametry

*i*<br/>
podczas Indeks (liczony od zera) przycisku do zwrócenia.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do przycisku, który znajduje się w określonym indeksie. Wartość NULL, jeśli określony indeks jest poza zakresem.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonbuttonsgroupgetcount"></a><a name="getcount"></a> CMFCRibbonButtonsGroup:: GetCount

Zwraca liczbę przycisków w grupie.

```
int GetCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba przycisków w grupie.

## <a name="cmfcribbonbuttonsgroupgetimagesize"></a><a name="getimagesize"></a> CMFCRibbonButtonsGroup::GetImageSize

Pobiera rozmiar obrazu źródłowego chronionego `CMFCToolBarImages` elementu członkowskiego `m_Images` .

```
const CSize GetImageSize() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca rozmiar obrazu źródłowego obrazów pasków narzędzi, jeśli istnieją lub `CSize` zero, jeśli nie.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonbuttonsgroupgetregularsize"></a><a name="getregularsize"></a> CMFCRibbonButtonsGroup::GetRegularSize

Pobiera maksymalny możliwy rozmiar elementu grupy wstążki.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia grupy wstążki.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonbuttonsgrouphasimages"></a><a name="hasimages"></a> CMFCRibbonButtonsGroup::HasImages

Informuje, czy `CMFCRibbonButtonsGroup` obiekt zawiera obrazy pasków narzędzi.

```
BOOL HasImages() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE, Jeśli chroniony `CMFCToolBarImages` element członkowski `m_Images` zawiera wszystkie obrazy, lub wartość false, jeśli nie.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonbuttonsgroupondrawimage"></a><a name="ondrawimage"></a> CMFCRibbonButtonsGroup::OnDrawImage

Rysuje odpowiedni obraz dla określonego przycisku, w zależności od tego, czy przycisk jest normalny, wyróżniony czy wyłączony.

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rectImage,
    CMFCRibbonBaseElement* pButton,
    int nImageIndex);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia `CMFCRibbonButtonsGroup` obiektu.

*rectImage*<br/>
podczas Prostokąt, w którym ma zostać narysowany obraz.

*pButton*<br/>
podczas Przycisk, dla którego ma zostać narysowany obraz.

*nImageIndex*<br/>
podczas Indeks obrazu do rysowania na przycisku (w jednej z trzech tablic obrazu dla normalnych, wyróżnionych lub wyłączonych przycisków).

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonbuttonsgroupremoveall"></a><a name="removeall"></a> CMFCRibbonButtonsGroup::

Usuwa wszystkie przyciski z `CMFCRibbonButtonsGroup` obiektu.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcribbonbuttonsgroupsetimages"></a><a name="setimages"></a> CMFCRibbonButtonsGroup:: SetImages

Przypisuje obrazy do grupy przycisków wstążki.

```cpp
void SetImages(
    CMFCToolBarImages* pImages,
    CMFCToolBarImages* pHotImages,
    CMFCToolBarImages* pDisabledImages);
```

### <a name="parameters"></a>Parametry

*pImages*<br/>
podczas Zwykłe obrazy.

*pHotImages*<br/>
podczas Obrazy gorącą.

*pDisabledImages*<br/>
podczas Wyłączone obrazy.

### <a name="remarks"></a>Uwagi

Wywołaj `SetImages` przed dodaniem przycisków do grupy. Liczba obrazów musi być większa lub równa liczbie przycisków, które mają zostać dodane do grupy.

> [!NOTE]
> Obrazy są wyświetlane, gdy użytkownik umieści wskaźnik myszy nad przyciskiem. Wyłączone obrazy są obrazami wyświetlanymi, gdy przycisk jest wyłączony.

## <a name="cmfcribbonbuttonsgroupsetparentcategory"></a><a name="setparentcategory"></a> CMFCRibbonButtonsGroup::SetParentCategory

Ustawia element nadrzędny `CMFCRibbonCategory` `CMFCRibbonButtonsGroup` obiektu i wszystkie znajdujące się w nim przyciski.

```
virtual void SetParentCategory(CMFCRibbonCategory* pCategory);
```

### <a name="parameters"></a>Parametry

*pCategory*<br/>
podczas Wskaźnik do kategorii nadrzędnej do ustawienia (grupy z kartami w kontrolkach wstążki są nazywane kategoriami).

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)

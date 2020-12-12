---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonComboBox'
title: Klasa CMFCRibbonComboBox
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
ms.openlocfilehash: be4078145817d06fafddb76f2cefbd0df0083503
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293669"
---
# <a name="cmfcribboncombobox-class"></a>Klasa CMFCRibbonComboBox

`CMFCRibbonComboBox`Klasa implementuje formant pola kombi, który można dodać do paska wstążki, panelu wstążki lub menu podręcznego wstążki.

## <a name="syntax"></a>Składnia

```cpp
class CMFCRibbonComboBox : public CMFCRibbonEdit
```

## <a name="members"></a>Elementy członkowskie

### <a name="constructors"></a>Konstruktory

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|Konstruuje obiekt CMFCRibbonComboBox.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonComboBox:: AddItem](#additem)|Dołącza unikatowy element do pola listy.|
|[CMFCRibbonComboBox::D eleteItem](#deleteitem)|Usuwa określony element z pola listy.|
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|Określa, czy pole listy może zmieniać rozmiar, gdy zostanie on porzucany.|
|[CMFCRibbonComboBox::FindItem](#finditem)|Zwraca indeks pierwszego elementu w polu listy, który pasuje do określonego ciągu.|
|[CMFCRibbonComboBox:: GetCount](#getcount)|Zwraca liczbę elementów w polu listy.|
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Pobiera indeks aktualnie wybranego elementu w polu listy.|
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Pobiera wysokość pola listy, gdy pole listy zostanie usunięte.|
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Zwraca rozmiar pola kombi wyświetlanego w trybie pośrednim.|
|[CMFCRibbonComboBox:: GetItem](#getitem)|Zwraca ciąg skojarzony z elementem w określonym indeksie w polu listy.|
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Zwraca dane skojarzone z elementem w określonym indeksie w polu listy.|
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Wskazuje, czy kontrolka zawiera pole edycji.|
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|Wskazuje, czy można zmienić rozmiar pola listy.|
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Wywoływane przez platformę, gdy użytkownik wybierze element w polu listy.|
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Usuwa wszystkie elementy z pola listy i czyści pole edycji.|
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Wybiera element w polu listy.|
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Ustawia wysokość pola listy, gdy zostanie ono usunięte.|

## <a name="remarks"></a>Uwagi

Pole kombi wstążki składa się z pola listy połączonego z etykietą statyczną lub etykietą, która może być edytowana przez użytkownika. Należy określić typ, który ma być używany podczas tworzenia pola kombi wstążki.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania obiektu `CMFCRibbonComboBox` klasy, Dodawanie elementu do pola kombi, Zaznaczanie elementu w polu kombi i Dodawanie pola kombi do panelu.

[!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxribboncombobox. h

## <a name="cmfcribboncomboboxadditem"></a><a name="additem"></a> CMFCRibbonComboBox:: AddItem

Dołącza unikatowy element do pola listy.

```cpp
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parametry

*lpszItem*<br/>
podczas Ciąg elementu do dodania.

*dwData*<br/>
podczas Dane skojarzone z elementem do dodania.

### <a name="return-value"></a>Wartość zwracana

Indeks (liczony od zera) dołączonego elementu.

## <a name="cmfcribboncomboboxcmfcribboncombobox"></a><a name="cmfcribboncombobox"></a> CMFCRibbonComboBox::CMFCRibbonComboBox

Konstruuje `CMFCRibbonComboBox` obiekt.

```cpp
public:
CMFCRibbonComboBox(
    UINT nID,
    BOOL bHasEditBox=TRUE,
    Int nWidth=-1,
    LPCTSTR lpszLabel=NULL,
    Int nImage=-1);

protected:
CMFCRibbonComboBox();
```

### <a name="parameters"></a>Parametry

*nID*<br/>
podczas Identyfikator pola kombi.

*bHasEditBox*<br/>
podczas PRAWDA, jeśli chcesz, aby pole edycji było w formancie; W przeciwnym razie zwraca wartość FALSE.

*nWidth*<br/>
podczas Szerokość pola kombi w pikselach; lub-1 dla szerokości domyślnej.

*lpszLabel*<br/>
podczas Etykieta wyświetlania pola kombi.

*Nokreślono*<br/>
podczas Indeks małego obrazu pola kombi.

### <a name="remarks"></a>Uwagi

Domyślna szerokość to 108 pikseli.

## <a name="cmfcribboncomboboxdeleteitem"></a><a name="deleteitem"></a> CMFCRibbonComboBox::D eleteItem

Usuwa określony element z pola listy.

```cpp
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametry

*iIndex*<br/>
podczas Indeks (liczony od zera) elementu, który ma zostać usunięty.

*dwData*<br/>
podczas Dane skojarzone z elementem, który ma zostać usunięty.

*lpszText*<br/>
podczas Ciąg elementu, który ma zostać usunięty. Jeśli istnieje wiele elementów z tym samym ciągiem, pierwszy element jest usuwany.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli określony element został usunięty; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncomboboxenabledropdownlistresize"></a><a name="enabledropdownlistresize"></a> CMFCRibbonComboBox::EnableDropDownListResize

Określa, czy pole listy może zmieniać rozmiar, gdy zostanie on porzucany.

```cpp
void EnableDropDownListResize(BOOL bEnable=FALSE);
```

### <a name="parameters"></a>Parametry

*bEnable*<br/>
podczas Wartość TRUE, aby włączyć zmianę rozmiarów; Wartość FALSE powoduje wyłączenie zmiany rozmiarów.

### <a name="remarks"></a>Uwagi

Gdy zmiana rozmiaru jest włączona, pole listy zmieni rozmiar w celu dopasowania do wyświetlanych elementów.

## <a name="cmfcribboncomboboxfinditem"></a><a name="finditem"></a> CMFCRibbonComboBox::FindItem

Zwraca indeks pierwszego elementu w polu listy, który pasuje do określonego ciągu.

```cpp
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Parametry

*lpszText*<br/>
podczas Ciąg elementu w polu listy.

### <a name="return-value"></a>Wartość zwracana

Indeks (liczony od zera) elementu; lub-1, jeśli element nie zostanie znaleziony.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncomboboxgetcount"></a><a name="getcount"></a> CMFCRibbonComboBox:: GetCount

Zwraca liczbę elementów w polu listy.

```cpp
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Wartość zwracana

Liczba elementów w polu listy lub 0, jeśli pole listy nie zawiera żadnych elementów.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncomboboxgetcursel"></a><a name="getcursel"></a> CMFCRibbonComboBox::GetCurSel

Pobiera indeks aktualnie wybranego elementu w polu listy.

```cpp
int GetCurSel() const;
```

### <a name="return-value"></a>Wartość zwracana

Indeks (liczony od zera) aktualnie zaznaczonego elementu w polu listy; lub-1, jeśli nie wybrano żadnego elementu.

## <a name="cmfcribboncomboboxgetdropdownheight"></a><a name="getdropdownheight"></a> CMFCRibbonComboBox::GetDropDownHeight

Pobiera wysokość pola listy, gdy pole listy zostanie usunięte.

```cpp
int GetDropDownHeight();
```

### <a name="return-value"></a>Wartość zwracana

Wysokość pola listy w pikselach.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncomboboxgetintermediatesize"></a><a name="getintermediatesize"></a> CMFCRibbonComboBox::GetIntermediateSize

Zwraca rozmiar pola kombi wyświetlanego w trybie pośrednim.

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia dla pola kombi.

### <a name="return-value"></a>Wartość zwracana

Rozmiar pola kombi.

### <a name="remarks"></a>Uwagi

Zwrócony rozmiar jest oparty na rozmiarze pola kombi, gdy wyświetla małe obrazy.

## <a name="cmfcribboncomboboxgetitem"></a><a name="getitem"></a> CMFCRibbonComboBox:: GetItem

Zwraca ciąg skojarzony z elementem w określonym indeksie w polu listy.

```cpp
LPCTSTR GetItem(int iIndex) const;
```

### <a name="parameters"></a>Parametry

*iIndex*<br/>
podczas Indeks (liczony od zera) elementu w polu listy.

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do ciągu, który jest skojarzony z elementem; w przeciwnym razie wartość NULL, jeśli parametr index jest nieprawidłowy, lub jeśli parametr index to-1 i nie wybrano elementu w polu kombi.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncomboboxgetitemdata"></a><a name="getitemdata"></a> CMFCRibbonComboBox::GetItemData

Zwraca dane skojarzone z elementem w określonym indeksie w polu listy.

```cpp
DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Parametry

*iIndex*<br/>
podczas Indeks (liczony od zera) elementu w polu listy.

### <a name="return-value"></a>Wartość zwracana

Dane skojarzone z elementem; lub 0, jeśli element nie istnieje, lub jeśli parametr index ma wartość-1, a w polu listy nie ma wybranego elementu.

## <a name="cmfcribboncomboboxhaseditbox"></a><a name="haseditbox"></a> CMFCRibbonComboBox::HasEditBox

Wskazuje, czy kontrolka zawiera pole edycji.

```cpp
BOOL HasEditBox() const;
```

### <a name="return-value"></a>Wartość zwracana

TRUE, Jeśli kontrolka zawiera pole edycji; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncomboboxisresizedropdownlist"></a><a name="isresizedropdownlist"></a> CMFCRibbonComboBox::IsResizeDropDownList

Wskazuje, czy można zmienić rozmiar pola listy.

```cpp
BOOL IsResizeDropDownList() const;
```

### <a name="return-value"></a>Wartość zwracana

Wartość TRUE, jeśli można zmienić rozmiar pola listy; w przeciwnym razie FALSE. [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)

### <a name="remarks"></a>Uwagi

Można włączyć zmianę rozmiarów pola listy przy użyciu metody [CMFCRibbonComboBox:: EnableDropDownListResize](#enabledropdownlistresize) .

## <a name="cmfcribboncomboboxonselectitem"></a><a name="onselectitem"></a> CMFCRibbonComboBox::OnSelectItem

Wywoływane przez platformę, gdy użytkownik wybierze element w polu listy.

```cpp
virtual void OnSelectItem(int nItem);
```

### <a name="parameters"></a>Parametry

*nItem*<br/>
podczas Indeks wybranego elementu.

### <a name="remarks"></a>Uwagi

Zastąp tę metodę, jeśli chcesz przetworzyć wybór danych wejściowych użytkownika.

## <a name="cmfcribboncomboboxremoveallitems"></a><a name="removeallitems"></a> CMFCRibbonComboBox::RemoveAllItems

Usuwa wszystkie elementy z pola listy i czyści pole edycji.

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncomboboxselectitem"></a><a name="selectitem"></a> CMFCRibbonComboBox::SelectItem

Wybiera element w polu listy.

```cpp
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametry

*iIndex*<br/>
podczas Indeks (liczony od zera) elementu w polu listy.

*dwData*<br/>
podczas Dane skojarzone z elementem w polu listy.

*lpszText*<br/>
podczas Ciąg elementu w polu listy.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli metoda zakończyła się pomyślnie. w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

## <a name="cmfcribboncomboboxsetdropdownheight"></a><a name="setdropdownheight"></a> CMFCRibbonComboBox::SetDropDownHeight

Ustawia wysokość pola listy, gdy zostanie ono usunięte.

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Parametry

*nHeight*<br/>
podczas Wysokość pola listy w pikselach.

### <a name="remarks"></a>Uwagi

Domyślna wysokość to 150 pikseli.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

---
description: 'Dowiedz się więcej na temat: Klasa CMFCHeaderCtrl'
title: Klasa CMFCHeaderCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
helpviewer_keywords:
- CMFCHeaderCtrl [MFC], CMFCHeaderCtrl
- CMFCHeaderCtrl [MFC], EnableMultipleSort
- CMFCHeaderCtrl [MFC], GetColumnState
- CMFCHeaderCtrl [MFC], GetSortColumn
- CMFCHeaderCtrl [MFC], IsAscending
- CMFCHeaderCtrl [MFC], IsDialogControl
- CMFCHeaderCtrl [MFC], IsMultipleSort
- CMFCHeaderCtrl [MFC], RemoveSortColumn
- CMFCHeaderCtrl [MFC], SetSortColumn
- CMFCHeaderCtrl [MFC], OnDrawItem
- CMFCHeaderCtrl [MFC], OnDrawSortArrow
- CMFCHeaderCtrl [MFC], OnFillBackground
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
ms.openlocfilehash: a6be476e095dc4a013705657e259a90d7cafe0d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265379"
---
# <a name="cmfcheaderctrl-class"></a>Klasa CMFCHeaderCtrl

`CMFCHeaderCtrl`Klasa obsługuje sortowanie wielu kolumn w kontrolce nagłówka.

## <a name="syntax"></a>Składnia

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|Konstruuje `CMFCHeaderCtrl` obiekt.|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|Włącza lub wyłącza tryb *sortowania wielu kolumn* dla bieżącego formantu nagłówka.|
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|Wskazuje, czy kolumna nie jest posortowana, czy jest sortowana w kolejności rosnącej czy malejącej.|
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|Pobiera indeks (liczony od zera) pierwszej posortowanej kolumny w kontrolce nagłówka.|
|`CMFCHeaderCtrl::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|
|[CMFCHeaderCtrl:: isascending](#isascending)|Wskazuje, czy jakakolwiek kolumna w formancie nagłówka jest posortowana w kolejności rosnącej.|
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|Wskazuje, czy okno nadrzędne bieżącego formantu nagłówka jest oknem dialogowym.|
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|Wskazuje, czy bieżący formant nagłówka jest w trybie *sortowania wielu kolumn* .|
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|Usuwa określoną kolumnę z listy kolumn sortowania.|
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|Ustawia kolejność sortowania określonej kolumny w kontrolce nagłówka.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|Wywoływane przez platformę, aby narysować kolumnę kontrolki nagłówka.|
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|Wywoływane przez platformę, by narysować strzałkę sortowania.|
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|Wywoływane przez platformę, by wypełnić tło kolumny kontrolki nagłówka.|

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania obiektu `CMFCHeaderCtrl` klasy oraz sposób włączania *wielu kolumn tryb sortowania* dla bieżącego formantu nagłówka.

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>Uwagi

`CMFCHeaderCtrl`Klasa rysuje strzałkę sortowania w kolumnie kontrolki nagłówka, aby wskazać, że kolumna jest posortowana. Użyj trybu *sortowania wielu kolumn* , jeśli zestaw kolumn w kontrolce listy nadrzędnej ( [Klasa CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)) może być sortowany w tym samym czasie.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxheaderctrl. h

## <a name="cmfcheaderctrlcmfcheaderctrl"></a><a name="cmfcheaderctrl"></a> CMFCHeaderCtrl::CMFCHeaderCtrl

Konstruuje `CMFCHeaderCtrl` obiekt.

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>Uwagi

Ten konstruktor inicjuje następujące zmienne członkowskie do określonych wartości:

|Zmienna członkowska|Wartość|
|---------------------|-----------|
|`m_bIsMousePressed`|Fałsz|
|`m_bMultipleSort`|Fałsz|
|`m_bAscending`|Prawda|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|Fałsz|
|`m_bIsDlgControl`|Fałsz|
|`m_hFont`|NULL|

## <a name="cmfcheaderctrlenablemultiplesort"></a><a name="enablemultiplesort"></a> CMFCHeaderCtrl::EnableMultipleSort

Włącza lub wyłącza tryb *sortowania wielu kolumn* dla bieżącego formantu nagłówka.

```cpp
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametry

*bEnable*<br/>
podczas Wartość TRUE powoduje włączenie trybu sortowania wielu kolumn; Wartość FALSE powoduje wyłączenie trybu sortowania wielu kolumn i usunięcie wszystkich kolumn z listy posortowanych kolumn. Wartość domyślna to TRUE.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby włączyć lub wyłączyć tryb sortowania wielu kolumn. Co najmniej dwie kolumny mogą uczestniczyć w sortowaniu, Jeśli kontrolka nagłówka znajduje się w trybie sortowania wielu kolumn.

## <a name="cmfcheaderctrlgetcolumnstate"></a><a name="getcolumnstate"></a> CMFCHeaderCtrl::GetColumnState

Wskazuje, czy kolumna jest nieposortowana, czy jest sortowana w kolejności rosnącej czy malejącej.

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>Parametry

*iColumn*<br/>
podczas Indeks kolumny (liczony od zera).

### <a name="return-value"></a>Wartość zwracana

Wartość wskazująca stan sortowania określonej kolumny. Poniższa tabela zawiera listę możliwych wartości:

|Wartość|Opis|
|-----------|-----------------|
|-1|Posortowane w kolejności malejącej.|
|0|Nie posortowane.|
|1|Posortowane w kolejności rosnącej.|

### <a name="remarks"></a>Uwagi

## <a name="cmfcheaderctrlgetsortcolumn"></a><a name="getsortcolumn"></a> CMFCHeaderCtrl::GetSortColumn

Pobiera indeks (liczony od zera) pierwszej posortowanej kolumny w kontrolce nagłówka.

```
int GetSortColumn() const;
```

### <a name="return-value"></a>Wartość zwracana

Indeks posortowanej kolumny lub-1, jeśli nie zostanie znaleziona posortowana kolumna.

### <a name="remarks"></a>Uwagi

Jeśli kontrolka nagłówka znajduje się w trybie *sortowania wielu kolumn* i aplikacja została skompilowana w trybie debugowania, ta metoda potwierdza i zaleca użycie metody [CMFCHeaderCtrl:: GetColumnState](#getcolumnstate) . Jeśli kontrolka nagłówka znajduje się w trybie sortowania wielu kolumn i aplikacja została skompilowana w trybie handlu detalicznego, ta metoda zwraca wartość-1.

## <a name="cmfcheaderctrlisascending"></a><a name="isascending"></a> CMFCHeaderCtrl:: isascending

Wskazuje, czy jakakolwiek kolumna w formancie nagłówka jest posortowana w kolejności rosnącej.

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli jakakolwiek kolumna w formancie nagłówka jest posortowana w kolejności rosnącej; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Wartość zwracana przez tę metodę jest używana do wyświetlania odpowiedniej strzałki sortowania elementu formantu nagłówka. Użyj metody [CMFCHeaderCtrl:: SetSortColumn](#setsortcolumn) , aby ustawić kolejność sortowania.

## <a name="cmfcheaderctrlisdialogcontrol"></a><a name="isdialogcontrol"></a> CMFCHeaderCtrl::IsDialogControl

Wskazuje, czy okno nadrzędne bieżącego formantu nagłówka jest oknem dialogowym.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>Wartość zwracana

PRAWDA, jeśli okno nadrzędne bieżącego formantu nagłówka jest oknem dialogowym; w przeciwnym razie FALSE.

## <a name="cmfcheaderctrlismultiplesort"></a><a name="ismultiplesort"></a> CMFCHeaderCtrl::IsMultipleSort

Wskazuje, czy bieżący formant nagłówka jest w trybie *sortowania wielu kolumn* .

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli jest włączony tryb sortowania wielu kolumn; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Użyj metody [CMFCHeaderCtrl:: EnableMultipleSort](#enablemultiplesort) , aby włączyć lub wyłączyć tryb sortowania wielu kolumn. Co najmniej dwie kolumny mogą uczestniczyć w sortowaniu, Jeśli kontrolka nagłówka znajduje się w trybie sortowania wielu kolumn.

## <a name="cmfcheaderctrlondrawitem"></a><a name="ondrawitem"></a> CMFCHeaderCtrl::OnDrawItem

Wywoływane przez platformę, aby narysować kolumnę kontrolki nagłówka.

```
virtual void OnDrawItem(
    CDC* pDC,
    int iItem,
    CRect rect,
    BOOL bIsPressed,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

*iItem*<br/>
podczas Indeks (liczony od zera) elementu do narysowania.

*cinania*<br/>
podczas Prostokąt ograniczający elementu do rysowania.

*bIsPressed*<br/>
podczas Wartość TRUE, aby narysować element w stanie naciśniętym; w przeciwnym razie FALSE.

*bIsHighlighted*<br/>
podczas Wartość TRUE, aby narysować element w wyróżnionym stanie; w przeciwnym razie FALSE.

## <a name="cmfcheaderctrlondrawsortarrow"></a><a name="ondrawsortarrow"></a> CMFCHeaderCtrl::OnDrawSortArrow

Wywoływane przez platformę, by narysować strzałkę sortowania.

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

*rectArrow*<br/>
podczas Prostokąt ograniczający strzałkę sortowania.

## <a name="cmfcheaderctrlonfillbackground"></a><a name="onfillbackground"></a> CMFCHeaderCtrl::OnFillBackground

Wywoływane przez platformę, by wypełnić tło kolumny kontrolki nagłówka.

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Parametry

*Domeny*<br/>
podczas Wskaźnik do kontekstu urządzenia.

### <a name="remarks"></a>Uwagi

## <a name="cmfcheaderctrlremovesortcolumn"></a><a name="removesortcolumn"></a> CMFCHeaderCtrl::RemoveSortColumn

Usuwa określoną kolumnę z listy kolumn sortowania.

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Parametry

*iColumn*<br/>
podczas Indeks (liczony od zera) kolumny do usunięcia.

## <a name="cmfcheaderctrlsetsortcolumn"></a><a name="setsortcolumn"></a> CMFCHeaderCtrl::SetSortColumn

Ustawia kolejność sortowania określonej kolumny w kontrolce nagłówka.

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>Parametry

*iColumn*<br/>
podczas Indeks kolumn kontrolki nagłówka (liczony od zera). Jeśli ten parametr jest mniejszy od zera, ta metoda usuwa wszystkie kolumny z listy kolumn sortowania.

*bAscending*<br/>
podczas Określa kolejność sortowania kolumny określanej przez parametr *IColumn* . Wartość TRUE powoduje ustawienie kolejności rosnącej; Wartość FALSE powoduje ustawienie kolejności malejącej. Wartość domyślna to TRUE.

*bDodaj*<br/>
podczas Wartość TRUE powoduje ustawienie kolejności sortowania kolumny określanej przez parametr *IColumn* .

Jeśli bieżący formant nagłówka znajduje się w trybie *sortowania wielu kolumn* , ta metoda dodaje określoną kolumnę do listy kolumn sortowania. Użyj [CMFCHeaderCtrl:: EnableMultipleSort](#enablemultiplesort) , aby ustawić wiele kolumn trybu sortowania.

Jeśli tryb sortowania wielu kolumn nie jest ustawiony i ta metoda jest kompilowana w trybie debugowania, ta metoda zostanie potwierdzona. Jeśli nie ustawiono trybu sortowania wielu kolumn i ta metoda jest skompilowana w trybie sprzedaży detalicznej, ta metoda najpierw usunie wszystkie kolumny z listy kolumn sortowania, a następnie doda określoną kolumnę do listy.

Wartość FALSE, aby najpierw usunąć wszystkie kolumny z listy kolumn sortowania, a następnie dodać określoną kolumnę do listy. Wartość domyślna to FALSE.

### <a name="remarks"></a>Uwagi

Użyj tej metody, aby ustawić kolejność sortowania kolumny. W razie potrzeby ta metoda dodaje kolumnę do listy kolumn sortowania. Kontrolka nagłówka używa porządku sortowania, aby narysować strzałkę sortowania wskazującą w górę lub w dół.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

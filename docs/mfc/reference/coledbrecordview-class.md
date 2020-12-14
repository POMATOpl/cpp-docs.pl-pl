---
description: 'Dowiedz się więcej na temat: Klasa COleDBRecordView'
title: Klasa COleDBRecordView
ms.date: 11/04/2016
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
helpviewer_keywords:
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
ms.openlocfilehash: bce03a482aff558ed6d22c7720ff74f304a9214f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227315"
---
# <a name="coledbrecordview-class"></a>Klasa COleDBRecordView

Widok, w którym są wyświetlane rekordy bazy danych w kontrolkach.

## <a name="syntax"></a>Składnia

```
class COleDBRecordView : public CFormView
```

## <a name="members"></a>Elementy członkowskie

### <a name="protected-constructors"></a>Konstruktory chronione

|Nazwa|Opis|
|----------|-----------------|
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|Konstruuje `COleDBRecordView` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleDBRecordView::OnGetRowset](#ongetrowset)|Zwraca standardową wartość HRESULT.|
|[COleDBRecordView:: OnMove](#onmove)|Aktualizuje bieżący rekord (jeśli jest zanieczyszczony) w źródle danych, a następnie przechodzi do określonego rekordu (Następny, poprzedni, pierwszy lub ostatni).|

## <a name="remarks"></a>Uwagi

Widok to widok formularza połączony bezpośrednio z `CRowset` obiektem. Widok jest tworzony na podstawie zasobu szablonu okna dialogowego i wyświetla pola `CRowset` obiektu w kontrolkach szablonu okna dialogowego. `COleDBRecordView`Obiekt używa wymiany danych okna dialogowego (DDX) oraz funkcji nawigacyjnych wbudowanych w `CRowset` program, aby zautomatyzować przenoszenie danych między kontrolkami w formularzu i polami zestawu wierszy. `COleDBRecordView` dostarcza również domyślną implementację do przechodzenia do pierwszego, następnego, poprzedniego lub ostatniego rekordu oraz interfejs do aktualizowania rekordu aktualnie w widoku.

Możesz użyć funkcji DDX with, `COleDbRecordView` Aby pobrać dane bezpośrednio z zestawu rekordów bazy danych i wyświetlić je w kontrolce okna dialogowego. Należy używać `DDX_*` metod (takich jak `DDX_Text` ), a nie `DDX_Field*` funkcji (takich jak `DDX_FieldText` ) z `COleDbRecordView` . `DDX_FieldText` nie będzie działał z, `COleDbRecordView` ponieważ `DDX_FieldText` Pobiera dodatkowy argument typu `CRecordset*` (for `CRecordView` ) lub `CDaoRecordset*` (dla `CDaoRecordView` ).

> [!NOTE]
> Jeśli pracujesz z klasami obiektów dostępu do danych (DAO), a nie OLE DB klas szablonów konsumentów, zamiast tego użyj klasy [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) . Aby uzyskać więcej informacji, zobacz [Omówienie artykułu: Programowanie baz danych](../../data/data-access-programming-mfc-atl.md).

`COleDBRecordView` śledzi położenie użytkownika w zestawie wierszy, aby widok rekordu mógł zaktualizować interfejs użytkownika. Gdy użytkownik przejdzie do dowolnego końca zestawu wierszy, widok rekordu wyłącza obiekty interfejsu użytkownika, takie jak elementy menu lub przyciski paska narzędzi — do przenoszenia dalej w tym samym kierunku.

Aby uzyskać więcej informacji na temat klas zestawów wierszy, zobacz artykuł [Using OLE DB — szablony klientów](../../data/oledb/ole-db-consumer-templates-cpp.md) .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`COleDBRecordView`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxoledb. h

## <a name="coledbrecordviewcoledbrecordview"></a><a name="coledbrecordview"></a> COleDBRecordView::COleDBRecordView

Konstruuje `COleDBRecordView` obiekt.

```
COleDBRecordView(LPCTSTR lpszTemplateName);
COleDBRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>Parametry

*lpszTemplateName*<br/>
Zawiera ciąg zakończony znakiem null, który jest nazwą zasobu szablonu okna dialogowego.

*nIDTemplate*<br/>
Zawiera numer IDENTYFIKACYJNy zasobu szablonu okna dialogowego.

### <a name="remarks"></a>Uwagi

Podczas tworzenia obiektu typu pochodnego `COleDBRecordView` wywoływanie jednego z konstruktorów w celu utworzenia obiektu widoku i zidentyfikowania zasobu okna dialogowego, w którym jest oparty ten widok. Zasób można zidentyfikować według nazwy (przekazać ciąg jako argument do konstruktora) lub według jego identyfikatora (przekazać jako argument liczbę całkowitą bez znaku).

> [!NOTE]
> Klasa pochodna *musi* dostarczyć własnego konstruktora. W konstruktorze Wywołaj konstruktora, `COleDBRecordView::COleDBRecordView` przy użyciu nazwy zasobu lub identyfikatora jako argumentu.

## <a name="coledbrecordviewongetrowset"></a><a name="ongetrowset"></a> COleDBRecordView::OnGetRowset

Zwraca dojście dla obiektu **CRowset<>** skojarzonego z widokiem rekordu.

```
virtual CRowset<>* OnGetRowset() = 0;
```

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

Należy przesłonić tę funkcję elementu członkowskiego, aby skonstruować lub uzyskać obiekt zestawu wierszy i zwrócić do niego uchwyt. Jeśli zadeklarujesz klasę widoku rekordu przy użyciu ClassWizard, Kreator zapisze domyślne przesłonięcie. Domyślna implementacja ClassWizard zwraca dojście zestawu wierszy przechowywane w widoku rekordu, jeśli taki istnieje. Jeśli nie, konstruuje obiekt zestawu wierszy typu określonego za pomocą ClassWizard i wywołuje jego `Open` funkcję członkowską, aby otworzyć tabelę lub uruchomić zapytanie, a następnie zwraca dojście do obiektu.

> [!NOTE]
> Poprzedni do MFC 7,0, `OnGetRowset` zwrócił wskaźnik do `CRowset` . Jeśli masz kod, który wywołuje `OnGetRowset` , musisz zmienić zwracany typ na klasę Szablonowana **CRowset<>**.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

Aby uzyskać więcej informacji i przykładów, zobacz widok [rekordu artykułu: Używanie widoku rekordu](../../data/using-a-record-view-mfc-data-access.md).

## <a name="coledbrecordviewonmove"></a><a name="onmove"></a> COleDBRecordView:: OnMove

Przenosi do innego rekordu w zestawie wierszy i wyświetla jego pola w kontrolkach widoku rekordu.

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>Parametry

*nIDMoveCommand*<br/>
Jedna z następujących wartości identyfikatora polecenia standardowego:

- ID_RECORD_FIRST — przejdź do pierwszego rekordu w zestawie rekordów.

- ID_RECORD_LAST — przejdź do ostatniego rekordu w zestawie rekordów.

- ID_RECORD_NEXT — przejdź do następnego rekordu w zestawie rekordów.

- ID_RECORD_PREV — przejdź do poprzedniego rekordu w zestawie rekordów.

### <a name="return-value"></a>Wartość zwracana

Niezerowe, jeśli przenoszenie zakończyło się pomyślnie; w przeciwnym razie wartość 0, jeśli żądanie przeniesienia zostało odrzucone.

### <a name="remarks"></a>Uwagi

Domyślna implementacja wywołuje odpowiednią `Move` funkcję elementu członkowskiego `CRowset` obiektu skojarzonego z widokiem rekordu.

Domyślnie program `OnMove` aktualizuje bieżący rekord w źródle danych, jeśli użytkownik zmienił go w widoku rekordu.

Kreator aplikacji tworzy zasób menu z elementami menu pierwszy rekord, ostatni rekord, następny rekord i poprzedni rekord. W przypadku wybrania opcji paska narzędzi było dokować Kreator aplikacji utworzy również pasek narzędzi z przyciskami odpowiadającymi tym poleceniem.

W przypadku przeniesienia ostatniego rekordu w zestawie rekordów widok rekordu będzie nadal wyświetlał ostatni rekord. W przypadku przeniesienia do tyłu pierwszego rekordu widok rekordu będzie nadal wyświetlał pierwszy rekord.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)

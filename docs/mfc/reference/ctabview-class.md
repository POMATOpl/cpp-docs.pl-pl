---
description: 'Dowiedz się więcej na temat: Klasa CTabView'
title: Klasa CTabView
ms.date: 11/04/2016
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
helpviewer_keywords:
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
ms.openlocfilehash: 59d4169bae108575fcf4844ec7c5c6e1e6681e28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345059"
---
# <a name="ctabview-class"></a>Klasa CTabView

`CTabView`Klasa upraszcza korzystanie z klasy formantu karty ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) w aplikacjach korzystających ze architektury dokumentu/widoku MFC.

## <a name="syntax"></a>Składnia

```
class CTabbedView : public CView
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CTabView:: AddView](#addview)|Dodaje nowy widok do kontrolki karta.|
|[CTabView::FindTab](#findtab)|Zwraca indeks określonego widoku w kontrolce karty.|
|[CTabView::GetActiveView](#getactiveview)|Zwraca wskaźnik do aktualnie aktywnego widoku|
|[CTabView:: GetTabControl](#gettabcontrol)|Zwraca odwołanie do kontrolki karta skojarzonej z widokiem.|
|[CTabView::RemoveView](#removeview)|Usuwa widok z kontrolki karta.|
|[CTabView::SetActiveView](#setactiveview)|Sprawia, że widok jest aktywny.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CTabView:: IsScrollBar](#isscrollbar)|Wywoływane przez platformę podczas tworzenia widoku karty, aby określić, czy widok karty ma współużytkowany poziomy pasek przewijania.|
|[CTabView:: OnActivateView](#onactivateview)|Wywoływane przez platformę, gdy widok karty jest aktywny lub nieaktywny.|

## <a name="remarks"></a>Uwagi

Ta klasa ułatwia umieszczenie widoku z kartami w aplikacji dokumentu/widoku. `CTabView` jest `CView` klasą pochodną, która zawiera osadzony `CMFCTabCtrl` obiekt. `CTabView` obsługuje wszystkie komunikaty wymagane do obsługi `CMFCTabCtrl` obiektu. Po prostu Utwórz klasę z `CTabView` i podłącz ją do swojej aplikacji, a następnie Dodaj `CView` klasy pochodne przy użyciu `AddView` metody. Kontrolki karty będą wyświetlały te widoki jako karty.

Na przykład może istnieć dokument, który może być reprezentowany na różne sposoby: w postaci arkusza kalkulacyjnego, wykresu, formularza do edycji itd. W razie potrzeby można utworzyć poszczególne widoki rysowania danych, wstawić je do `CTabView` obiektu pochodnego i umieścić je na kartach bez żadnego dodatkowego kodowania.

[Przykład TabbedView: aplikacja widoku z kartami MFC](../../overview/visual-cpp-samples.md) ilustruje użycie `CTabView` .

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak `CTabView` jest używany w próbce TabbedView.

[!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxTabView. h

## <a name="ctabviewaddview"></a><a name="addview"></a> CTabView:: AddView

Dodaje widok do kontrolki karta.

```
int AddView(
    CRuntimeClass* pViewClass,
    const CString& strViewLabel,
    int iIndex=-1,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>Parametry

*pViewClass*<br/>
podczas Wskaźnik do klasy środowiska uruchomieniowego wstawionego widoku.

*strViewLabel*<br/>
podczas Określa tekst tabulacji.

*iIndex*<br/>
podczas Określa pozycję od zera, w której ma zostać wstawiony widok. Jeśli pozycja to-1, Nowa karta zostanie wstawiona na końcu.

*pContext*<br/>
podczas Wskaźnik do `CCreateContext` widoku.

### <a name="return-value"></a>Wartość zwracana

Indeks widoku, jeśli ta metoda zakończy się pomyślnie. W przeciwnym razie-1.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby dodać widok do kontrolki karta, która jest osadzona w ramce.

## <a name="ctabviewfindtab"></a><a name="findtab"></a> CTabView::FindTab

Zwraca indeks określonego widoku w kontrolce karty.

```
int FindTab(HWND hWndView) const;
```

### <a name="parameters"></a>Parametry

*hWndView*<br/>
podczas Uchwyt widoku.

### <a name="return-value"></a>Wartość zwracana

Indeks widoku, jeśli zostanie znaleziony; w przeciwnym razie-1.

### <a name="remarks"></a>Uwagi

Wywołaj tę funkcję, aby pobrać indeks widoku, który ma określone dojście.

## <a name="ctabviewgetactiveview"></a><a name="getactiveview"></a> CTabView::GetActiveView

Zwraca wskaźnik do aktualnie aktywnego widoku.

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Wartość zwracana

Prawidłowy wskaźnik do aktywnego widoku lub wartość NULL, jeśli nie ma aktywnego widoku.

### <a name="remarks"></a>Uwagi

## <a name="ctabviewgettabcontrol"></a><a name="gettabcontrol"></a> CTabView:: GetTabControl

Zwraca odwołanie do kontrolki karta skojarzonej z widokiem.

```
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do kontrolki karta skojarzonej z widokiem.

## <a name="ctabviewisscrollbar"></a><a name="isscrollbar"></a> CTabView:: IsScrollBar

Wywoływane przez platformę podczas tworzenia widoku karty, aby określić, czy widok karty ma współużytkowany poziomy pasek przewijania.

```
virtual BOOL IsScrollBar() const;
```

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli widok karty powinien być utworzony razem z udostępnionym paskiem przewijania. W przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Struktura wywołuje tę metodę, gdy tworzony jest obiekt *CTabView* .

Zastąp metodę *IsScrollBar* w klasie pochodnej *CTabView* i zwróć wartość true, jeśli chcesz utworzyć widok, który ma współużytkowany poziomy pasek przewijania.

## <a name="ctabviewonactivateview"></a><a name="onactivateview"></a> CTabView:: OnActivateView

Wywoływane przez platformę, gdy widok karty jest aktywny lub nieaktywny.

```
virtual void OnActivateView(CView* view);
```

### <a name="parameters"></a>Parametry

*widokiem*<br/>
podczas Wskaźnik do widoku.

### <a name="remarks"></a>Uwagi

Domyślna implementacja nie robi nic. Zastąp tę metodę w `CTabView` klasie pochodnej, aby przetworzyć to powiadomienie.

## <a name="ctabviewremoveview"></a><a name="removeview"></a> CTabView::RemoveView

Usuwa widok z kontrolki karta.

```
BOOL RemoveView(int iTabNum);
```

### <a name="parameters"></a>Parametry

*iTabNum*<br/>
podczas Indeks widoku do usunięcia.

### <a name="return-value"></a>Wartość zwracana

Indeks usuniętego widoku, jeśli ta metoda zakończy się pomyślnie. W przeciwnym razie-1.

### <a name="remarks"></a>Uwagi

## <a name="ctabviewsetactiveview"></a><a name="setactiveview"></a> CTabView::SetActiveView

Sprawia, że widok jest aktywny.

```
BOOL SetActiveView(int iTabNum);
```

### <a name="parameters"></a>Parametry

*iTabNum*<br/>
podczas Indeks (liczony od zera) widoku karty.

### <a name="return-value"></a>Wartość zwracana

Ma wartość TRUE, jeśli określony widok został uaktywniony, wartość FALSE, jeśli indeks widoku jest nieprawidłowy.

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [CMFCTabCtrl:: SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTabCtrl](../../mfc/reference/ctabview-class.md)<br/>
[Klasa CView](../../mfc/reference/cview-class.md)

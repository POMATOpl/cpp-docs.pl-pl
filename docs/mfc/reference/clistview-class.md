---
description: 'Dowiedz się więcej na temat: Klasa CListView'
title: Klasa CListView
ms.date: 11/04/2016
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
ms.openlocfilehash: 5576a0997c84e8f5639911a1120a6645e720a7cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259568"
---
# <a name="clistview-class"></a>Klasa CListView

Upraszcza korzystanie z kontrolki list i [CListCtrl](../../mfc/reference/clistctrl-class.md), klasy, która hermetyzuje funkcje kontrolki listy z architekturą widoku dokumentu MFC.

## <a name="syntax"></a>Składnia

```
class CListView : public CCtrlView
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CListView:: CListView](#clistview)|Konstruuje `CListView` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CListView:: funkcji GetListCtrl](#getlistctrl)|Zwraca kontrolkę listy skojarzoną z widokiem.|

### <a name="protected-methods"></a>Metody chronione

|Nazwa|Opis|
|----------|-----------------|
|[CListView:: RemoveImageList](#removeimagelist)|Usuwa określoną listę obrazów z widoku listy.|

## <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat tej architektury, zobacz Omówienie klasy [CView](../../mfc/reference/cview-class.md) i odsyłaczy w tym miejscu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxcview. h

## <a name="clistviewclistview"></a><a name="clistview"></a> CListView:: CListView

Konstruuje `CListView` obiekt.

```
CListView();
```

## <a name="clistviewgetlistctrl"></a><a name="getlistctrl"></a> CListView:: funkcji GetListCtrl

Wywołaj tę funkcję elementu członkowskiego, aby uzyskać odwołanie do kontrolki listy skojarzonej z widokiem.

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>Wartość zwracana

Odwołanie do kontrolki listy skojarzonej z widokiem.

### <a name="example"></a>Przykład

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

## <a name="clistviewremoveimagelist"></a><a name="removeimagelist"></a> CListView:: RemoveImageList

Usuwa określoną listę obrazów z widoku listy.

```cpp
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>Parametry

*nImageList*<br/>
Indeks (liczony od zera) obrazu do usunięcia.

## <a name="see-also"></a>Zobacz też

[Przykład ROWLIST MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CCtrlView](../../mfc/reference/cctrlview-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CCtrlView](../../mfc/reference/cctrlview-class.md)

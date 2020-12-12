---
description: 'Dowiedz się więcej na temat: Klasa COleResizeBar'
title: Klasa COleResizeBar
ms.date: 11/04/2016
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
ms.openlocfilehash: bdd97e854257e2f858b52ed45f4066b26c71394d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226717"
---
# <a name="coleresizebar-class"></a>Klasa COleResizeBar

Typ paska sterowania, który obsługuje zmienianie rozmiarów elementów OLE w miejscu.

## <a name="syntax"></a>Składnia

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleResizeBar:: COleResizeBar](#coleresizebar)|Konstruuje `COleResizeBar` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleResizeBar:: Create](#create)|Tworzy i inicjuje okno podrzędne systemu Windows i kojarzy je z `COleResizeBar` obiektem.|

## <a name="remarks"></a>Uwagi

`COleResizeBar` obiekty są wyświetlane jako [CRectTracker](../../mfc/reference/crecttracker-class.md) z obramowaniem kreskowanym i zewnętrznymi uchwytami zmiany rozmiaru.

`COleResizeBar` obiekty są zwykle osadzonymi elementami członkowskimi obiektów okien ramowych pochodnych z klasy [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) .

Aby uzyskać więcej informacji, zobacz [Aktywacja](../../mfc/activation-cpp.md)artykułu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Afxole. h

## <a name="coleresizebarcoleresizebar"></a><a name="coleresizebar"></a> COleResizeBar:: COleResizeBar

Konstruuje `COleResizeBar` obiekt.

```
COleResizeBar();
```

### <a name="remarks"></a>Uwagi

Wywołaj `Create` , aby utworzyć obiekt paska zmiany rozmiaru.

## <a name="coleresizebarcreate"></a><a name="create"></a> COleResizeBar:: Create

Tworzy okno podrzędne i kojarzy je z `COleResizeBar` obiektem.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>Parametry

*pParentWnd*<br/>
Wskaźnik do okna nadrzędnego paska zmiany rozmiaru.

*dwStyle*<br/>
Określa atrybuty [stylu okna](../../mfc/reference/styles-used-by-mfc.md#window-styles) .

*nID*<br/>
Identyfikator okna podrzędnego zmiana rozmiaru paska.

### <a name="return-value"></a>Wartość zwracana

Różne od zera, jeśli pasek zmiany rozmiaru został utworzony; w przeciwnym razie 0.

## <a name="see-also"></a>Zobacz też

[Przykład SUPERPAD MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa CControlBar](../../mfc/reference/ccontrolbar-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa COleServerDoc](../../mfc/reference/coleserverdoc-class.md)

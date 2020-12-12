---
description: 'Dowiedz się więcej na temat: Klasa CDialogEx'
title: Klasa CDialogEx
ms.date: 11/04/2016
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
ms.openlocfilehash: 27ec0011935871d472734cae6f0d62b402382727
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185248"
---
# <a name="cdialogex-class"></a>Klasa CDialogEx

`CDialogEx`Klasa określa kolor tła i obraz tła okna dialogowego.

## <a name="syntax"></a>Składnia

```
class CDialogEx : public CDialog
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDialogEx::CDialogEx](#cdialogex)|Konstruuje `CDialogEx` obiekt.|
|`CDialogEx::~CDialogEx`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|Ustawia kolor tła okna dialogowego.|
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|Ustawia obraz tła okna dialogowego.|

## <a name="remarks"></a>Uwagi

Aby użyć `CDialogEx` klasy, należy utworzyć klasę okna dialogowego z klasy, `CDialogEx` a nie `CDialog` klasy.

Obrazy okna dialogowego są przechowywane w pliku zasobów. Struktura automatycznie usuwa wszystkie obrazy, które są ładowane z pliku zasobów. Aby programowo usunąć bieżący obraz tła, wywołaj metodę [CDialogEx:: SetBackgroundImage](#setbackgroundimage) lub Zaimplementuj `OnDestroy` procedurę obsługi zdarzeń. Gdy wywołasz metodę [CDialogEx:: SetBackgroundImage](#setbackgroundimage) , Przekaż `HBITMAP` parametr jako uchwyt obrazu. Obiekt przejdzie `CDialogEx` na własność obrazu i usunie go, jeśli `m_bAutoDestroyBmp` flaga jest `TRUE` .

`CDialogEx`Obiekt może być elementem nadrzędnym obiektu [klasy CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) . Obiekt [klasy CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) wywołuje metodę, `CDialogEx::SetActiveMenu` gdy zostanie otwarty obiekt [klasy CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) . Następnie `CDialogEx` obiekt obsługuje wszystkie zdarzenia menu do momentu zamknięcia obiektu [klasy CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdialogex. h

## <a name="cdialogexcdialogex"></a><a name="cdialogex"></a> CDialogEx::CDialogEx

Konstruuje `CDialogEx` obiekt.

```
CDialogEx(
    UINT nIDTemplate,
    CWnd* pParent=NULL);

CDialogEx(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd=NULL);
```

### <a name="parameters"></a>Parametry

*nIDTemplate*<br/>
podczas Identyfikator zasobu szablonu okna dialogowego.

*lpszTemplateName*<br/>
podczas Nazwa zasobu szablonu okna dialogowego.

*pParent*<br/>
podczas Wskaźnik do okna nadrzędnego. Wartość domyślna to NULL.

*pParentWnd*<br/>
podczas Wskaźnik do okna nadrzędnego. Wartość domyślna to NULL.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cdialogexsetbackgroundcolor"></a><a name="setbackgroundcolor"></a> CDialogEx::SetBackgroundColor

Ustawia kolor tła okna dialogowego.

```cpp
void SetBackgroundColor(
    COLORREF color,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Parametry

*Kolor*<br/>
podczas Wartość koloru RGB.

*bRepaint*<br/>
podczas Wartość TRUE, aby natychmiast zaktualizować ekran; w przeciwnym razie FALSE. Wartość domyślna to TRUE.

### <a name="remarks"></a>Uwagi

## <a name="cdialogexsetbackgroundimage"></a><a name="setbackgroundimage"></a> CDialogEx::SetBackgroundImage

Ustawia obraz tła okna dialogowego.

```cpp
void SetBackgroundImage(
    HBITMAP hBitmap,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bAutoDestroy=TRUE,
    BOOL bRepaint=TRUE);

BOOL SetBackgroundImage(
    UINT uiBmpResId,
    BackgroundLocation location=BACKGR_TILE,
    BOOL bRepaint=TRUE);
```

### <a name="parameters"></a>Parametry

*hBitmap*<br/>
podczas Uchwyt do obrazu tła.

*uiBmpResId*<br/>
podczas Identyfikator zasobu obrazu tła.

*przeniesienie*<br/>
podczas Jedna z `CDialogEx::BackgroundLocation` wartości, która określa lokalizację obrazu. Prawidłowe wartości to BACKGR_TILE, BACKGR_TOPLEFT, BACKGR_TOPRIGHT, BACKGR_BOTTOMLEFT i BACKGR_BOTTOMRIGHT. Wartość domyślna to BACKGR_TILE.

*bAutoDestroy*<br/>
podczas TRUE, aby automatycznie zniszczyć obraz tła; w przeciwnym razie FALSE.

*bRepaint*<br/>
podczas Wartość TRUE powoduje natychmiastowe ponowne narysowanie okna dialogowego; w przeciwnym razie FALSE.

### <a name="return-value"></a>Wartość zwracana

W drugiej składni przeciążenia metody wartość TRUE, jeśli metoda zakończy się pomyślnie; w przeciwnym razie FALSE.

### <a name="remarks"></a>Uwagi

Określony obraz nie jest rozciągany w celu dopasowania go do obszaru klienckiego okna dialogowego.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)<br/>
[Klasa CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)

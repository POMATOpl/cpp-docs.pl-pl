---
description: 'Dowiedz się więcej na temat: Klasa COleIPFrameWnd'
title: Klasa COleIPFrameWnd
ms.date: 11/04/2016
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
ms.openlocfilehash: d89cfa9b3f6d610276c3c972ee48c943f753e36a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227016"
---
# <a name="coleipframewnd-class"></a>Klasa COleIPFrameWnd

Podstawa okna edycji w miejscu aplikacji.

## <a name="syntax"></a>Składnia

```
class COleIPFrameWnd : public CFrameWnd
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleIPFrameWnd:: COleIPFrameWnd](#coleipframewnd)|Konstruuje `COleIPFrameWnd` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[COleIPFrameWnd:: funkcja OnCreateControlBars](#oncreatecontrolbars)|Wywoływane przez platformę, gdy element jest aktywowany do edycji w miejscu.|
|[COleIPFrameWnd:: RepositionFrame](#repositionframe)|Wywoływane przez platformę, aby zmienić położenie okna edycji w miejscu.|

## <a name="remarks"></a>Uwagi

Ta klasa tworzy i ustawia paski kontrolne w oknie dokumentu aplikacji kontenera. Obsługuje również powiadomienia generowane przez osadzony obiekt [COleResizeBar](../../mfc/reference/coleresizebar-class.md) , gdy użytkownik zmienia rozmiar okna edycji w miejscu.

Aby uzyskać więcej informacji na temat korzystania z programu `COleIPFrameWnd` , zobacz [Aktywacja](../../mfc/activation-cpp.md)artykułu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Afxole. h

## <a name="coleipframewndcoleipframewnd"></a><a name="coleipframewnd"></a> COleIPFrameWnd:: COleIPFrameWnd

Konstruuje `COleIPFrameWnd` obiekt i inicjuje informacje o stanie w miejscu, które są przechowywane w strukturze typu OLEINPLACEFRAMEINFO.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [OLEINPLACEFRAMEINFO](/windows/win32/api/oleidl/ns-oleidl-oleinplaceframeinfo) w Windows SDK.

## <a name="coleipframewndoncreatecontrolbars"></a><a name="oncreatecontrolbars"></a> COleIPFrameWnd:: funkcja OnCreateControlBars

Struktura wywołuje funkcję, `OnCreateControlBars` gdy element jest aktywowany do edycji w miejscu.

```
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,
    CWnd* pWndDoc);

virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,
    CFrameWnd* pWndDoc);
```

### <a name="parameters"></a>Parametry

*pWndFrame*<br/>
Wskaźnik do okna ramki aplikacji kontenera.

*Używasz pwnddoc*<br/>
Wskaźnik do okna poziomu dokumentu kontenera. Może mieć wartość NULL, jeśli kontener jest aplikacją SDI.

### <a name="return-value"></a>Wartość zwracana

Niezerowe po powodzeniu; w przeciwnym razie 0.

### <a name="remarks"></a>Uwagi

Domyślna implementacja nie robi nic. Zastąp tę funkcję, aby wykonać wszelkie specjalne przetwarzanie wymagane podczas tworzenia pasków sterowania.

## <a name="coleipframewndrepositionframe"></a><a name="repositionframe"></a> COleIPFrameWnd:: RepositionFrame

Struktura wywołuje `RepositionFrame` funkcję członkowską, aby ułożyć paski kontroli i zmienić położenie okna edycji w miejscu, tak aby wszystkie były widoczne.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parametry

*lpPosRect*<br/>
Wskaźnik do `RECT` struktury lub `CRect` obiektu zawierającego bieżące Współrzędne położenia okna ramki w pikselach względem obszaru klienckiego.

*lpClipRect*<br/>
Wskaźnik do `RECT` struktury lub `CRect` obiektu zawierającego bieżące współrzędne prostokąta wycinka okna ramki w pikselach względem obszaru klienckiego.

### <a name="remarks"></a>Uwagi

Układ pasków sterowania w oknie kontenera różni się od tego, który jest wykonywany przez okno ramki inne niż OLE. Okno ramki inne niż OLE oblicza pozycje pasków sterowania i innych obiektów z danego rozmiaru okna ramki, jak w wywołaniu [obiektu CFrameWnd:: RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Obszar klienta to to, co pozostanie, gdy zostanie odjęte miejsce dla pasków sterowania i innych obiektów. `COleIPFrameWnd`Okno z drugiej strony umieszcza paski narzędzi zgodnie z danym obszarem klienta. Innymi słowy, `CFrameWnd::RecalcLayout` działa "z zewnątrz w", " `COleIPFrameWnd::RepositionFrame` działa" od wewnątrz ".

## <a name="see-also"></a>Zobacz też

[Przykład HIERSVR MFC](../../overview/visual-cpp-samples.md)<br/>
[Klasa obiektu CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa obiektu CFrameWnd](../../mfc/reference/cframewnd-class.md)

---
description: 'Dowiedz się więcej na temat: Klasa CHtmlEditView'
title: Klasa CHtmlEditView
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
ms.openlocfilehash: 9ab998ca16a26fd4ef7a23e4dc58c6542ec330b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261323"
---
# <a name="chtmleditview-class"></a>Klasa CHtmlEditView

Oferuje funkcje platformy edycji WebBrowser w kontekście architektury dokumentu/widoku MFC.

## <a name="syntax"></a>Składnia

```
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|Konstruuje `CHtmlEditView` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHtmlEditView:: Create](#create)|Tworzy nowy obiekt okna.|
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|Zwraca `IHTMLDocument2` interfejs w bieżącym dokumencie.|
|[CHtmlEditView::GetStartDocument](#getstartdocument)|Pobiera nazwę dokumentu domyślnego dla tego widoku.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CHtmlView](../../mfc/reference/chtmlview-class.md)

`CHtmlEditView`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxhtml. h

## <a name="chtmleditviewchtmleditview"></a><a name="chtmleditview"></a> CHtmlEditView::CHtmlEditView

Konstruuje `CHtmlEditView` obiekt.

```
CHtmlEditView();
```

## <a name="chtmleditviewcreate"></a><a name="create"></a> CHtmlEditView:: Create

Tworzy nowy obiekt okna.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametry

*lpszClassName*<br/>
Wskazuje ciąg znaków zakończony znakiem null, który nazywa klasę systemu Windows. Nazwa klasy może być dowolną nazwą zarejestrowanej za pomocą funkcji globalnej [AfxRegisterWndClass —](application-information-and-management.md#afxregisterwndclass) lub `RegisterClass` funkcji systemu Windows. Jeśli wartość jest równa NULL, program używa wstępnie zdefiniowanych domyślnych atrybutów [obiektu CFrameWnd](../../mfc/reference/cframewnd-class.md) .

*lpszWindowName*<br/>
Wskazuje ciąg znaków zakończony znakiem null, który reprezentuje nazwę okna.

*dwStyle*<br/>
Określa atrybuty stylu okna. Domyślnie są ustawiane style WS_VISIBLE i WS_CHILD systemu Windows.

*cinania*<br/>
Odwołanie do struktury [Rect](/windows/win32/api/windef/ns-windef-rect) określające rozmiar i położenie okna. Wartość *rectDefault* umożliwia systemowi Windows określenie rozmiaru i pozycji nowego okna.

*pParentWnd*<br/>
Wskaźnik do okna nadrzędnego formantu.

*nID*<br/>
Numer IDENTYFIKACYJNy widoku. Domyślnie Ustaw wartość AFX_IDW_PANE_FIRST.

*pContext*<br/>
Wskaźnik do elementu [CCreateContext](../../mfc/reference/ccreatecontext-structure.md). Domyślnie wartość NULL.

### <a name="remarks"></a>Uwagi

Ta metoda spowoduje również wywołanie zawartej metody WebBrowser w `Navigate` celu załadowania dokumentu domyślnego (zobacz [CHtmlEditView:: GetStartDocument](#getstartdocument)).

## <a name="chtmleditviewgetdhtmldocument"></a><a name="getdhtmldocument"></a> CHtmlEditView::GetDHtmlDocument

Zwraca `IHTMLDocument2` interfejs w bieżącym dokumencie.

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Parametry

*ppDocument*<br/>
Interfejs [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) .

## <a name="chtmleditviewgetstartdocument"></a><a name="getstartdocument"></a> CHtmlEditView::GetStartDocument

Pobiera nazwę dokumentu domyślnego dla tego widoku.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>Zobacz też

[Przykład HTMLEdit](../../overview/visual-cpp-samples.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)

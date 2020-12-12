---
description: 'Dowiedz się więcej na temat: Klasa CHtmlEditCtrl'
title: Klasa CHtmlEditCtrl
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
helpviewer_keywords:
- CHtmlEditCtrl [MFC], CHtmlEditCtrl
- CHtmlEditCtrl [MFC], Create
- CHtmlEditCtrl [MFC], GetDHtmlDocument
- CHtmlEditCtrl [MFC], GetStartDocument
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
ms.openlocfilehash: d395f0f9f3e8b5ae10ad0ce35b2b1e410633e8d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184000"
---
# <a name="chtmleditctrl-class"></a>Klasa CHtmlEditCtrl

Oferuje funkcje kontrolki ActiveX WebBrowser w oknie MFC.

## <a name="syntax"></a>Składnia

```
class CHtmlEditCtrl: public CWnd,
    public CHtmlEditCtrlBase<CHtmlEditCtrl>
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|Konstruuje `CHtmlEditCtrl` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CHtmlEditCtrl:: Create](#create)|Tworzy formant ActiveX WebBrowser i dołącza go do `CHtmlEditCtrl` obiektu. Ta funkcja automatycznie umieszcza formant ActiveX WebBrowser w trybie edycji.|
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|Pobiera Interfejs [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) w dokumencie aktualnie załadowanym do zawartej kontrolki WebBrowser.|
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|Pobiera adres URL do dokumentu domyślnego do załadowania w zawartej kontrolce WebBrowser.|

## <a name="remarks"></a>Uwagi

Hostowany formant WebBrowser jest automatycznie umieszczany w trybie edycji po jego utworzeniu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHtmlEditCtrl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxhtml. h

## <a name="chtmleditctrlchtmleditctrl"></a><a name="chtmleditctrl"></a> CHtmlEditCtrl::CHtmlEditCtrl

Konstruuje `CHtmlEditCtrl` obiekt.

```
CHtmlEditCtrl();
```

## <a name="chtmleditctrlcreate"></a><a name="create"></a> CHtmlEditCtrl:: Create

Tworzy formant ActiveX WebBrowser i dołącza go do `CHtmlEditCtrl` obiektu. Kontrolka ActiveX WebBrowser automatycznie nawiguje do dokumentu domyślnego, a następnie jest umieszczana w trybie edycji przez tę funkcję.

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametry

*lpszWindowName*<br/>
Ten parametr jest nieużywany.

*dwStyle*<br/>
Ten parametr jest nieużywany.

*cinania*<br/>
Określa rozmiar i położenie kontrolki.

*pParentWnd*<br/>
Określa okno nadrzędne kontrolki. Nie może mieć wartości NULL.

*nID*<br/>
Określa identyfikator kontrolki.

*pContext*<br/>
Ten parametr jest nieużywany.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość TRUE dla sukcesu, FALSE w przypadku błędu.

## <a name="chtmleditctrlgetdhtmldocument"></a><a name="getdhtmldocument"></a> CHtmlEditCtrl::GetDHtmlDocument

Pobiera Interfejs [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) w dokumencie aktualnie załadowanym do zawartej kontrolki WebBrowser

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>Parametry

*ppDocument*<br/>
Interfejs dokumentu.

## <a name="chtmleditctrlgetstartdocument"></a><a name="getstartdocument"></a> CHtmlEditCtrl::GetStartDocument

Pobiera adres URL do dokumentu domyślnego do załadowania w zawartej kontrolce WebBrowser.

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)

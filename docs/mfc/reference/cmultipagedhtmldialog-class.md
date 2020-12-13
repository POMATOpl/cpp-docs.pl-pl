---
description: 'Dowiedz się więcej na temat: Klasa CMultiPageDHtmlDialog'
title: Klasa CMultiPageDHtmlDialog
ms.date: 03/27/2019
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
ms.openlocfilehash: 1f7f8c2081687c71a98e427bb5396cfa47a73deb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331531"
---
# <a name="cmultipagedhtmldialog-class"></a>Klasa CMultiPageDHtmlDialog

Wielostronicowe okno dialogowe wyświetla wiele stron HTML sekwencyjnie i obsługuje zdarzenia z poszczególnych stron.

## <a name="syntax"></a>Składnia

```
class CMultiPageDHtmlDialog : public CDHtmlDialog
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Konstruuje obiekt okna dialogowego języka DHTML wielostronicowego (kreatora).|
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#_dtorcmultipagedhtmldialog)|Niszczy obiekt okna dialogowego DHTML wielostronicowego.|

## <a name="remarks"></a>Uwagi

Mechanizmem wykonywania tej operacji jest [Mapa zdarzeń DHTML i URL](dhtml-event-maps.md), która zawiera osadzone mapy zdarzeń dla każdej strony.

## <a name="example"></a>Przykład

W tym oknie dialogowym wielostronicowym założono trzy zasoby HTML, które definiują proste funkcje podobne do kreatora. Pierwsza strona ma przycisk **dalej** , drugi przycisk **poprzedni** i **Następny** oraz trzeci przycisk **poprzedni** . Po naciśnięciu jednego z przycisków funkcja obsługi wywołuje [CDHtmlDialog:: LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) w celu załadowania odpowiedniej nowej strony.

Odpowiednie części deklaracji klasy (w CMyMultiPageDlg. h):

[!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]

Odpowiednie części implementacji klasy (w CMyMultipageDlg. cpp):

[!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

`CMultiPageDHtmlDialog`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdhtml. h

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="cmultipagedhtmldialog"></a> CMultiPageDHtmlDialog::CMultiPageDHtmlDialog

Konstruuje obiekt okna dialogowego języka DHTML wielostronicowego (kreatora).

```
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID = NULL,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog();
```

### <a name="parameters"></a>Parametry

*lpszTemplateName*<br/>
Ciąg zakończony znakiem null, który jest nazwą zasobu szablonu okna dialogowego.

*szHtmlResID*<br/>
Ciąg zakończony znakiem null, który jest nazwą zasobu HTML.

*pParentWnd*<br/>
Wskaźnik do obiektu nadrzędnego lub elementu będącego właścicielem (typu [CWnd](../../mfc/reference/cwnd-class.md)), do którego należy obiekt okna dialogowego. Jeśli ma wartość NULL, okno nadrzędne obiektu okna dialogowego jest ustawione na główne okno aplikacji.

*nIDTemplate*<br/>
Zawiera numer IDENTYFIKACYJNy zasobu szablonu okna dialogowego.

*nHtmlResID*<br/>
Zawiera numer IDENTYFIKACYJNy zasobu HTML.

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="_dtorcmultipagedhtmldialog"></a> CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog

Niszczy obiekt okna dialogowego DHTML wielostronicowego.

```
virtual ~CMultiPageDHtmlDialog();
```

## <a name="see-also"></a>Zobacz też

[Klasa CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

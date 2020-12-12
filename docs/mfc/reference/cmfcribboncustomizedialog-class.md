---
description: 'Dowiedz się więcej na temat: Klasa CMFCRibbonCustomizeDialog'
title: Klasa CMFCRibbonCustomizeDialog
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
ms.openlocfilehash: 9420ebdf32a1c26cba6efee17467fd3dfe202574
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293615"
---
# <a name="cmfcribboncustomizedialog-class"></a>Klasa CMFCRibbonCustomizeDialog

Wyświetla stronę **Dostosuj** Wstążkę.

## <a name="syntax"></a>Składnia

```
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|Konstruuje `CMFCRibbonCustomizeDialog` obiekt.|
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCRibbonCustomizeDialog::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|

## <a name="remarks"></a>Uwagi

MFC tworzy wystąpienie tej klasy automatycznie, jeśli nie przetworzysz komunikatu AFX_WM_ON_RIBBON_CUSTOMIZE lub jeśli zwracasz wartość 0 z programu obsługi komunikatów.

Jeśli chcesz użyć tej klasy w aplikacji do wyświetlania okna dialogowego **Dostosuj** Wstążkę, po prostu Utwórz wystąpienie go i Wywołaj `DoModal` metodę.

Ponieważ ta klasa jest pochodną [klasy CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md), można dodawać niestandardowe strony przy użyciu `CMFCPropertySheet` interfejsu API.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

[CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxribboncustomizedialog. h

## <a name="cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a> CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog

Konstruuje `CMFCRibbonCustomizeDialog` obiekt.

```
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,
    CMFCRibbonBar* pRibbon);
```

### <a name="parameters"></a>Parametry

*pWndParent*<br/>
podczas Wskaźnik do okna nadrzędnego (zazwyczaj ramka główna).

*pRibbon*<br/>
podczas Wskaźnik do `CMFCRibbonBar` , który ma zostać dostosowany.

### <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania `CMFCRibbonCustomizeDialog` obiektu.

[!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]

### <a name="remarks"></a>Uwagi

Konstruktor tworzy wystąpienie obiektu [klasy CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) i dodaje go do kolekcji stron arkusza właściwości.

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)

---
description: 'Dowiedz się więcej na temat: Klasa CMFCPropertyPage'
title: Klasa CMFCPropertyPage
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
ms.openlocfilehash: 9acdce1fd2f6133d44699f7bea4cce00e9d6dadb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289858"
---
# <a name="cmfcpropertypage-class"></a>Klasa CMFCPropertyPage

`CMFCPropertyPage`Klasa obsługuje wyświetlanie menu podręcznych na stronie właściwości.

## <a name="syntax"></a>Składnia

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|Konstruuje `CMFCPropertyPage` obiekt.|
|`CMFCPropertyPage::~CMFCPropertyPage`|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|Używane przez platformę do tworzenia wystąpienia dynamicznego tego typu klasy.|
|`CMFCPropertyPage::GetThisClass`|Używane przez platformę do uzyskania wskaźnika do obiektu [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) , który jest skojarzony z tym typem klasy.|
|`CMFCPropertyPage::OnSetActive`|Ta funkcja członkowska jest wywoływana przez platformę, gdy strona zostanie wybrana przez użytkownika i zostanie uaktywniona. (Przesłania [CPropertyPage:: OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).)|
|`CMFCPropertyPage::PreTranslateMessage`|Tłumaczy komunikaty okna przed ich wysłaniem do funkcji systemu Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) i [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) . Aby uzyskać więcej informacji i składni metod, zobacz [CWnd::P retranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Przesłania `CPropertyPage::PreTranslateMessage`).|

## <a name="remarks"></a>Uwagi

`CMFCPropertyPage`Klasa reprezentuje pojedyncze strony arkusza właściwości, w przeciwnym razie znane jako karta okna dialogowego.

Użyj `CMFCPropertyPage` klasy razem z klasą [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) . Aby użyć menu na stronie właściwości, Zastąp wszystkie wystąpienia `CPropertyPage` klasy klasą `CMFCPropertyPage` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxpropertypage. h

## <a name="cmfcpropertypagecmfcpropertypage"></a><a name="cmfcpropertypage"></a> CMFCPropertyPage::CMFCPropertyPage

Konstruuje `CMFCPropertyPage` obiekt.

```
CMFCPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption=0);

CMFCPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption=0);
```

### <a name="parameters"></a>Parametry

*nIDTemplate*<br/>
Identyfikator zasobu szablonu dla tej strony.

*nIDCaption*<br/>
Identyfikator zasobu etykiety, który ma zostać umieszczony na karcie na tej stronie. Jeśli wartość jest równa 0, nazwa jest uzyskiwana z szablonu okna dialogowego na tej stronie. Wartość domyślna to 0.

*lpszTemplateName*<br/>
Wskazuje nazwę szablonu na tej stronie. Nie może mieć wartości NULL.

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji o parametrach konstruktora, zobacz [CPropertyPage:: CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage).

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

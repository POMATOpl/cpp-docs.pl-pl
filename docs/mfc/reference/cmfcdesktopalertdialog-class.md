---
description: 'Dowiedz się więcej na temat: Klasa CMFCDesktopAlertDialog'
title: Klasa CMFCDesktopAlertDialog
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::CreateFromParams
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::GetDlgSize
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::HasFocus
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::PreTranslateMessage
helpviewer_keywords:
- CMFCDesktopAlertDialog [MFC], CreateFromParams
- CMFCDesktopAlertDialog [MFC], GetDlgSize
- CMFCDesktopAlertDialog [MFC], HasFocus
- CMFCDesktopAlertDialog [MFC], PreTranslateMessage
ms.assetid: a53c60aa-9607-485b-b826-ec64962075f6
ms.openlocfilehash: 327ec72b1e58d90e768f51c083ff9545f24f6f0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193191"
---
# <a name="cmfcdesktopalertdialog-class"></a>Klasa CMFCDesktopAlertDialog

`CMFCDesktopAlertDialog`Klasa jest używana razem z [klasą CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md) do wyświetlania niestandardowego okna dialogowego w oknie podręcznym.

Aby uzyskać więcej szczegółów, zobacz kod źródłowy znajdujący się w folderze **VC \\ atlmfc \\ src \\ MFC** instalacji programu Visual Studio.

## <a name="syntax"></a>Składnia

```
class CMFCDesktopAlertDialog : public CDialogEx
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCDesktopAlertDialog::CreateFromParams](#createfromparams)||
|[CMFCDesktopAlertDialog::GetDlgSize](#getdlgsize)||
|[CMFCDesktopAlertDialog::HasFocus](#hasfocus)||
|[CMFCDesktopAlertDialog::P reTranslateMessage](#pretranslatemessage)|(Przesłania `CDialogEx::PreTranslateMessage`).|

### <a name="remarks"></a>Uwagi

Wykonaj następujące kroki, aby wyświetlić niestandardowe okno dialogowe w oknie podręcznym:

1. Utwórz klasę z `CMFCDesktopAlertDialog` .

1. Utwórz podrzędny szablon okna dialogowego w zasobach projektu.

1. Wywołanie [CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) z identyfikatorem zasobu szablonu okna dialogowego i wskaźnikiem do informacji o klasie środowiska uruchomieniowego klasy pochodnej jako parametrów.

1. Zaprogramowanie niestandardowego okna dialogowego służącego do obsługi wszystkich powiadomień pochodzących z formantów hostowanych lub programowych formantów hostowanych w celu bezpośredniej obsługi tych powiadomień.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxDesktopAlertDialog. h

## <a name="cmfcdesktopalertdialogcreatefromparams"></a><a name="createfromparams"></a> CMFCDesktopAlertDialog::CreateFromParams

```
BOOL CreateFromParams(
    CMFCDesktopAlertWndInfo& params,
    CMFCDesktopAlertWnd* pParent);
```

### <a name="parameters"></a>Parametry

podczas *Parametry*<br/>

podczas *pParent*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcdesktopalertdialoggetdlgsize"></a><a name="getdlgsize"></a> CMFCDesktopAlertDialog::GetDlgSize

```
CSize GetDlgSize();
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcdesktopalertdialoghasfocus"></a><a name="hasfocus"></a> CMFCDesktopAlertDialog::HasFocus

```
BOOL HasFocus() const;
```

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="cmfcdesktopalertdialogpretranslatemessage"></a><a name="pretranslatemessage"></a> CMFCDesktopAlertDialog::P reTranslateMessage

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametry

podczas *pMsg*<br/>

### <a name="return-value"></a>Wartość zwracana

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[Klasa CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[Klasa CDialogEx](../../mfc/reference/cdialogex-class.md)

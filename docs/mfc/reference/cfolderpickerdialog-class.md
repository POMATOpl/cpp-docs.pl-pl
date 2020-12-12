---
description: 'Dowiedz się więcej na temat: Klasa CFolderPickerDialog'
title: Klasa CFolderPickerDialog
ms.date: 03/27/2019
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: f4a5bcc3162a5fffcc723d7ec420685b02be10f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184429"
---
# <a name="cfolderpickerdialog-class"></a>Klasa CFolderPickerDialog

Klasa CFolderPickerDialog implementuje CFileDialog w trybie selektora folderów.

## <a name="syntax"></a>Składnia

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CFolderPickerDialog:: ~ CFolderPickerDialog](#_dtorcfolderpickerdialog)|Destruktor.|
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|Konstruktor.|

## <a name="remarks"></a>Uwagi

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdlgs. h

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="cfolderpickerdialog"></a> CFolderPickerDialog::CFolderPickerDialog

Konstruktor.

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>Parametry

*lpszFolder*<br/>
Folder początkowy.

*flagiDW*<br/>
Kombinacja jednej lub wielu flag, które umożliwiają dostosowanie okna dialogowego.

*pParentWnd*<br/>
Wskaźnik do okna nadrzędnego lub właściciela obiektu okna dialogowego.

*dwSize*<br/>
Rozmiar struktury OPENFILEname.

### <a name="remarks"></a>Uwagi

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="_dtorcfolderpickerdialog"></a> CFolderPickerDialog:: ~ CFolderPickerDialog

Destruktor.

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>Uwagi

## <a name="see-also"></a>Zobacz też

[Klasy](../../mfc/reference/mfc-classes.md)

---
description: 'Dowiedz się więcej na temat: Klasa CCommonDialog'
title: Klasa CCommonDialog
ms.date: 11/04/2016
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
ms.openlocfilehash: 927348982529f14eb0ad762019bb4463aaa77c99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227900"
---
# <a name="ccommondialog-class"></a>Klasa CCommonDialog

Klasa bazowa dla klas, które hermetyzują funkcjonalność wspólnych okien dialogowych systemu Windows.

## <a name="syntax"></a>Składnia

```
class CCommonDialog : public CDialog
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CCommonDialog::CCommonDialog](#ccommondialog)|Konstruuje `CCommonDialog` obiekt.|

## <a name="remarks"></a>Uwagi

Następujące klasy hermetyzują funkcjonalność wspólnych okien dialogowych systemu Windows:

- [CFileDialog](../../mfc/reference/cfiledialog-class.md)

- [CFontDialog](../../mfc/reference/cfontdialog-class.md)

- [CColorDialog](../../mfc/reference/ccolordialog-class.md)

- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)

- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)

- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)

- [Okno CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)

- [COleDialog](../../mfc/reference/coledialog-class.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CCommonDialog`

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxdlgs. h

## <a name="ccommondialogccommondialog"></a><a name="ccommondialog"></a> CCommonDialog::CCommonDialog

Konstruuje `CCommonDialog` obiekt.

```
explicit CCommonDialog(CWnd* pParentWnd);
```

### <a name="parameters"></a>Parametry

*pParentWnd*<br/>
Wskazuje obiekt obiektu nadrzędnego lub właściciela (typu [CWnd](../../mfc/reference/cwnd-class.md)), do którego należy obiekt okna dialogowego. Jeśli ma wartość NULL, okno nadrzędne obiektu okna dialogowego jest ustawione na główne okno aplikacji.

### <a name="remarks"></a>Uwagi

Aby uzyskać pełne informacje, zobacz [CDialog:: CDialog](../../mfc/reference/cdialog-class.md#cdialog) .

## <a name="see-also"></a>Zobacz też

[Klasa CDialog](../../mfc/reference/cdialog-class.md)<br/>
[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasa CFileDialog](../../mfc/reference/cfiledialog-class.md)<br/>
[Klasa CFontDialog](../../mfc/reference/cfontdialog-class.md)<br/>
[Klasa CColorDialog](../../mfc/reference/ccolordialog-class.md)<br/>
[Klasa CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)<br/>
[Klasa CPrintDialog](../../mfc/reference/cprintdialog-class.md)<br/>
[Klasa okno CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)<br/>
[Klasa COleDialog](../../mfc/reference/coledialog-class.md)

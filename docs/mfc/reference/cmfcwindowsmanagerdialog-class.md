---
description: 'Dowiedz się więcej na temat: Klasa CMFCWindowsManagerDialog'
title: Klasa CMFCWindowsManagerDialog
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: 526cf731e049ffd267382b0c3895b5d29792dcb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331627"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>Klasa CMFCWindowsManagerDialog

`CMFCWindowsManagerDialog`Obiekt umożliwia użytkownikowi Zarządzanie oknami podrzędnymi MDI w aplikacji MDI.

## <a name="syntax"></a>Składnia

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Konstruuje `CMFCWindowsManagerDialog` obiekt.|

## <a name="remarks"></a>Uwagi

`CMFCWindowsManagerDialog`Zawiera listę okien podrzędnych MDI, które są aktualnie otwarte w aplikacji. Użytkownik może ręcznie kontrolować stan okien podrzędnych MDI przy użyciu tego okna dialogowego.

`CMFCWindowsManagerDialog` jest osadzony wewnątrz [klasy CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md). `CMFCWindowsManagerDialog`Nie jest klasą, którą należy utworzyć ręcznie. Zamiast tego należy wywołać funkcję [CMDIFrameWndEx:: ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog)i utworzyć i wyświetlić `CMFCWindowsManagerDialog` obiekt.

## <a name="example"></a>Przykład

Poniższy przykład ilustruje sposób konstruowania `CMFCWindowsManagerDialog` obiektu przez wywołanie `CMDIFrameWndEx::ShowWindowsDialog` . Ten fragment kodu jest częścią [przykładu demonstracyjnego Visual Studio](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>Wymagania

**Nagłówek:** afxWindowsManagerDialog. h

## <a name="cmfcwindowsmanagerdialogcmfcwindowsmanagerdialog"></a><a name="cmfcwindowsmanagerdialog"></a> CMFCWindowsManagerDialog::CMFCWindowsManagerDialog

Konstruuje obiekt [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) .

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>Parametry

*pMDIFrame*<br/>
podczas Wskaźnik do okna nadrzędnego lub właściciela.

*bHelpButton*<br/>
podczas Parametr logiczny określający, czy struktura wyświetla przycisk **Pomoc** .

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji na temat menedżerów wizualnych, zobacz [Menedżer wizualizacji](../../mfc/visualization-manager.md).

## <a name="see-also"></a>Zobacz też

[Wykres hierarchii](../../mfc/hierarchy-chart.md)<br/>
[Klasy](../../mfc/reference/mfc-classes.md)<br/>
[Klasa CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)

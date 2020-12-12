---
description: 'Dowiedz się więcej o: WM_ obsługi komunikatów: F-K'
title: 'Programy obsługi komunikatów WM_: F - K'
ms.date: 11/27/2018
f1_keywords:
- ON_WM_FONTCHANGE
- ON_WM_ICONERASEBKGND
- ON_WM_KEYDOWN
- ON_WM_GETMINMAXINFO
- ON_WM_KEYUP
- ON_WM_HSCROLL
- ON_WM_KILLFOCUS
- ON_WM_HSCROLLCLIPBOARD
- ON_WM_GETDLGCODE
- ON_WM_HELPINFO
- ON_WM_INITMENUPOPUP
- ON_WM_INITMENU
helpviewer_keywords:
- ON_WM_HELPINFO [MFC]
- ON_WM_KILLFOCUS [MFC]
- ON_WM_GETMINMAXINFO [MFC]
- ON_WM_KEYUP [MFC]
- ON_WM_HSCROLL [MFC]
- ON_WM_INITMENUPOPUP [MFC]
- ON_WM_FONTCHANGE [MFC]
- ON_WM_ICONERASEBKGND [MFC]
- ON_WM_GETDLGCODE [MFC]
- ON_WM_HSCROLLCLIPBOARD [MFC]
- ON_WM_INITMENU [MFC]
- WM_ messages [MFC]
- ON_WM_KEYDOWN [MFC]
ms.assetid: 0e7de191-1499-499f-859c-62742797808e
ms.openlocfilehash: 91fb2448862dd70a852191f021244571813b0102
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218345"
---
# <a name="wm_-message-handlers-f---k"></a>Programy obsługi komunikatów WM_: F - K

Następujące wpisy mapy po lewej stronie odpowiadają prototypom funkcji po prawej stronie:

|Wpis mapy|Prototyp funkcji|
|---------------|------------------------|
|ON_WM_FONTCHANGE ()|afx_msg void [OnFontChange](../../mfc/reference/cwnd-class.md#onfontchange)();|
|ON_WM_GETDLGCODE ()|afx_msg UINT [OnGetDlgCode](../../mfc/reference/cwnd-class.md#ongetdlgcode)();|
|ON_WM_GETMINMAXINFO ()|afx_msg void [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)(MINMAXINFO *);|
|ON_WM_HELPINFO ()|afx_msg BOOL [OnHelpInfo](../../mfc/reference/cwnd-class.md#onhelpinfo)(HELPINFO *);|
|ON_WM_HOTKEY ()|afx_msg void [onhotkey](../../mfc/reference/cwnd-class.md#onhotkey)(UINT, UINT, uint);|
|ON_WM_HSCROLL ()|afx_msg void [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)(UINT, uint, CWnd *);|
|ON_WM_HSCROLLCLIPBOARD ()|afx_msg void [OnHScrollClipboard](../../mfc/reference/cwnd-class.md#onhscrollclipboard)(CWnd *, UINT, uint);|
|ON_WM_ICONERASEBKGND ()|afx_msg void [OnIconEraseBkgnd](../../mfc/reference/cwnd-class.md#oniconerasebkgnd)(przepust *);|
|ON_WM_INITMENU ()|afx_msg void [OnInitMenu](../../mfc/reference/cwnd-class.md#oninitmenu)(CMenu *);|
|ON_WM_INITMENUPOPUP ()|afx_msg void [OnInitMenuPopup](../../mfc/reference/cwnd-class.md#oninitmenupopup)(CMenu *, uint, bool);|
|ON_WM_INPUT ()|afx_msg void [OnRawInput](../../mfc/reference/cwnd-class.md#onrawinput)(uint, HRAWINPUT);|
|ON_WM_INPUT_DEVICE_CHANGE ()|afx_msg void [OnInputDeviceChange](../../mfc/reference/cwnd-class.md#oninputdevicechange)(krótkie niepodpisane);|
|ON_WM_INPUTLANGCHANGE ()|afx_msg void [OnInputLangChange](../../mfc/reference/cwnd-class.md#oninputlangchange)(Byte, uint);|
|ON_WM_INPUTLANGCHANGEREQUEST ()|afx_msg void [OnInputLangChangeRequest](../../mfc/reference/cwnd-class.md#oninputlangchangerequest)(uint, HKL);|
|ON_WM_KEYDOWN ()|afx_msg void [OnKeyDown](../../mfc/reference/cwnd-class.md#onkeydown)(UINT, UINT, uint);|
|ON_WM_KEYUP ()|afx_msg void [OnKeyUp](../../mfc/reference/cwnd-class.md#onkeyup)(UINT, UINT, uint);|
|ON_WM_KILLFOCUS ()|afx_msg void [OnKillFocus](../../mfc/reference/cwnd-class.md#onkillfocus)(CWnd *);|

## <a name="see-also"></a>Zobacz też

[Mapy komunikatów](../../mfc/reference/message-maps-mfc.md)<br/>
[Programy obsługi komunikatów WM_](../../mfc/reference/handlers-for-wm-messages.md)

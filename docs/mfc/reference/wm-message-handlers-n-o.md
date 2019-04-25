---
title: 'Programy obsługi komunikatów WM_: N - O'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_NCHITTEST
- ON_WM_NCLBUTTONDOWN
- ON_WM_NCCALCSIZE
- ON_WM_NCLBUTTONUP
- ON_WM_NCPAINT
- ON_WM_NCMBUTTONUP
- ON_WM_NCCREATE
- ON_WM_NCACTIVATE
- ON_WM_NCMOUSEMOVE
- ON_WM_NCRBUTTONDBLCLK
- ON_WM_NCLBUTTONDBLCLK
- ON_WM_NCDESTROY
- ON_WM_NCMBUTTONDBLCLK
- ON_WM_NCRBUTTONDOWN
- ON_WM_NCRBUTTONUP
- ON_WM_NCMBUTTONDOWN
helpviewer_keywords:
- ON_WM_NCCALCSIZE [MFC]
- ON_WM_NCMBUTTONDOWN [MFC]
- ON_WM_NCRBUTTONDBLCLK [MFC]
- ON_WM_NCMBUTTONDBLCLK [MFC]
- ON_WM_NCLBUTTONDBLCLK [MFC]
- ON_WM_NCDESTROY [MFC]
- ON_WM_NCRBUTTONDOWN [MFC]
- ON_WM_NCLBUTTONDOWN [MFC]
- ON_WM_NCCREATE [MFC]
- ON_WM_NCRBUTTONUP [MFC]
- ON_WM_NCLBUTTONUP [MFC]
- ON_WM_NCPAINT [MFC]
- ON_WM_NCACTIVATE [MFC]
- ON_WM_NCHITTEST [MFC]
- ON_WM_NCMOUSEMOVE [MFC]
- ON_WM_NCMBUTTONUP [MFC]
- WM_ messages
ms.assetid: 4efd1cda-b642-4e8b-89e8-73255fa70d77
ms.openlocfilehash: 59fd895823ff13039e6f78b8164cd19f3eac2af9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309127"
---
# <a name="wm-message-handlers-n---o"></a>Programy obsługi komunikatów WM_: N - O

Następujące wpisy mapy po lewej stronie odpowiadają prototypy funkcji po prawej stronie:

|Wpis mapy|Prototyp funkcji|
|---------------|------------------------|
|ON_WM_NCACTIVATE()|afx_msg BOOL [OnNcActivate](../../mfc/reference/cwnd-class.md#onncactivate)(wartość logiczna);|
|ON_WM_NCCALCSIZE()|afx_msg void [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)(wartość logiczna, nccalcsize_params — DALEKI *);|
|ON_WM_NCCREATE()|afx_msg BOOL [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)(LPCREATESTRUCT);|
|ON_WM_NCDESTROY()|afx_msg void [onncdestroy —](../../mfc/reference/cwnd-class.md#onncdestroy)();|
|ON_WM_NCHITTEST()|afx_msg LRESULT [OnNcHitTest](../../mfc/reference/cwnd-class.md#onnchittest)(CPoint);|
|ON_WM_NCLBUTTONDBLCLK()|afx_msg void [OnNcLButtonDblClk](../../mfc/reference/cwnd-class.md#onnclbuttondblclk)(UINT, CPoint);|
|ON_WM_NCLBUTTONDOWN()|afx_msg void [OnNcLButtonDown](../../mfc/reference/cwnd-class.md#onnclbuttondown)(UINT, CPoint);|
|ON_WM_NCLBUTTONUP()|afx_msg void [OnNcLButtonUp](../../mfc/reference/cwnd-class.md#onnclbuttonup)(UINT, CPoint);|
|ON_WM_NCMBUTTONDBLCLK()|afx_msg void [OnNcMButtonDblClk](../../mfc/reference/cwnd-class.md#onncmbuttondblclk)(UINT, CPoint);|
|ON_WM_NCMBUTTONDOWN()|afx_msg void [OnNcMButtonDown](../../mfc/reference/cwnd-class.md#onncmbuttondown)(UINT, CPoint);|
|ON_WM_NCMBUTTONUP()|afx_msg void [OnNcMButtonUp](../../mfc/reference/cwnd-class.md#onncmbuttonup)(UINT, CPoint);|
|ON_WM_NCMOUSEHOVER()|afx_msg void [OnNcMouseHover](../../mfc/reference/cwnd-class.md#onncmousehover)(UINT, CPoint);|
|ON_WM_NCMOUSELEAVE()|afx_msg void [OnNcMouseLeave](../../mfc/reference/cwnd-class.md#onncmouseleave)();|
|ON_WM_NCMOUSEMOVE()|afx_msg void [OnNcMouseMove](../../mfc/reference/cwnd-class.md#onncmousemove)(UINT, CPoint);|
|ON_WM_NCPAINT()|afx_msg void [OnNcPaint](../../mfc/reference/cwnd-class.md#onncpaint)();|
|ON_WM_NCRBUTTONDBLCLK()|afx_msg void [OnNcRButtonDblClk](../../mfc/reference/cwnd-class.md#onncrbuttondblclk)(UINT, CPoint);|
|ON_WM_NCRBUTTONDOWN()|afx_msg void [OnNcRButtonDown](../../mfc/reference/cwnd-class.md#onncrbuttondown)(UINT, CPoint);|
|ON_WM_NCRBUTTONUP()|afx_msg void [OnNcRButtonUp](../../mfc/reference/cwnd-class.md#onncrbuttonup)(UINT, CPoint);|
|ON_WM_NCXBUTTONDBLCLK()|void [OnNcXButtonDblClk](../../mfc/reference/cwnd-class.md#onncxbuttondblclk)(krótki, UINT, CPoint);|
|ON_WM_NCXBUTTONDOWN()|afx_msg void [OnNcXButtonDown](../../mfc/reference/cwnd-class.md#onncxbuttondown)(krótki, UINT, CPoint);|
|ON_WM_NCXBUTTONUP()|afx_msg void [OnNcXButtonUp](../../mfc/reference/cwnd-class.md#onncxbuttonup)(krótki, UINT, CPoint);|
|ON_WM_NEXTMENU()|afx_msg void [OnNextMenu](../../mfc/reference/cwnd-class.md#onnextmenu)(UINT, LPMDINEXTMENU);|
|ON_WM_NOTIFYFORMAT()|afx_msg UINT [OnNotifyFormat](../../mfc/reference/cwnd-class.md#onnotifyformat)(CWnd *, UINT);|

## <a name="see-also"></a>Zobacz także

[Mapy komunikatów](../../mfc/reference/message-maps-mfc.md)<br/>
[Programy obsługi komunikatów WM_](../../mfc/reference/handlers-for-wm-messages.md)

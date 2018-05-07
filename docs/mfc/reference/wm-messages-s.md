---
title: 'Komunikaty WM_: S | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ON_WM_SYSDEADCHAR
- ON_WM_SYSKEYDOWN
- ON_WM_STYLECHANGING
- ON_WM_STYLECHANGED
- ON_WM_SPOOLERSTATUS
- ON_WM_SYSCHAR
- ON_WM_SETFOCUS
- ON_WM_SIZE
- ON_WM_SIZING
- ON_WM_SETCURSOR
- ON_WM_SYSCOMMAND
- ON_WM_SETTINGCHANGE
- ON_WM_SHOWWINDOW
- ON_WM_SYSKEYUP
- ON_WM_SIZECLIPBOARD
- ON_WM_SYSCOLORCHANGE
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_SIZE [MFC]
- ON_WM_SETFOCUS [MFC]
- ON_WM_SIZING [MFC]
- ON_WM_SYSCHAR [MFC]
- ON_WM_SETTINGCHANGE [MFC]
- ON_WM_SYSDEADCHAR [MFC]
- ON_WM_SHOWWINDOW [MFC]
- ON_WM_STYLECHANGING [MFC]
- ON_WM_SYSCOMMAND [MFC]
- ON_WM_STYLECHANGED [MFC]
- ON_WM_SPOOLERSTATUS [MFC]
- ON_WM_SYSCOLORCHANGE [MFC]
- ON_WM_SETCURSOR [MFC]
- ON_WM_SIZECLIPBOARD [MFC]
- ON_WM_SYSKEYUP [MFC]
- ON_WM_SYSKEYDOWN [MFC]
- WM_ messages
ms.assetid: 4b9aec79-a98f-4aa0-a3d9-110941b6dcbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b3b7918b74db4e7720f935bcfdf3bf3ffd3d950
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="wm-messages-s"></a>WM_ Messages: S
Następujące wpisy mapy odpowiadają prototypy funkcji.  
  
|Wpis w mapie|Prototyp funkcji|  
|---------------|------------------------|  
|(ON_WM_SETCURSOR)|afx_msg BOOL [OnSetCursor](../../mfc/reference/cwnd-class.md#onsetcursor)(CWnd *, UINT, UINT);|  
|(ON_WM_SETFOCUS)|afx_msg void [klasy OnSetFocus](../../mfc/reference/cwnd-class.md#onsetfocus)(CWnd *);|  
|(ON_WM_SETTINGCHANGE)|afx_msg void [OnSettingChange](../../mfc/reference/cwnd-class.md#onsettingchange)(uFlags UINT, LPCTSTR lpszSection);|  
|(ON_WM_SHOWWINDOW)|afx_msg void [OnShowWindow](../../mfc/reference/cwnd-class.md#onshowwindow)(wartość logiczna, UINT);|  
|(ON_WM_SIZE)|afx_msg void [OnSize](../../mfc/reference/cwnd-class.md#onsize)(UINT, int, int);|  
|(ON_WM_SIZECLIPBOARD)|afx_msg void [OnSizeClipboard](../../mfc/reference/cwnd-class.md#onsizeclipboard)(CWnd *, dojście);|  
|(ON_WM_SIZING)|afx_msg void [OnSizing](../../mfc/reference/cwnd-class.md#onsizing)(UINT, lprect —);|  
|(ON_WM_SPOOLERSTATUS)|afx_msg void [OnSpoolerStatus](../../mfc/reference/cwnd-class.md#onspoolerstatus)(UINT, UINT);|  
|(ON_WM_STYLECHANGED)|afx_msg void [OnStyleChanged](../../mfc/reference/cwnd-class.md#onstylechanged)(int, LPSTYLESTRUCT);|  
|(ON_WM_STYLECHANGING)|afx_msg void [OnStyleChanging](../../mfc/reference/cwnd-class.md#onstylechanging)(int, LPSTYLESTRUCT);|  
|(ON_WM_SYSCHAR)|afx_msg void [OnSysChar](../../mfc/reference/cwnd-class.md#onsyschar)(UINT, UINT, UINT);|  
|(ON_WM_SYSCOLORCHANGE)|afx_msg void [OnSysColorChange](../../mfc/reference/cwnd-class.md#onsyscolorchange)();|  
|(ON_WM_SYSCOMMAND)|afx_msg void [OnSysCommand](../../mfc/reference/cwnd-class.md#onsyscommand)(UINT, DŁUGI);|  
|(ON_WM_SYSDEADCHAR)|afx_msg void [OnSysDeadChar](../../mfc/reference/cwnd-class.md#onsysdeadchar)(UINT, UINT, UINT);|  
|(ON_WM_SYSKEYDOWN)|afx_msg void [OnSysKeyDown](../../mfc/reference/cwnd-class.md#onsyskeydown)(UINT, UINT, UINT);|  
|(ON_WM_SYSKEYUP)|afx_msg void [OnSysKeyUp](../../mfc/reference/cwnd-class.md#onsyskeyup)(UINT, UINT, UINT);|  
  
## <a name="see-also"></a>Zobacz też  
 [Mapy komunikatów](../../mfc/reference/message-maps-mfc.md)   
 [Programy obsługi komunikatów WM_](../../mfc/reference/handlers-for-wm-messages.md)


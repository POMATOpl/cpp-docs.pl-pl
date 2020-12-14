---
description: 'Dowiedz się więcej na temat: Thread-Specific klawisze dostępu'
title: Klawisze dostępu właściwe dla wątków
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
ms.openlocfilehash: 352d39b801d7e6dcecfbf27d841d6977d3666138
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216122"
---
# <a name="thread-specific-hot-keys"></a>Klawisze dostępu właściwe dla wątków

Aplikacja ustawia klawisz dostępu specyficzny dla wątku ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) przy użyciu funkcji systemu Windows `RegisterHotKey` . Gdy użytkownik naciśnie klawisz dostępu specyficzny dla wątku, system Windows ogłasza komunikat [WM_HOTKEY](/windows/win32/inputdev/wm-hotkey) na początku kolejki komunikatów określonego wątku. Komunikat WM_HOTKEY zawiera kod klucza wirtualnego, stan przesunięcia i zdefiniowany przez użytkownika identyfikator określonego klawisza skrótu, który został naciśnięty. Aby uzyskać listę standardowych kodów kluczy wirtualnych, zobacz Winuser. h. Aby uzyskać więcej informacji na temat tej metody, zobacz [funkcję RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey).

Należy zauważyć, że flagi zmiany stanu użyte w wywołaniu `RegisterHotKey` nie są takie same jak te zwrócone przez funkcję członkowską [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) ; przed wywołaniem należy przetłumaczyć te flagi `RegisterHotKey` .

## <a name="see-also"></a>Zobacz też

[Korzystanie z CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)

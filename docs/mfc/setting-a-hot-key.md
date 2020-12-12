---
description: 'Dowiedz się więcej na temat: Ustawianie klawisza dostępu'
title: Ustawianie klawisza dostępu
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: fa713be2d478eb18b11dca27558656e5e6993076
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217188"
---
# <a name="setting-a-hot-key"></a>Ustawianie klawisza dostępu

Aplikacja może korzystać z informacji dostarczonych przez kontrolkę klawisza dostępu ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) na jeden z dwóch sposobów:

- Skonfiguruj globalny klawisz dostępu w celu aktywowania okna niepodrzędnego, wysyłając do okna komunikat [WM_SETHOTKEY](/windows/win32/inputdev/wm-sethotkey) , który ma zostać aktywowany.

- Skonfiguruj odpowiedni dla wątku klawisz dostępu, wywołując funkcję systemu Windows [funkcję RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey).

## <a name="see-also"></a>Zobacz też

[Korzystanie z CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)

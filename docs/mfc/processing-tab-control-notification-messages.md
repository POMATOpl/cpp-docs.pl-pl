---
description: 'Dowiedz się więcej na temat: przetwarzanie komunikatów powiadomień dotyczących formantów karty'
title: Przetwarzanie komunikatów powiadomień dotyczących formantu karty
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
ms.openlocfilehash: f5d81437b566143e2fc7cb1e0f275c0f9e9993de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154724"
---
# <a name="processing-tab-control-notification-messages"></a>Przetwarzanie komunikatów powiadomień dotyczących formantu karty

Gdy użytkownik kliknie karty lub przyciski, formant karty ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) wysyła komunikaty powiadomień do okna nadrzędnego. Obsługuj te komunikaty, jeśli chcesz zrobić coś w odpowiedzi. Na przykład, gdy użytkownik kliknie kartę, możesz chcieć wstępnie ustawić dane kontroli na stronie przed jej wyświetleniem.

Przetwarzaj komunikaty WM_NOTIFY z kontrolki karta w widoku lub w klasie okna dialogowego. Użyj [kreatora klas](reference/mfc-class-wizard.md) , aby utworzyć funkcję procedury obsługi [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) za pomocą instrukcji switch na podstawie tego, który komunikat powiadomienia jest obsługiwany. Aby uzyskać listę powiadomień, które formant karty może wysłać do okna nadrzędnego, zobacz sekcję **powiadomienia** w temacie Informacje o [kontrolkach kart](/windows/win32/controls/tab-control-reference) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)

---
description: 'Dowiedz się więcej o: przetwarzanie komunikatów powiadomień w kontrolkach listy'
title: Przetwarzanie komunikatów powiadomień w kontrolkach listy
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: b761f5213a73ce31484a7a252b9b441da2fe154d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154802"
---
# <a name="processing-notification-messages-in-list-controls"></a>Przetwarzanie komunikatów powiadomień w kontrolkach listy

Gdy użytkownicy klikają nagłówki kolumn, przeciągają ikony, edytują etykiety i tak dalej, formant listy ([CListCtrl](../mfc/reference/clistctrl-class.md)) wysyła komunikaty powiadomień do okna nadrzędnego. Obsługuj te komunikaty, jeśli chcesz zrobić coś w odpowiedzi. Na przykład, gdy użytkownik kliknie nagłówek kolumny, możesz chcieć posortować elementy na podstawie zawartości klikniętej kolumny, tak jak w programie Microsoft Outlook.

Przetwarzaj komunikaty WM_NOTIFY z kontrolki listy w oknie widok lub Klasa okna dialogowego. Użyj [kreatora klas](reference/mfc-class-wizard.md) , aby utworzyć funkcję procedury obsługi [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) za pomocą instrukcji switch na podstawie tego, który komunikat powiadomienia jest obsługiwany.

Aby uzyskać listę powiadomień wysyłanych przez formant listy do okna nadrzędnego, zobacz temat informacje o [kontrolce widoku listy](/windows/win32/Controls/list-view-control-reference) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Korzystanie z CListCtrl](../mfc/using-clistctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)

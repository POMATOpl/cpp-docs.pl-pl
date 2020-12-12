---
description: 'Dowiedz się więcej o: otrzymywanie powiadomień z formantów wspólnych'
title: Odbieranie powiadomienia od formantów wspólnych
ms.date: 11/04/2016
helpviewer_keywords:
- OnNotify method [MFC]
- common controls [MFC], notifications
- ON_NOTIFY macro [MFC]
- controls [MFC], notifications
- receiving notifications from common controls
- notifications [MFC], common controls
- Windows common controls [MFC], notifications
- WM_NOTIFY message
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
ms.openlocfilehash: a135dbc71447d31156ee4cfb223db410aad5218e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248557"
---
# <a name="receiving-notification-from-common-controls"></a>Odbieranie powiadomienia od formantów wspólnych

Formanty standardowe są oknami podrzędnymi, które wysyłają komunikaty powiadomień do okna nadrzędnego, gdy zdarzenia, takie jak dane wejściowe użytkownika, występują w formancie.

Aplikacja korzysta z tych komunikatów powiadomień, aby określić, jakie działania użytkownik chce wykonać. Najczęstsze formanty wysyłają komunikaty powiadomień jako wiadomości WM_NOTIFY. Formanty systemu Windows wysyłają większość komunikatów powiadomień jako wiadomości WM_COMMAND. [CWnd:: Onpowiadamianie](../mfc/reference/cwnd-class.md#onnotify) jest programem obsługi komunikatu WM_NOTIFY. Podobnie jak w przypadku `CWnd::OnCommand` , implementacja `OnNotify` wysyła komunikat powiadomienia do `OnCmdMsg` obsługi w mapach komunikatów. Wpis mapy komunikatów na potrzeby obsługi powiadomień jest ON_NOTIFY. Aby uzyskać więcej informacji, zobacz [Uwagi techniczne 61: ON_NOTIFY i WM_NOTIFY komunikatów](../mfc/tn061-on-notify-and-wm-notify-messages.md).

Alternatywnie Klasa pochodna może obsługiwać własne komunikaty powiadomień przy użyciu "odbicie komunikatów". Aby uzyskać więcej informacji, zobacz [Uwaga techniczna 62: odbicie komunikatu dla formantów systemu Windows](../mfc/tn062-message-reflection-for-windows-controls.md).

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>Pobieranie pozycji kursora w komunikacie powiadomienia

Czasami warto określić bieżącą pozycję kursora, gdy pewne komunikaty powiadomienia są odbierane przez wspólny formant. Na przykład warto określić bieżącą lokalizację kursora, gdy typowy formant odbierze NM_RCLICK komunikat powiadomienia.

Istnieje prosty sposób osiągnięcia tego przez wywołanie `CWnd::GetCurrentMessage` . Jednakże ta metoda pobiera tylko położenie kursora w momencie wysłania komunikatu. Ponieważ kursor mógł zostać przeniesiony od momentu wysłania wiadomości, należy wywołać, `CWnd::GetCursorPos` Aby uzyskać bieżącą pozycję kursora.

> [!NOTE]
> `CWnd::GetCurrentMessage` powinien być wywoływany tylko w ramach procedury obsługi komunikatów.

Dodaj następujący kod do treści programu obsługi komunikatów powiadomień (w tym przykładzie NM_RCLICK):

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

W tym momencie Lokalizacja kursora myszy jest przechowywana w `cursorPos` obiekcie.

## <a name="see-also"></a>Zobacz też

[Tworzenie i używanie kontrolek](../mfc/making-and-using-controls.md)<br/>
[Formanty](../mfc/controls-mfc.md)

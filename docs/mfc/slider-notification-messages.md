---
description: 'Dowiedz się więcej na temat: komunikaty powiadomień suwaka'
title: Komunikaty powiadomień suwaka
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
ms.openlocfilehash: fab8d515e71fd2ca8fd390a41b6d1bf68442c24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216889"
---
# <a name="slider-notification-messages"></a>Komunikaty powiadomień suwaka

Kontrolka suwaka powiadamia okno nadrzędne akcji użytkownika przez wysłanie nadrzędnej WM_HSCROLL lub WM_VSCROLL komunikatów, w zależności od orientacji kontrolki suwaka. Aby obsłużyć te komunikaty, Dodaj programy obsługi dla WM_HSCROLL i WM_VSCROLL komunikatów do okna nadrzędnego. Funkcje członkowskie [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) i [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) będą przekazywać kod powiadomienia, pozycję suwaka oraz wskaźnik do obiektu [Korzystanie CSliderCtrl](../mfc/reference/csliderctrl-class.md) . Należy zauważyć, że wskaźnik jest typu, chociaż `CScrollBar *` wskazuje na `CSliderCtrl` obiekt. Może być konieczne rzutowanie tego wskaźnika, jeśli trzeba będzie manipulować kontrolką suwaka.

Zamiast korzystać z kodów powiadomień paska przewijania, kontrolki suwaka wysyłają inny zestaw kodów powiadomień. Kontrolka suwaka wysyła TB_BOTTOM, TB_LINEDOWN, TB_LINEUP i TB_TOP kody powiadomień tylko wtedy, gdy użytkownik współdziała z kontrolką suwaka przy użyciu klawiatury. Komunikaty powiadomień TB_THUMBPOSITION i TB_THUMBTRACK są wysyłane tylko wtedy, gdy użytkownik korzysta z myszy. Kody powiadomień TB_ENDTRACK, TB_PAGEDOWN i TB_PAGEUP są wysyłane w obu przypadkach.

W poniższej tabeli przedstawiono komunikaty powiadomień kontrolki suwaka oraz zdarzenia (kody kluczy wirtualnych lub zdarzenia myszy), które powodują wysłanie powiadomień. (Aby uzyskać listę standardowych kodów kluczy wirtualnych, zobacz Winuser. h.)

|Komunikat z powiadomieniem|Zdarzenie powodujące wysłanie powiadomienia|
|--------------------------|-------------------------------------------|
|TB_BOTTOM|VK_END|
|TB_ENDTRACK|WM_KEYUP (użytkownik wydał klucz, który wysłał odpowiedni kod klucza wirtualnego)|
|TB_LINEDOWN|VK_RIGHT lub VK_DOWN|
|TB_LINEUP|VK_LEFT lub VK_UP|
|TB_PAGEDOWN|VK_NEXT (użytkownik kliknął kanał poniżej lub z prawej strony suwaka)|
|TB_PAGEUP|VK_PRIOR (użytkownik kliknął kanał powyżej lub z lewej strony suwaka)|
|TB_THUMBPOSITION|WM_LBUTTONUP po TB_THUMBTRACK komunikacie powiadomienia|
|TB_THUMBTRACK|Przesunięcie suwaka (użytkownik Przeciągnięcie suwaka)|
|TB_TOP|VK_HOME|

## <a name="see-also"></a>Zobacz też

[Korzystanie z CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Formanty](../mfc/controls-mfc.md)

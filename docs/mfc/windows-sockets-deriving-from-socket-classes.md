---
description: 'Dowiedz się więcej na temat: Windows Sockets: wyprowadzanie z klas gniazd'
title: 'Windows Sockets: wyprowadzanie z klas gniazd'
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
ms.openlocfilehash: ba3526ddde4d254ff044fa09588d7764b16fb719
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132967"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows Sockets: wyprowadzanie z klas gniazd

W tym artykule opisano niektóre funkcje, które można uzyskać przez wyjęcie własnej klasy z jednej z klas gniazd.

Aby dodać własne funkcje, można utworzyć własne klasy gniazd z [CAsyncSocket](../mfc/reference/casyncsocket-class.md) lub [CSocket](../mfc/reference/csocket-class.md) . W szczególności te klasy dostarczają wiele funkcji wirtualnych elementów członkowskich, które można przesłonić. Te funkcje obejmują [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect)i [OnClose](../mfc/reference/casyncsocket-class.md#onclose). Można przesłonić funkcje w pochodnej klasie gniazda, aby korzystać z powiadomień, które zapewniają, gdy wystąpią zdarzenia sieciowe. Struktura wywołuje te funkcje wywołania zwrotnego powiadomień, aby powiadomić Cię o ważnych zdarzeniach gniazda, takich jak otrzymanie danych, które można rozpocząć odczytywanie. Aby uzyskać więcej informacji na temat funkcji powiadomień, zobacz [Windows Sockets: powiadomienia dotyczące gniazd](../mfc/windows-sockets-socket-notifications.md).

Ponadto Klasa `CSocket` dostarcza funkcję członkowską [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) (zaawansowaną). MFC wywołuje tę funkcję, gdy gniazdo pompuje komunikaty systemu Windows. Możesz przesłonić wyszukiwanie `OnMessagePending` konkretnych komunikatów z systemu Windows i odpowiadać na nie.

Domyślna wersja `OnMessagePending` dostarczonych w klasie `CSocket` bada kolejkę komunikatów dla WM_PAINT komunikatów podczas oczekiwania na ukończenie wywołania blokującego. Wysyła wiadomości Paint w celu poprawy jakości wyświetlania. Nie robimy coś przydatnego, to ilustruje jeden ze sposobów, aby można było samodzielnie zastąpić funkcję. W innym przykładzie należy rozważyć użycie `OnMessagePending` dla poniższego zadania. Załóżmy, że podczas oczekiwania na zakończenie transakcji sieciowej zostanie wyświetlone niemodalne okno dialogowe. Okno dialogowe zawiera przycisk Anuluj, którego użytkownik może użyć do anulowania blokowania transakcji, które trwają zbyt długo. `OnMessagePending`Przesłonięcie może obsłużyć komunikaty dotyczące tego niemodalnego okna dialogowego.

W `OnMessagePending` przesłonięciu Zwróć **wartość true** lub Return z wywołania do wersji klasy bazowej `OnMessagePending` . Wywołaj wersję klasy bazowej, jeśli wykonuje ona zadania, które nadal chcesz wykonać.

Aby uzyskać więcej informacji, zobacz:

- [Windows Sockets: używanie gniazd z archiwami](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Sockets: Używanie klasy CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Sockets: blokowanie](../mfc/windows-sockets-blocking.md)

- [Windows Sockets: porządkowanie bajtów](../mfc/windows-sockets-byte-ordering.md)

- [Windows Sockets: konwertowanie ciągów](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)

---
description: 'Dowiedz się więcej na temat: Windows Sockets: blokowanie'
title: 'Windows Sockets: blokowanie'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
ms.openlocfilehash: 21d1a2fb635f3d45e639c950a7ad1748dc3dda74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197455"
---
# <a name="windows-sockets-blocking"></a>Windows Sockets: blokowanie

Ten artykuł i dwa artykuły towarzyszące wyjaśniają kilka problemów dotyczących programowania Windows Sockets. W tym artykule omówiono blokowanie. Inne problemy zostały omówione w artykułach: [Windows Sockets: porządkowanie bajtów](../mfc/windows-sockets-byte-ordering.md) i [Windows Sockets: konwertowanie ciągów](../mfc/windows-sockets-converting-strings.md).

Jeśli używasz lub pochodzi z klasy [CAsyncSocket](../mfc/reference/casyncsocket-class.md), musisz samodzielnie zarządzać tymi problemami. Jeśli używasz lub dziedziczysz z klasy [CSocket](../mfc/reference/csocket-class.md), MFC zarządza nimi.

## <a name="blocking"></a>blokowanie

Gniazdo może być w trybie "tryb blokowania" lub "tryb niezablokowany". Funkcje gniazd w trybie blokującym (lub synchronicznym) nie zwracają, dopóki nie będą mogły zakończyć działania. Jest to nazywane blokowaniem, ponieważ gniazdo, którego funkcja została wywołana, nie może nic robić — jest blokowane — do momentu wywołania zwrotnego. Wywołanie `Receive` funkcji składowej może być na przykład długotrwałe i czasochłonne, ponieważ czeka na wysłanie przez aplikację wysyłającą (jest to możliwe, jeśli używasz programu `CSocket` lub używasz `CAsyncSocket` z blokowaniem). Jeśli `CAsyncSocket` obiekt jest w trybie niezablokowanym (działa asynchronicznie), wywołanie wraca natychmiast, a bieżący kod błędu, pobieranie z funkcją elementu członkowskiego [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror) , to **WSAEWOULDBLOCK**, co oznacza, że wywołanie byłoby zablokowane, nie zostało zwrócone bezpośrednio z powodu trybu. ( `CSocket` nigdy nie zwraca **WSAEWOULDBLOCK**. Klasa zarządza blokowaniem.)

Zachowanie gniazd jest inne niż 32-bitowe i 64-bitowe systemy operacyjne (takie jak Windows 95 lub Windows 98) niż w przypadku 16-bitowych systemów operacyjnych (na przykład Windows 3,1). W przeciwieństwie do 16-bitowych systemów operacyjnych, 32-bitowe i 64-bitowe systemy operacyjne używają przeprowadzenia przeprowadzenia wielozadania i zapewniają wielowątkowość. W systemach operacyjnych 32-bitowe i 64-bitowe można umieścić gniazda w oddzielnych wątkach roboczych. Gniazdo w wątku może blokować bez zakłócania innych działań w aplikacji i bez poświęcania czasu obliczeniowego na blokowanie. Aby uzyskać informacje na temat programowania wielowątkowego, zobacz [wielowątkowość](../parallel/multithreading-support-for-older-code-visual-cpp.md)artykułu.

> [!NOTE]
> W aplikacjach wielowątkowych można użyć właściwości blokowania, `CSocket` Aby uprościć projekt programu bez wpływu na czas odpowiedzi interfejsu użytkownika. Obsługując Interakcje użytkownika w głównym wątku i `CSocket` Przetwarzanie w wątkach alternatywnych, można oddzielić te operacje logiczne. W aplikacji, która nie jest wielowątkowa, te dwa działania muszą być połączone i obsługiwane jako pojedynczy wątek, co zwykle oznacza użycie, `CAsyncSocket` Aby można było obsługiwać żądania komunikacji na żądanie lub zastępowanie `CSocket::OnMessagePending` do obsługi akcji użytkownika podczas długotrwałego działania synchronicznego.

Pozostała część tej dyskusji dotyczy dla programistów przeznaczonych dla 16-bitowych systemów operacyjnych:

Zwykle Jeśli używasz programu `CAsyncSocket` , należy unikać używania operacji blokowania i asynchronicznej obsługi w zamian. W operacjach asynchronicznych od momentu, w którym otrzymujesz kod błędu **WSAEWOULDBLOCK** po wywołaniu `Receive` , na przykład czekasz, aż `OnReceive` funkcja członkowska zostanie wywołana w celu powiadomienia użytkownika o tym, że można go ponownie odczytać. Wywołania asynchroniczne są nawiązywane przez wywołanie funkcji powiadomień o wywołaniach zwrotnych w gnieździe, na przykład [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive).

W systemie Windows blokowanie wywołań jest traktowane jako złe rozwiązanie. Domyślnie [CAsyncSocket](../mfc/reference/casyncsocket-class.md) obsługuje wywołania asynchroniczne, a użytkownik musi zarządzać blokowaniem przy użyciu powiadomień wywołania zwrotnego. Klasa [CSocket](../mfc/reference/csocket-class.md)z drugiej strony jest synchroniczna. Kieruje komunikatami systemu Windows i zarządza blokowaniem.

Aby uzyskać więcej informacji na temat blokowania, zobacz specyfikację Windows Sockets. Aby uzyskać więcej informacji na temat funkcji "on", zobacz [Windows Sockets: powiadomienia gniazda](../mfc/windows-sockets-socket-notifications.md) i [Windows Sockets: wyprowadzanie z klas gniazd](../mfc/windows-sockets-deriving-from-socket-classes.md).

Aby uzyskać więcej informacji, zobacz:

- [Windows Sockets: Używanie klasy CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Sockets: używanie gniazd z archiwami](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Sockets: Tło](../mfc/windows-sockets-background.md)

- [Windows Sockets: gniazda strumienia](../mfc/windows-sockets-stream-sockets.md)

- [Windows Sockets: gniazda datagramów](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[CAsyncSocket:: OnSend](../mfc/reference/casyncsocket-class.md#onsend)

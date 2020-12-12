---
description: 'Dowiedz się więcej na temat: Windows Sockets: powiadomienia dotyczące gniazd'
title: 'Windows Sockets: powiadomienia dotyczące gniazd'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
ms.openlocfilehash: 856e954050753545a7ff64d3e111c648dc0284d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207660"
---
# <a name="windows-sockets-socket-notifications"></a>Windows Sockets: powiadomienia dotyczące gniazd

W tym artykule opisano funkcje powiadomień w klasach gniazd. Te funkcje członkowskie są funkcjami wywołania zwrotnego, które są wywoływane przez platformę w celu powiadomienia obiektu gniazda ważnych zdarzeń. Funkcje powiadomień są następujące:

- [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive): powiadamia to gniazdo, że w buforze znajdują się dane do pobrania przez wywołanie metody [Receive](../mfc/reference/casyncsocket-class.md#receive).

- [OnSend](../mfc/reference/casyncsocket-class.md#onsend): powiadamia to gniazdo, że może teraz wysyłać dane przez wywołanie metody [send](../mfc/reference/casyncsocket-class.md#send).

- [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept): powiadamia gniazdo nasłuchiwania, które może akceptować oczekujące żądania połączenia przez wywołanie metody [Accept](../mfc/reference/casyncsocket-class.md#accept).

- [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect): powiadamia to gniazdo łączące, że próba połączenia została zakończona: być może pomyślnie lub prawdopodobnie wystąpił błąd.

- [OnClose](../mfc/reference/casyncsocket-class.md#onclose): powiadamia to gniazdo o zamknięciu gniazda, z którym jest ono połączone.

    > [!NOTE]
    >  Dodatkowa funkcja powiadomień to [OnOutOfBandData](../mfc/reference/casyncsocket-class.md#onoutofbanddata). To powiadomienie informuje gniazdo odbiorcze, że wysyła gniazdo wysyłające dane poza pasmem. Dane poza pasmem są logicznie niezależnym kanałem skojarzonym z każdą parą podłączonych gniazd strumienia. Kanał poza pasmem jest zazwyczaj używany do wysyłania "pilnych" danych. MFC obsługuje dane poza pasmem. Zaawansowani użytkownicy pracujący z klasą [CAsyncSocket](../mfc/reference/casyncsocket-class.md) mogą potrzebować korzystania ze kanału poza pasmem, ale nie są zalecane dla użytkowników klasy [CSocket](../mfc/reference/csocket-class.md) . Łatwiejszym sposobem, aby utworzyć drugie gniazdo do przekazywania takich danych. Aby uzyskać więcej informacji na temat danych poza pasmem, zobacz specyfikację Windows Sockets dostępną w Windows SDK.

W przypadku wyprowadzania z klasy należy `CAsyncSocket` zastąpić funkcje powiadomień dla tych zdarzeń sieci, które są istotne dla aplikacji. Jeśli klasa jest pochodną klasy `CSocket` , należy wybrać, czy chcesz zastąpić interesujące funkcje powiadomień. Można również użyć `CSocket` samego, w którym przypadku funkcja powiadomień domyślnie nie wykonuje żadnych operacji.

Te funkcje są wykorzystanymi funkcjami wywołania zwrotnego. `CAsyncSocket` i `CSocket` Konwertuj komunikaty na powiadomienia, ale musisz zaimplementować sposób reagowania funkcji powiadomień, jeśli chcesz ich używać. Funkcje powiadamiania są wywoływane w chwili, gdy gniazdo zostanie powiadomione o zdarzeniu, na przykład o obecności danych do odczytu.

MFC wywołuje funkcje powiadomień, aby umożliwić dostosowanie zachowania gniazda w momencie powiadomienia. Można na przykład wywoływać `Receive` z `OnReceive` funkcji powiadamiania, czyli powiadomienia o danych do odczytu, aby `Receive` je odczytać. Takie podejście nie jest konieczne, ale jest prawidłowym scenariuszem. Alternatywnie możesz użyć funkcji powiadomień do śledzenia postępu, drukowania komunikatów **śledzenia** i tak dalej.

Aby skorzystać z tych powiadomień, można zastępowanie funkcji powiadomień w pochodnej klasie gniazd i zapewnić implementację.

Podczas operacji, takiej jak otrzymywanie lub wysyłanie danych, `CSocket` obiekt zostaje synchronicznie. Podczas synchronicznego stanu wszystkie powiadomienia przeznaczone dla innych gniazd są umieszczane w kolejce, gdy bieżące gniazdo oczekuje na powiadomienie. (Na przykład w trakcie `Receive` wywołania gniazdo chce, aby powiadomienie zostało odczytane). Gdy gniazdo ukończy operację synchroniczną i przestanie być asynchroniczne, inne gniazda mogą zacząć odbierać powiadomienia znajdujące się w kolejce.

> [!NOTE]
> W programie `CSocket` `OnConnect` Funkcja powiadomień nigdy nie jest wywoływana. W przypadku połączeń nastąpi wywołanie `Connect` , które zwróci, gdy połączenie zostanie zakończone (pomyślne lub w przypadku błędu). Sposób obsługi powiadomień o połączeniach to szczegóły implementacji MFC.

Aby uzyskać szczegółowe informacje na temat każdej funkcji powiadomień, zobacz Funkcja w klasie `CAsyncSocket` w *dokumentacji MFC*. Aby uzyskać kod źródłowy i informacje o przykładach MFC, zobacz [MFC Samples](../overview/visual-cpp-samples.md#mfc-samples).

Aby uzyskać więcej informacji, zobacz:

- [Windows Sockets: Używanie klasy CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Sockets: wyprowadzanie z klas gniazd](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Sockets: jak działają gniazda z archiwami](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Sockets: blokowanie](../mfc/windows-sockets-blocking.md)

- [Windows Sockets: porządkowanie bajtów](../mfc/windows-sockets-byte-ordering.md)

- [Windows Sockets: konwertowanie ciągów](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)

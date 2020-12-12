---
description: 'Dowiedz się więcej o programie: Windows Sockets: gniazda strumienia'
title: 'Windows Sockets: gniazda strumieni'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- stream sockets [MFC]
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
ms.openlocfilehash: b9e40be06ebb1de04466b5f13a46fe82fb3b0bd2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207647"
---
# <a name="windows-sockets-stream-sockets"></a>Windows Sockets: gniazda strumieni

W tym artykule opisano gniazda strumienia, jeden z dwóch dostępnych typów gniazd systemu Windows. (Drugi typ to [gniazdo datagramu](../mfc/windows-sockets-datagram-sockets.md)).

Gniazda strumienia zapewniają przepływ danych bez granic rekordów: strumień bajtów, który może być dwukierunkowy (aplikacja jest pełna: może wysyłać i odbierać dane za pomocą gniazda). Strumienie mogą opierać się na dostarczaniu sekwencyjnych, niezduplikowanych danych. ("Sekwencyjne" oznacza, że pakiety są dostarczane w wysłanej kolejności. "Unduplikowane" oznacza, że otrzymujesz konkretny pakiet tylko raz.) Przesyłanie komunikatów strumieniowych jest gwarantowane, a strumienie są dobrze dopasowane do obsługi dużych ilości danych.

Warstwa transportu sieciowego może rozbić lub grupować dane w pakietach o rozsądnym rozmiarze. `CSocket`Klasa będzie obsługiwać pakowanie i rozpakowywanie.

Strumienie są oparte na jawnych połączeniach: gniazdo A żąda połączenia z gniazdem B; Gniazdo B akceptuje lub odrzuca żądanie połączenia.

Połączenie telefoniczne zapewnia dobrą analogową obsługę strumienia. W normalnych warunkach Strona otrzymująca słyszy to, co powiedzieć, w kolejności, w jakiej zostało napisane, bez duplikowania ani utraty. Gniazda strumienia są odpowiednie, na przykład w przypadku implementacji takich jak protokół transferu plików (FTP), które ułatwiają transferowanie plików ASCII lub binarnych o dowolnym rozmiarze.

Gniazda strumienia są preferowane w celu przechodzenia do gniazd, gdy dane muszą zostać dostarczone i gdy rozmiar danych jest duży. Aby uzyskać więcej informacji na temat gniazd strumienia, zobacz specyfikację Windows Sockets. Specyfikacja jest dostępna w Windows SDK.

Korzystanie z gniazd strumienia może być nadrzędne dla aplikacji zaprojektowanych do korzystania z gniazda datagramów do rozgłaszania do wszystkich gniazd otrzymujących w sieci, ponieważ

- Model rozgłaszania podlega problemom z zalaniem sieci (lub "burzą").

- Model klient-serwer został przyjęty w późniejszym czasie.

- Model strumienia dostarcza niezawodnego transferu danych, gdzie model datagramu nie jest obsługiwany.

- Ostatni model wykorzystuje możliwość komunikowania się między aplikacjami z gniazdami Unicode i ANSI, które Klasa CArchive przyjmuje do klasy CSocket.

    > [!NOTE]
    >  Jeśli używasz klasy `CSocket` , musisz użyć strumienia. Potwierdzenie MFC kończy się niepowodzeniem, jeśli typ gniazda zostanie określony jako **SOCK_DGRAM**.

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows Sockets: Tło](../mfc/windows-sockets-background.md)

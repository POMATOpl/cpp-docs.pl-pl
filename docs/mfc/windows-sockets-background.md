---
description: 'Dowiedz się więcej na temat: Windows Sockets: Background'
title: 'Windows Sockets: Tło'
ms.date: 11/04/2016
helpviewer_keywords:
- record-oriented data [MFC]
- e-mail [MFC]
- Internet Protocol Suite
- mail [MFC]
- communications [MFC], domain
- Windows Sockets [MFC], stream sockets
- mail [MFC], programming for
- sockets [MFC], stream sockets
- datagram sockets [MFC]
- SOCKET handle
- data types [MFC], socket
- e-mail [MFC], programming for
- X Window servers
- sequenced data flow
- stream sockets [MFC]
ms.assetid: f60d4ed2-bf23-4a0e-98d2-fee77e8473dd
ms.openlocfilehash: 9ac373f5f81dfe3914664d14122a7a6bd46cda40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214471"
---
# <a name="windows-sockets-background"></a>Windows Sockets: Tło

W tym artykule wyjaśniono charakter i przeznaczenie Windows Sockets. W tym artykule opisano również następujące artykuły:

- [Definiuje termin "Socket"](#_core_definition_of_a_socket).

- [Opisuje typ danych uchwytu gniazda](#_core_the_socket_data_type).

- [Opisuje użycie usługi Sockets](#_core_uses_for_sockets).

Specyfikacja Windows Sockets definiuje interfejs programowania sieci zgodne z binarniem dla systemu Microsoft Windows. Usługi Windows Sockets są oparte na implementacji usługi UNIX Sockets w ramach dystrybucji oprogramowania Berkeley (BSD, wersja 4,3) z uczelni w systemie Berkeley. Specyfikacja obejmuje zarówno procedury, jak i rozszerzenia w stylu BSD, charakterystyczne dla systemu Windows. Użycie usługi Windows Sockets umożliwia aplikacji komunikację między sieciami, które są zgodne z interfejsem API usługi Windows Sockets. W systemie Win32 usługi Windows Sockets zapewniają bezpieczeństwo wątków.

Wielu dostawców oprogramowania sieciowego obsługuje gniazda systemu Windows w ramach protokołów sieciowych, w tym Transmission Control Protocol/Internet Protocol (TCP/IP), Xerox Network System (XNS), protokół firmy Digital Equipment Corporation, Internet Packet Exchange/Sequenced Exchange (IPX/SPX) i inne. Mimo że obecna Specyfikacja Windows Sockets definiuje abstrakcję gniazd dla protokołu TCP/IP, każdy protokół sieciowy może być zgodny z Windows Sockets, dostarczając własną wersję biblioteki dołączanej dynamicznie (DLL), która implementuje interfejs Windows Sockets. Przykłady aplikacji komercyjnych utworzonych w usłudze Windows Sockets obejmują serwery X systemu Windows, emulatory terminali i systemy poczty elektronicznej.

> [!NOTE]
> Celem korzystania z Windows Sockets jest oddzielenie sieci podstawowej w taki sposób, aby nie trzeba było znać tej sieci i aby aplikacja mogła działać w dowolnej sieci, która obsługuje gniazda. W związku z tym Ta dokumentacja nie omawia szczegółów protokołów sieciowych.

Biblioteka MFC (MFC) obsługuje programowanie z interfejsem API Windows Sockets przez dostarczenie dwóch klas. Jedną z tych klas, `CSocket` , zapewnia wysoki poziom abstrakcji, aby uprościć programowanie komunikacji sieciowej.

Specyfikacja Windows Sockets, Windows Sockets: otwarty interfejs do obsługi sieci w systemie Microsoft Windows, teraz w wersji 1,1, został opracowany jako otwarty standard sieci przez dużą grupę osób i firm w społeczności TCP/IP i jest dostępny do użytku. Model programowania Sockets obsługuje obecnie jedną "domenę komunikacji" przy użyciu pakietu protokołu internetowego. Specyfikacja jest dostępna w Windows SDK.

> [!TIP]
> Ponieważ usługa Sockets korzysta z internetowego zestawu protokołów, są one preferowaną trasą dla aplikacji, które obsługują komunikację internetową na "autostradach informacyjnych".

## <a name="definition-of-a-socket"></a><a name="_core_definition_of_a_socket"></a> Definicja gniazda

Gniazdo jest punktem końcowym komunikacji — obiektem, za pomocą którego aplikacja Windows Sockets wysyła lub odbiera pakiety danych w sieci. Gniazdo ma typ i jest skojarzony z uruchomionym procesem i może mieć nazwę. Obecnie gniazda zwykle wymieniają dane tylko z innymi gniazdami w tej samej domenie komunikacji, która używa zestawu protokołów internetowych.

Oba rodzaje gniazd są dwukierunkowe; są przepływy danych, które mogą być przekazywane w obu kierunkach jednocześnie (pełnego dupleksu).

Dostępne są dwa typy gniazd:

- gniazda strumieni

   Gniazda strumienia zapewniają przepływ danych bez granic rekordów: strumień bajtów. Strumienie muszą zostać dostarczone i być prawidłowo sekwencjonowane i nieduplikowane.

- gniazda do przesyłania datagramów

   Gniazda datagramy obsługują przepływ danych zorientowanych na rekordy, które nie są gwarantowane i mogą nie być sekwencjonowane jako wysłane lub nieduplikowane.

"Sekwencjonowanie" oznacza, że pakiety są dostarczane w wysyłanej kolejności. "Unduplikowane" oznacza, że otrzymujesz konkretny pakiet tylko raz.

> [!NOTE]
> W przypadku niektórych protokołów sieciowych, takich jak XNS, strumienie mogą być rejestrowane jako strumienie rekordów, a nie strumienie bajtów. Jednak w ramach bardziej wspólnego protokołu TCP/IP strumienie są strumienie bajtów. Windows Sockets zapewnia poziom abstrakcji niezależny od bazowego protokołu.

Aby uzyskać informacje o tych typach i rodzaju gniazda, które mają być używane w tym przypadku, zobacz [Windows Sockets: Stream Sockets](../mfc/windows-sockets-stream-sockets.md) and [Windows Sockets: Datagram Sockets](../mfc/windows-sockets-datagram-sockets.md).

## <a name="the-socket-data-type"></a><a name="_core_the_socket_data_type"></a> Typ danych gniazda

Każdy obiekt gniazda MFC hermetyzuje dojście do obiektu Windows Sockets. Typem danych tego dojścia jest **gniazdo**. Uchwyt **gniazda** jest analogiczny do `HWND` okna dla elementu. Klasy gniazd MFC dostarczają operacje na hermetyzowanym uchwycie.

Typ danych **gniazda** został szczegółowo opisany w Windows SDK. Zobacz "Socket Data typ i wartości błędów" w obszarze Windows Sockets.

## <a name="uses-for-sockets"></a><a name="_core_uses_for_sockets"></a> Użycie dla gniazd

Gniazda są bardzo przydatne w co najmniej trzech kontekstach komunikacji:

- Modele klient/serwer.

- Scenariusze komunikacji równorzędnej, takie jak aplikacje do obsługi komunikatów.

- Wykonywanie zdalnych wywołań procedur (RPC) przez posiadanie aplikacji odbiorczej interpretuje komunikat jako wywołanie funkcji.

> [!TIP]
> Idealnym przypadkiem korzystania z funkcji MFC Sockets jest zapisanie obu punktów końcowych komunikacji: przy użyciu MFC w obu końcach. Aby uzyskać więcej informacji na temat tego tematu, w tym o tym, jak zarządzać przypadkiem podczas komunikowania się z aplikacjami nienależącymi do MFC, zobacz [Windows Sockets: porządkowanie bajtów](../mfc/windows-sockets-byte-ordering.md).

Aby uzyskać więcej informacji, zobacz Specyfikacja Windows Sockets: **ntohs**, **ntohl**, **htons**, **htonl**. Zobacz również następujące tematy:

- [Windows Sockets: używanie gniazd z archiwami](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Sockets: przykład gniazd korzystających z archiwów](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows Sockets: Używanie klasy CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)

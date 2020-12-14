---
description: 'Dowiedz się więcej na temat: Windows Sockets: porty i adresy gniazd'
title: 'Windows Sockets: porty i adresy gniazd'
ms.date: 11/04/2016
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
ms.openlocfilehash: 354505796ff60cc8968b2e10a2aac98be2eb4666
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263403"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows Sockets: porty i adresy gniazd

W tym artykule opisano terminy "Port" i "Address" używane w przypadku Windows Sockets.

## <a name="port"></a><a name="_core_port"></a> Przewożąc

Port identyfikuje unikatowy proces, dla którego można dostarczyć usługę. W obecnym kontekście port jest skojarzony z aplikacją, która obsługuje Windows Sockets. Pomysłem jest zidentyfikowanie każdej aplikacji Windows Sockets w sposób unikatowy, aby można było korzystać z więcej niż jednej aplikacji Windows Sockets uruchomionej na komputerze w tym samym czasie.

Niektóre porty są zarezerwowane dla typowych usług, takich jak FTP. Należy unikać używania tych portów, chyba że użytkownik świadczy ten rodzaj usługi. Specyfikacja systemu Windows Sockets zawiera szczegółowe informacje o tych portach zarezerwowanych. Plik WINSOCK. H również wyświetla je.

Aby umożliwić usłudze Windows Sockets DLL wybranie portu do użycia, należy przekazać 0 jako wartość portu. MFC wybiera wartość portu większą niż 1 024 dziesiętną. Możesz pobrać wartość portu wybraną przez MFC, wywołując funkcję członkowską [CAsyncSocket:: GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) .

## <a name="socket-address"></a><a name="_core_socket_address"></a> Adres gniazda

Każdy obiekt gniazda jest skojarzony z adresem protokołu internetowego (IP) w sieci. Zazwyczaj jest to nazwa komputera, taka jak "ftp.microsoft.com", lub liczba kropkowana, taka jak "128.56.22.8".

Podczas wyszukiwania w celu utworzenia gniazda zwykle nie trzeba określać własnego adresu.

> [!NOTE]
> Istnieje możliwość, że maszyna ma wiele kart sieciowych (lub aplikacja może Someday działać na takich maszynach), z których każdy reprezentuje inną sieć. Jeśli tak, może być konieczne podanie adresu, aby określić kartę sieciową, która będzie używana przez gniazdo. Jest to pewne zaawansowana użycie i możliwy problem z przenośnością.

Aby uzyskać więcej informacji, zobacz:

- [Windows Sockets: Używanie klasy CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Sockets: używanie gniazd z archiwami](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Sockets: jak działają gniazda z archiwami](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Sockets: gniazda strumienia](../mfc/windows-sockets-stream-sockets.md)

- [Windows Sockets: gniazda datagramów](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)

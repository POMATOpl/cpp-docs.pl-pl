---
description: 'Dowiedz się więcej na temat: Windows Sockets: Sekwencja operacji'
title: 'Windows Sockets: sekwencja operacji'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
ms.openlocfilehash: 89870de642abcc8e0584c2c5dc93860eda9785e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263377"
---
# <a name="windows-sockets-sequence-of-operations"></a>Windows Sockets: sekwencja operacji

W tym artykule przedstawiono obok siebie sekwencje operacji dla gniazda serwera i gniazda klienta. Ponieważ gniazda używają `CArchive` obiektów, muszą być to [gniazda strumienia](../mfc/windows-sockets-stream-sockets.md).

## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>Sekwencja operacji komunikacji gniazda usługi Stream

Do punktu konstruowania `CSocketFile` obiektu następująca sekwencja jest dokładna (z kilkoma różnicami między parametrami) dla obu `CAsyncSocket` i `CSocket` . Od tego momentu sekwencja jest ściśle dla `CSocket` . W poniższej tabeli przedstawiono sekwencję operacji związanych z konfigurowaniem komunikacji między klientem a serwerem.

### <a name="setting-up-communication-between-a-server-and-a-client"></a>Konfigurowanie komunikacji między serwerem a klientem

|Serwer|Klient|
|------------|------------|
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1, 2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`dwóch|
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3, 4|
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5000||
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> -lub-<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> -lub oba-|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> -lub-<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> -lub oba-|
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> -lub-<br /><br /> `arOut << dwValue;`ust|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> -lub-<br /><br /> `arOut << dwValue;`ust|

1. Gdzie *NPort* jest numerem portu. Zobacz [Windows Sockets: porty i adresy gniazd,](../mfc/windows-sockets-ports-and-socket-addresses.md) Aby uzyskać szczegółowe informacje o portach.

2. Serwer musi zawsze określać port, aby klienci mogli nawiązywać połączenia. `Create`Wywołanie czasami określa również adres. Po stronie klienta Użyj parametrów domyślnych, które zadają MFC do użycia dowolnego dostępnego portu.

3. Gdzie *NPort* jest numerem portu, a *strAddr* jest adresem komputera lub adresem IP.

4. Adresy maszyn mogą mieć kilka form: "ftp.microsoft.com", "microsoft.com". Adresy IP używają formy "127.54.67.32" z kropką. `Connect`Funkcja sprawdza, czy adres jest liczbą kropkowaną (chociaż nie sprawdza, czy jest to prawidłowy komputer w sieci). Jeśli nie, `Connect` przyjęto, że nazwa komputera jest jedną z pozostałych formularzy.

5. Po wywołaniu po `Accept` stronie serwera zostanie przekazane odwołanie do nowego obiektu gniazda. Najpierw należy skonstruować ten obiekt, ale nie należy go wywoływać `Create` . Należy pamiętać, że jeśli ten obiekt gniazda wykracza poza zakres, połączenie zostanie zamknięte. MFC nawiązuje połączenie nowego obiektu z uchwytem **gniazda** . Możesz skonstruować gniazdo na stosie, jak pokazano na stercie lub na stosie.

6. Archiwum i plik gniazda są zamykane, gdy wykraczają poza zakres. Destruktor obiektu gniazda wywołuje również funkcję [zamykającego](../mfc/reference/casyncsocket-class.md#close) elementu członkowskiego dla obiektu gniazda, gdy obiekt wykracza poza zakres lub został usunięty.

## <a name="additional-notes-about-the-sequence"></a>Dodatkowe uwagi dotyczące sekwencji

Sekwencja wywołań przedstawionych w powyższej tabeli dotyczy gniazda strumienia. Gniazda datagramy, które są bezpołączeniowe, nie wymagają wywołań [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect), [Listen](../mfc/reference/casyncsocket-class.md#listen)i [Accept](../mfc/reference/casyncsocket-class.md#accept) (chociaż można opcjonalnie użyć `Connect` ). Zamiast tego, jeśli używasz klasy `CAsyncSocket` , gniazda datagramy używają `CAsyncSocket::SendTo` `ReceiveFrom` funkcji i. (Jeśli używasz `Connect` z gniazdem datagram, używasz `Send` i `Receive` .) Ponieważ program nie `CArchive` działa z Datagrams, nie należy używać go `CSocket` w archiwum, jeśli gniazdo jest datagramem.

Usługa [CSocketFile](../mfc/reference/csocketfile-class.md) nie obsługuje wszystkich `CFile` funkcji; `CFile` elementy członkowskie, takie jak `Seek` , które nie mają sensu komunikacji z gniazdem, są niedostępne. Z tego względu niektóre domyślne `Serialize` funkcje MFC nie są zgodne z programem `CSocketFile` . Jest to szczególnie prawdziwe w `CEditView` klasie. Nie należy próbować serializować `CEditView` danych za pomocą `CArchive` obiektu dołączonego do `CSocketFile` obiektu za pomocą `CEditView::SerializeRaw` ; Użyj `CEditView::Serialize` zamiast tego (nieudokumentowane). Funkcja [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw) oczekuje, że obiekt pliku ma funkcje, takie jak `Seek` , które `CSocketFile` nie obsługuje.

Aby uzyskać więcej informacji, zobacz:

- [Windows Sockets: używanie gniazd z archiwami](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Sockets: Używanie klasy CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Sockets: porty i adresy gniazd](../mfc/windows-sockets-ports-and-socket-addresses.md)

- [Windows Sockets: gniazda strumienia](../mfc/windows-sockets-stream-sockets.md)

- [Windows Sockets: gniazda datagramów](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Zobacz też

[Windows Sockets w MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[Klasa CSocket](../mfc/reference/csocket-class.md)<br/>
[CAsyncSocket:: Create](../mfc/reference/casyncsocket-class.md#create)<br/>
[CAsyncSocket:: Close](../mfc/reference/casyncsocket-class.md#close)

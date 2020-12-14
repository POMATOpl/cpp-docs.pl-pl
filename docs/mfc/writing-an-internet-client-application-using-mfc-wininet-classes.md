---
description: 'Dowiedz się więcej o: pisaniu aplikacji klienckiej internetowej przy użyciu klas MFC WinInet'
title: Pisanie klienckich aplikacji internetowych przy użyciu klas MFC WinInet
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
ms.openlocfilehash: 61cfe3e9892f2bde6d233728b7b95ca0edd16ee8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189135"
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>Pisanie klienckich aplikacji internetowych przy użyciu klas MFC WinInet

Podstawą każdej aplikacji klienckiej internetowej jest sesja internetowa. MFC implementuje sesje internetowe jako obiekty klasy [CInternetSession](../mfc/reference/cinternetsession-class.md). Za pomocą tej klasy można utworzyć jedną sesję internetową lub kilka równoczesnych sesji.

Aby komunikować się z serwerem, wymagany jest obiekt [CInternetConnection](../mfc/reference/cinternetconnection-class.md) oraz `CInternetSession` . Można utworzyć `CInternetConnection` za pomocą [CInternetSession:: GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection), [CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection)lub [CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection). Każdy z tych wywołań jest specyficzny dla typu protokołu. Te wywołania nie otwierają pliku na serwerze w celu odczytu lub zapisu. Jeśli zamierzasz odczytywać lub zapisywać dane, musisz otworzyć plik jako osobny krok.

W przypadku większości sesji Internetu `CInternetSession` obiekt pracuje z ręką z obiektem [CInternetFile](../mfc/reference/cinternetfile-class.md) :

- W przypadku sesji internetowej należy utworzyć wystąpienie elementu [CInternetSession](../mfc/reference/cinternetsession-class.md).

- Jeśli sesja internetowa odczytuje lub zapisuje dane, należy utworzyć wystąpienie `CInternetFile` (lub jego podklasy, [CHttpFile](../mfc/reference/chttpfile-class.md) lub [CGopherFile](../mfc/reference/cgopherfile-class.md)). Najprostszym sposobem odczytywania danych jest wywołanie [CInternetSession:: OpenURL](../mfc/reference/cinternetsession-class.md#openurl). Ta funkcja analizuje adres URL (Universal Resource Locator) dostarczony przez Ciebie, otwiera połączenie z serwerem określonym przez adres URL i zwraca obiekt tylko do odczytu `CInternetFile` . `CInternetSession::OpenURL` nie jest specyficzny dla jednego typu protokołu — to samo wywołanie działa dla dowolnego adresu URL FTP, HTTP lub gopher. `CInternetSession::OpenURL` nawet działa z lokalnymi plikami (zwracając a `CStdioFile` zamiast a `CInternetFile` ).

- Jeśli sesja internetowa nie odczytuje ani nie zapisuje danych, ale wykonuje inne zadania, na przykład usuwając plik w katalogu FTP, może nie być konieczne tworzenie wystąpienia `CInternetFile` .

Istnieją dwa sposoby tworzenia `CInternetFile` obiektu:

- Jeśli używasz `CInternetSession::OpenURL` , aby nawiązać połączenie z serwerem, wywołanie `OpenURL` zwraca wartość `CStdioFile` .

- W przypadku używania `CInternetSession::GetFtpConnection` , `GetGopherConnection` , lub do nawiązywania połączenia z serwerem należy `GetHttpConnection` wywołać `CFtpConnection::OpenFile` , `CGopherConnection::OpenFile` , lub `CHttpConnection::OpenRequest` , odpowiednio, zwrócić `CInternetFile` , `CGopherFile` , lub `CHttpFile` , odpowiednio.

Kroki implementowania aplikacji klienckiej internetowej różnią się w zależności od tego, czy tworzysz ogólnego klienta internetowego w oparciu o `OpenURL` lub klienta specyficznego dla protokołu przy użyciu jednej z tych `GetConnection` funkcji.

## <a name="what-do-you-want-to-know-more-about"></a>Co chcesz dowiedzieć się więcej o

- [Jak mogę napisać internetową aplikację kliencką, która działa ogólnie z wykorzystaniem protokołów FTP, HTTP i gopher](../mfc/steps-in-a-typical-internet-client-application.md)

- [Jak mogę napisanie aplikacji klienckiej FTP, która otwiera plik](../mfc/steps-in-a-typical-ftp-client-application.md)

- [Jak mogę napisanie aplikacji klienckiej FTP, która nie otwiera pliku, ale wykonuje operację katalogową, taką jak usuwanie pliku](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)

- [Jak mogę napisanie aplikacji klienckiej gopher](../mfc/steps-in-a-typical-gopher-client-application.md)

- [Jak mogę napisanie aplikacji klienckiej HTTP](../mfc/steps-in-a-typical-http-client-application.md)

## <a name="see-also"></a>Zobacz też

[Rozszerzenia internetowe Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Klasy MFC do tworzenia aplikacji internetowych klienta](../mfc/mfc-classes-for-creating-internet-client-applications.md)<br/>
[Wymagania wstępne dotyczące klas klientów internetowych](../mfc/prerequisites-for-internet-client-classes.md)

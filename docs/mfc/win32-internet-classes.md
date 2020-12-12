---
description: 'Dowiedz się więcej na temat: klasy internetowe Win32'
title: Klasy internetowe Win32
ms.date: 09/12/2018
f1_keywords:
- vc.classes.win32
helpviewer_keywords:
- Internet classes [MFC]
- WinInet classes [MFC], classes
- Win32 [MFC], Internet classes
- Windows API [MFC], Internet classes
ms.assetid: b49601d5-3025-4068-9408-316b54ee4375
ms.openlocfilehash: 8b6acad5f867444c33ed86cb7e70f4f1eec42df0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197481"
---
# <a name="win32-internet-classes"></a>Klasy internetowe Win32

MFC zawija Internet (WinInet) i technologię ActiveX, aby ułatwić programowanie Internetu.

>[!IMPORTANT]
> Kontrolka ActiveX to Starsza technologia, która nie powinna być używana do nowych celów programistycznych. Aby uzyskać więcej informacji na temat nowoczesnych technologii, które zastępują ActiveX, zobacz [kontrolki ActiveX](activex-controls.md).

[CInternetSession](../mfc/reference/cinternetsession-class.md)<br/>
Tworzy i inicjuje jedną sesję internetową lub kilka równoczesnych sesji internetowych oraz, w razie potrzeby, opisuje połączenie z serwerem proxy.

[CInternetConnection](../mfc/reference/cinternetconnection-class.md)<br/>
Zarządza połączeniem z serwerem internetowym.

[CInternetFile](../mfc/reference/cinternetfile-class.md)<br/>
Ta klasa i jej klasy pochodne umożliwiają dostęp do plików w systemach zdalnych, które korzystają z protokołów internetowych.

[CHttpConnection](../mfc/reference/chttpconnection-class.md)<br/>
Zarządza połączeniem z serwerem HTTP.

[CHttpFile](../mfc/reference/chttpfile-class.md)<br/>
Oferuje funkcje znajdowania i odczytywania plików na serwerze HTTP.

[CGopherFile](../mfc/reference/cgopherfile-class.md)<br/>
Oferuje funkcje znajdowania i odczytywania plików na serwerze gopher.

[CFtpConnection](../mfc/reference/cftpconnection-class.md)<br/>
Zarządza połączeniem z serwerem FTP.

[CGopherConnection](../mfc/reference/cgopherconnection-class.md)<br/>
Zarządza połączeniem z serwerem gopher.

[CFileFind](../mfc/reference/cfilefind-class.md)<br/>
Wykonuje wyszukiwanie plików lokalnych i internetowych.

[CFtpFileFind](../mfc/reference/cftpfilefind-class.md)<br/>
Pomoc dla wyszukiwania w pliku internetowym w przypadku serwerów FTP.

[CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)<br/>
Pomoc dla wyszukiwania w pliku internetowym serwerów Gopher.

[CGopherLocator](../mfc/reference/cgopherlocator-class.md)<br/>
Pobiera gopher "lokalizator" z serwera gopher, określa typ lokalizatora i udostępnia lokalizator `CGopherFileFind` .

[CInternetException](../mfc/reference/cinternetexception-class.md)<br/>
Reprezentuje warunek wyjątku związany z operacją internetową.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../mfc/class-library-overview.md)

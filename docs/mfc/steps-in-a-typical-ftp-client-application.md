---
description: 'Dowiedz się więcej na temat: kroki w typowej aplikacji klienckiej FTP'
title: Kroki wykonywane w typowej aplikacji klienckiej FTP
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
ms.openlocfilehash: caac613adf3ad886c4b36ae567a3b8c5c928ee10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216642"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>Kroki wykonywane w typowej aplikacji klienckiej FTP

Typowa aplikacja kliencka FTP tworzy obiekt [CInternetSession](../mfc/reference/cinternetsession-class.md) i [CFtpConnection](../mfc/reference/cftpconnection-class.md) . Należy zauważyć, że te klasy MFC WinInet nie kontrolują ustawień typu serwera proxy; Usługi IIS.

W poniższej tabeli przedstawiono kroki, które można wykonać w typowej aplikacji klienckiej FTP.

|Twój cel|Akcje wykonywane|Efekty|
|---------------|----------------------|-------------|
|Rozpocznij sesję FTP.|Utwórz obiekt [CInternetSession](../mfc/reference/cinternetsession-class.md) .|Inicjuje WinInet i nawiązuje połączenie z serwerem.|
|Nawiąż połączenie z serwerem FTP.|Użyj [CInternetSession:: GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Zwraca obiekt [CFtpConnection](../mfc/reference/cftpconnection-class.md) .|
|Przejdź do nowego katalogu FTP na serwerze.|Użyj [CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Zmienia katalog, z którym użytkownik jest aktualnie połączony na serwerze.|
|Znajdź pierwszy plik w katalogu FTP.|Użyj [CFtpFileFind:: FindFile —](../mfc/reference/cftpfilefind-class.md#findfile).|Znajduje pierwszy plik. Zwraca wartość FALSE, jeśli nie znaleziono plików.|
|Znajdź następny plik w katalogu FTP.|Użyj [CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Znajduje następny plik. Zwraca wartość FALSE, jeśli nie można odnaleźć pliku.|
|Otwórz plik znaleziony przez program `FindFile` lub `FindNextFile` do odczytu lub zapisu.|Użyj [CFtpConnection:: OpenFile](../mfc/reference/cftpconnection-class.md#openfile), używając nazwy pliku zwróconej przez [FindFile —](../mfc/reference/cftpfilefind-class.md#findfile) lub [FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Otwiera plik na serwerze na potrzeby odczytu lub zapisu. Zwraca obiekt [CInternetFile](../mfc/reference/cinternetfile-class.md) .|
|Odczytaj lub Zapisz do pliku.|Użyj [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read) lub [CInternetFile:: Write](../mfc/reference/cinternetfile-class.md#write).|Odczytuje lub zapisuje określoną liczbę bajtów przy użyciu dostarczonego buforu.|
|Obsługa wyjątków.|Użyj klasy [CInternetException](../mfc/reference/cinternetexception-class.md) .|Obsługuje wszystkie popularne typy wyjątków internetowych.|
|Zakończ sesję FTP.|Metoda Dispose obiektu [CInternetSession](../mfc/reference/cinternetsession-class.md) .|Automatycznie czyści dojścia i połączenia otwartych plików.|

## <a name="see-also"></a>Zobacz też

[Rozszerzenia internetowe Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Wymagania wstępne dotyczące klas klientów internetowych](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Pisanie aplikacji klienckiej internetowej przy użyciu klas MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

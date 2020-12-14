---
description: 'Dowiedz się więcej na temat: kroki w typowej aplikacji klienckiej FTP do usunięcia pliku'
title: Procedura usuwania pliku w typowej aplikacji klienckiej FTP
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
ms.openlocfilehash: 0de5ba71ac127a44c964571d243997bcb49faaa0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216655"
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>Procedura usuwania pliku w typowej aplikacji klienckiej FTP

W poniższej tabeli przedstawiono kroki, które można wykonać w typowej aplikacji klienckiej FTP, która usuwa plik.

|Twój cel|Akcje wykonywane|Efekty|
|---------------|----------------------|-------------|
|Rozpocznij sesję FTP.|Utwórz obiekt [CInternetSession](../mfc/reference/cinternetsession-class.md) .|Inicjuje WinInet i nawiązuje połączenie z serwerem.|
|Nawiąż połączenie z serwerem FTP.|Użyj [CInternetSession:: GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Zwraca obiekt [CFtpConnection](../mfc/reference/cftpconnection-class.md) .|
|Upewnij się, że jesteś w odpowiednim katalogu na serwerze FTP.|Użyj [CFtpConnection:: GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory) lub [CFtpConnection:: GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl).|Zwraca nazwę lub adres URL katalogu, z którym użytkownik jest aktualnie połączony na serwerze, w zależności od wybranej funkcji członkowskiej.|
|Przejdź do nowego katalogu FTP na serwerze.|Użyj [CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Zmienia katalog, z którym użytkownik jest aktualnie połączony na serwerze.|
|Znajdź pierwszy plik w katalogu FTP.|Użyj [CFtpFileFind:: FindFile —](../mfc/reference/cftpfilefind-class.md#findfile).|Znajduje pierwszy plik. Zwraca wartość FALSE, jeśli nie znaleziono plików.|
|Znajdź następny plik w katalogu FTP.|Użyj [CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Znajduje następny plik. Zwraca wartość FALSE, jeśli nie można odnaleźć pliku.|
|Usuń plik znaleziony przez `FindFile` lub `FindNextFile` .|Użyj [CFtpConnection:: Remove](../mfc/reference/cftpconnection-class.md#remove), używając nazwy pliku zwróconej przez `FindFile` lub `FindNextFile` .|Usuwa plik na serwerze w celu odczytu lub zapisu.|
|Obsługa wyjątków.|Użyj klasy [CInternetException](../mfc/reference/cinternetexception-class.md) .|Obsługuje wszystkie popularne typy wyjątków internetowych.|
|Zakończ sesję FTP.|Metoda Dispose obiektu [CInternetSession](../mfc/reference/cinternetsession-class.md) .|Automatycznie czyści dojścia i połączenia otwartych plików.|

## <a name="see-also"></a>Zobacz też

[Rozszerzenia internetowe Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Wymagania wstępne dotyczące klas klientów internetowych](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Pisanie aplikacji klienckiej internetowej przy użyciu klas MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

---
description: 'Dowiedz się więcej o: procedurach w typowej aplikacji klienckiej HTTP'
title: Kroki wykonywane w typowej aplikacji klienckiej HTTP
ms.date: 11/04/2016
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
ms.openlocfilehash: 0f08ca7629c389df67b579b8c20acceeb16b0cd3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216603"
---
# <a name="steps-in-a-typical-http-client-application"></a>Kroki wykonywane w typowej aplikacji klienckiej HTTP

W poniższej tabeli przedstawiono kroki, które można wykonać w typowej aplikacji klienckiej HTTP:

|Twój cel|Akcje wykonywane|Efekty|
|---------------|----------------------|-------------|
|Rozpocznij sesję HTTP.|Utwórz obiekt [CInternetSession](../mfc/reference/cinternetsession-class.md) .|Inicjuje WinInet i nawiązuje połączenie z serwerem.|
|Nawiąż połączenie z serwerem HTTP.|Użyj [CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection).|Zwraca obiekt [CHttpConnection](../mfc/reference/chttpconnection-class.md) .|
|Otwórz żądanie HTTP.|Użyj [CHttpConnection:: OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest).|Zwraca obiekt [CHttpFile](../mfc/reference/chttpfile-class.md) .|
|Wyślij żądanie HTTP.|Użyj [CHttpFile:: AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders) i [CHttpFile:: SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|Znajduje plik. Zwraca wartość FALSE, jeśli nie można odnaleźć pliku.|
|Odczytaj plik.|Użyj [CHttpFile](../mfc/reference/chttpfile-class.md).|Odczytuje określoną liczbę bajtów przy użyciu dostarczonego buforu.|
|Obsługa wyjątków.|Użyj klasy [CInternetException](../mfc/reference/cinternetexception-class.md) .|Obsługuje wszystkie popularne typy wyjątków internetowych.|
|Zakończ sesję HTTP.|Metoda Dispose obiektu [CInternetSession](../mfc/reference/cinternetsession-class.md) .|Automatycznie czyści dojścia i połączenia otwartych plików.|

## <a name="see-also"></a>Zobacz też

[Rozszerzenia internetowe Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Wymagania wstępne dotyczące klas klientów internetowych](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Pisanie aplikacji klienckiej internetowej przy użyciu klas MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

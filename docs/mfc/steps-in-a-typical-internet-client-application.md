---
description: 'Dowiedz się więcej o: krokach w typowej aplikacji klienckiej internetowej'
title: Kroki wykonywane w typowej klienckiej aplikacji internetowej
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
ms.openlocfilehash: 9660687136361efb0256ecdd1fd19b577c46ab26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216551"
---
# <a name="steps-in-a-typical-internet-client-application"></a>Kroki wykonywane w typowej klienckiej aplikacji internetowej

W poniższej tabeli przedstawiono kroki, które można wykonać w typowej aplikacji klienckiej internetowej.

|Twój cel|Akcje wykonywane|Efekty|
|---------------|----------------------|-------------|
|Rozpocznij sesję internetową.|Utwórz obiekt [CInternetSession](../mfc/reference/cinternetsession-class.md) .|Inicjuje WinInet i nawiązuje połączenie z serwerem.|
|Ustaw opcję zapytania internetowego (na przykład limit czasu lub liczba ponownych prób).|Użyj [CInternetSession:: SetOption](../mfc/reference/cinternetsession-class.md#setoption).|Zwraca wartość FALSE, jeśli operacja nie powiodła się.|
|Ustanów funkcję wywołania zwrotnego do monitorowania stanu sesji.|Użyj [CInternetSession:: EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback).|Ustanawia wywołanie zwrotne do [CInternetSession:: OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback). Przesłoń `OnStatusCallback` , aby utworzyć własną procedurę wywołania zwrotnego.|
|Nawiąż połączenie z serwerem internetowym, serwerem intranetowym lub plikiem lokalnym.|Użyj [CInternetSession:: OpenURL](../mfc/reference/cinternetsession-class.md#openurl).|Analizuje adres URL i otwiera połączenie z określonym serwerem. Zwraca [CStdioFile](../mfc/reference/cstdiofile-class.md) (w przypadku przekazania `OpenURL` nazwy pliku lokalnego). Jest to obiekt, za pośrednictwem którego uzyskujesz dostęp do danych pobieranych z serwera lub pliku.|
|Odczytaj plik.|Użyj [CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read).|Odczytuje określoną liczbę bajtów przy użyciu dostarczonego buforu.|
|Obsługa wyjątków.|Użyj klasy [CInternetException](../mfc/reference/cinternetexception-class.md) .|Obsługuje wszystkie popularne typy wyjątków internetowych.|
|Zakończ sesję internetową.|Metoda Dispose obiektu [CInternetSession](../mfc/reference/cinternetsession-class.md) .|Automatycznie czyści dojścia i połączenia otwartych plików.|

## <a name="see-also"></a>Zobacz też

[Rozszerzenia internetowe Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Wymagania wstępne dotyczące klas klientów internetowych](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Pisanie aplikacji klienckiej internetowej przy użyciu klas MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

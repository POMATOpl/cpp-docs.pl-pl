---
description: 'Dowiedz się więcej o: procedurach w typowej aplikacji klienckiej gopher'
title: Kroki wykonywane w typowej aplikacji klienckiej Gopher
ms.date: 11/04/2016
helpviewer_keywords:
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
ms.openlocfilehash: 23940457acf52009b6d334deec129324a53a7583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216629"
---
# <a name="steps-in-a-typical-gopher-client-application"></a>Kroki wykonywane w typowej aplikacji klienckiej Gopher

W poniższej tabeli przedstawiono kroki, które można wykonać w typowej aplikacji klienckiej gopher.

|Twój cel|Akcje wykonywane|Efekty|
|---------------|----------------------|-------------|
|Rozpocznij sesję gopher.|Utwórz obiekt [CInternetSession](../mfc/reference/cinternetsession-class.md) .|Inicjuje WinInet i nawiązuje połączenie z serwerem.|
|Nawiąż połączenie z serwerem gopher.|Użyj [CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection).|Zwraca obiekt [CGopherConnection](../mfc/reference/cgopherconnection-class.md) .|
|Znajdź pierwszy zasób w usłudze gopher.|Użyj [CGopherFileFind:: FindFile —](../mfc/reference/cgopherfilefind-class.md#findfile).|Znajduje pierwszy plik. Zwraca wartość FALSE, jeśli nie znaleziono plików.|
|Znajdź następny zasób w usłudze gopher.|Użyj [CGopherFileFind:: FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile).|Znajduje następny plik. Zwraca wartość FALSE, jeśli nie można odnaleźć pliku.|
|Otwórz plik znaleziony przez program `FindFile` lub `FindNextFile` do odczytu.|Pobierz lokalizator gopher przy użyciu [CGopherFileFind:: Getlocatorer](../mfc/reference/cgopherfilefind-class.md#getlocator). Użyj [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Otwiera plik określony przez lokalizatora. `OpenFile` zwraca obiekt [CGopherFile](../mfc/reference/cgopherfile-class.md) .|
|Otwórz plik przy użyciu dostarczonej przez Ciebie lokalizatora gopher.|Utwórz Lokalizator usługi gopher przy użyciu [CGopherConnection:: Islocatorer](../mfc/reference/cgopherconnection-class.md#createlocator). Użyj [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Otwiera plik określony przez lokalizatora. `OpenFile` zwraca obiekt [CGopherFile](../mfc/reference/cgopherfile-class.md) .|
|Odczytaj plik.|Użyj [CGopherFile](../mfc/reference/cgopherfile-class.md).|Odczytuje określoną liczbę bajtów przy użyciu dostarczonego buforu.|
|Obsługa wyjątków.|Użyj klasy [CInternetException](../mfc/reference/cinternetexception-class.md) .|Obsługuje wszystkie popularne typy wyjątków internetowych.|
|Zakończ sesję gopher.|Metoda Dispose obiektu [CInternetSession](../mfc/reference/cinternetsession-class.md) .|Automatycznie czyści dojścia i połączenia otwartych plików.|

## <a name="see-also"></a>Zobacz też

[Rozszerzenia internetowe Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Wymagania wstępne dotyczące klas klientów internetowych](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Pisanie aplikacji klienckiej internetowej przy użyciu klas MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)

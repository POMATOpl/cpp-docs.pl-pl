---
description: 'Dowiedz się więcej na temat: podstawowe informacje o programie WinInet'
title: Podstawy WinInet
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: 1ba8f9b898476849ca9bbb39b7850bbce3605154
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172781"
---
# <a name="wininet-basics"></a>Podstawy WinInet

Za pomocą usługi WinInet można dodać obsługę FTP, aby pobierać i ładować pliki z aplikacji. Można przesłonić [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) i użyć parametru *dwContext* w celu udostępnienia użytkownikom informacji o postępie podczas wyszukiwania i pobierania plików.

Ten artykuł zawiera następujące tematy:

- [Tworzenie bardzo prostej przeglądarki](#_core_create_a_very_simple_browser)

- [Pobierz stronę sieci Web](#_core_download_a_web_page)

- [Plik FTP](#_core_ftp_a_file)

- [Pobieranie katalogu gopher](#_core_retrieve_a_gopher_directory)

- [Wyświetlanie informacji o postępie podczas przesyłania plików](#_core_display_progress_information_while_transferring_files)

Poniższe fragmenty kodu przedstawiają sposób tworzenia prostej przeglądarki, pobierania strony sieci Web, FTP pliku i wyszukiwania pliku gopher. Nie są one przeznaczone jako kompletne przykłady, a nie wszystkie zawierają obsługę wyjątków.

Aby uzyskać dodatkowe informacje na temat usługi WinInet, zobacz [rozszerzenia internetowe Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md).

## <a name="create-a-very-simple-browser"></a><a name="_core_create_a_very_simple_browser"></a> Tworzenie bardzo prostej przeglądarki

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

## <a name="download-a-web-page"></a><a name="_core_download_a_web_page"></a> Pobierz stronę sieci Web

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

## <a name="ftp-a-file"></a><a name="_core_ftp_a_file"></a> Plik FTP

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

## <a name="retrieve-a-gopher-directory"></a><a name="_core_retrieve_a_gopher_directory"></a> Pobieranie katalogu gopher

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>Użyj OnStatusCallback

W przypadku korzystania z klas WinInet można użyć elementu [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) aplikacji obiektu [CInternetSession](../mfc/reference/cinternetsession-class.md) , aby pobrać informacje o stanie. Jeśli tworzysz własny `CInternetSession` obiekt, przesłonisz `OnStatusCallback` i włączysz wywołania zwrotne stanu, MFC wywoła `OnStatusCallback` funkcję z informacjami o postępie dotyczącymi wszystkich działań w tej sesji internetowej.

Ponieważ pojedyncza sesja może obsługiwać kilka połączeń (które w okresie istnienia mogą wykonywać wiele różnych operacji), `OnStatusCallback` wymaga mechanizmu identyfikacji każdej zmiany stanu przy użyciu określonego połączenia lub transakcji. Ten mechanizm jest dostarczany przez parametr identyfikatora kontekstu podany w wielu funkcjach składowych w klasach obsługi WinInet. Ten parametr jest zawsze typu **DWORD** i ma zawsze nazwę *dwContext*.

Kontekst przypisany do określonego obiektu internetowego jest używany tylko w celu zidentyfikowania działania, którego przyczyną jest obiekt w `OnStatusCallback` elemencie członkowskim `CInternetSession` obiektu. Wywołanie `OnStatusCallback` odbiera kilka parametrów; te parametry współpracują ze sobą, aby określić, jaki postęp został wykonany, dla którego transakcja i połączenie.

Podczas tworzenia `CInternetSession` obiektu można określić parametr *dwContext* w konstruktorze. `CInternetSession` sama sama nie używa identyfikatora kontekstu; Zamiast tego przekazuje identyfikator kontekstu do wszystkich obiektów pochodnych **InternetConnection**, które nie otrzymują jawnie identyfikatora kontekstu. Z kolei te `CInternetConnection` obiekty przekażą identyfikator kontekstu wraz z `CInternetFile` tworzonymi przez siebie obiektami, jeśli nie określisz jawnie innego identyfikatora kontekstu. Jeśli z drugiej strony określisz określony identyfikator kontekstu, obiekt i wszystkie wykonane zadania zostaną skojarzone z tym IDENTYFIKATORem kontekstu. Identyfikatory kontekstu mogą służyć do identyfikowania, jakie informacje o stanie są przekazywane do użytkownika w `OnStatusCallback` funkcji.

## <a name="display-progress-information-while-transferring-files"></a><a name="_core_display_progress_information_while_transferring_files"></a> Wyświetlanie informacji o postępie podczas przesyłania plików

Na przykład jeśli napiszesz aplikację, która tworzy połączenie z serwerem FTP w celu odczytania pliku, a także nawiąże połączenie z serwerem HTTP w celu uzyskania strony sieci Web, będziesz mieć `CInternetSession` obiekt, dwa `CInternetConnection` obiekty (jeden z nich to, `CFtpSession` a drugie `CHttpSession` ) i dwa `CInternetFile` obiekty (po jednym dla każdego połączenia). Jeśli zostały użyte wartości domyślne parametrów *dwContext* , nie można rozróżnić `OnStatusCallback` wywołań wskazujących postęp połączenia FTP i wywołań wskazujących postęp połączenia HTTP z serwerem... W przypadku określenia identyfikatora *dwContext* , który można później przetestować dla programu w programie `OnStatusCallback` , wiadomo, która operacja wygenerowała wywołanie zwrotne.

## <a name="see-also"></a>Zobacz też

[Podstawy programowania internetowego MFC](../mfc/mfc-internet-programming-basics.md)<br/>
[Rozszerzenia internetowe Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)

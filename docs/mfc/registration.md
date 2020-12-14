---
description: 'Dowiedz się więcej o usłudze: Rejestracja'
title: Rejestracja
ms.date: 11/04/2016
helpviewer_keywords:
- servers [MFC], initializing
- initializing servers [MFC]
- OLE, registration
- installing servers [MFC]
- registry [MFC], OLE item database
- registration databases [MFC]
- servers [MFC], installing
- OLE server applications [MFC], registering servers
ms.assetid: 991d5684-72c1-4f9e-a09a-9184ed12bbb9
ms.openlocfilehash: 8254f4b1ab8a005623650794adc8be0bd06cfdff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218124"
---
# <a name="registration"></a>Rejestracja

Gdy użytkownik chce wstawić element OLE do aplikacji, OLE wyświetla listę typów obiektów do wyboru. OLE pobiera tę listę z bazy danych rejestracji systemu, która zawiera informacje dostarczone przez wszystkie aplikacje serwera. Po zarejestrowaniu się serwera wpisy umieszczane w bazie danych rejestracji systemu (rejestr) opisują każdy typ obiektu, który dostarcza, rozszerzenia plików i ścieżki do siebie, między innymi informacjami.

Struktury i biblioteki dołączane dynamicznie (DLL) systemu OLE używają tego rejestru do określenia typów elementów OLE, które są dostępne w systemie. Biblioteki DLL systemu OLE używają również tego rejestru, aby określić, jak uruchomić aplikację serwera, gdy połączony lub osadzony obiekt jest aktywowany.

W tym artykule opisano, co aplikacja serwera musi wykonać, gdy jest zainstalowana, i za każdym razem, gdy jest ona wykonywana.

Aby uzyskać szczegółowe informacje o bazie danych rejestracji systemu i formacie plików reg używanych do ich aktualizacji, zobacz *informacje dotyczące programisty OLE*.

## <a name="server-installation"></a><a name="_core_server_installation"></a> Instalacja serwera

Podczas pierwszej instalacji aplikacji serwera należy zarejestrować wszystkie typy elementów OLE, które obsługuje. Serwer może także aktualizować bazę danych rejestracji systemu za każdym razem, gdy jest wykonywana jako aplikacja autonomiczna. Dzięki temu baza danych rejestracji jest aktualna, jeśli plik wykonywalny serwera jest przenoszony.

> [!NOTE]
> Aplikacje MFC wygenerowane przez Kreatora aplikacji są automatycznie rejestrowane, gdy są uruchamiane jako aplikacje autonomiczne.

Jeśli chcesz zarejestrować aplikację podczas instalacji, użyj programu RegEdit.exe. Jeśli dołączysz program instalacyjny z aplikacją, uruchom program instalacyjny "regedit/S *nazwa_aplikacji*. reg". (Flaga/S wskazuje operację dyskretną, czyli nie wyświetla okna dialogowego raportowania pomyślnego zakończenia polecenia). W przeciwnym razie Poinstruuj użytkownika, aby ręcznie uruchomił regedit.

> [!NOTE]
> Plik reg utworzony przez Kreatora aplikacji nie zawiera pełnej ścieżki pliku wykonywalnego. Program instalacyjny musi zmodyfikować plik reg w taki sposób, aby zawierał pełną ścieżkę do pliku wykonywalnego, lub zmodyfikować zmienną środowiskową PATH, aby uwzględnić katalog instalacji.

Regedit Scala zawartość pliku tekstowego reg z bazą danych rejestracji. Aby sprawdzić bazę danych lub naprawić ją, użyj Edytora rejestru. Pamiętaj, aby uniknąć usuwania istotnych wpisów OLE.

## <a name="server-initialization"></a><a name="_core_server_initialization"></a> Inicjowanie serwera

Podczas tworzenia aplikacji serwera za pomocą Kreatora aplikacji Kreator automatycznie uzupełnia wszystkie zadania inicjowania. W tej sekcji opisano, co należy zrobić w przypadku ręcznego zapisywania aplikacji serwera.

Gdy aplikacja serwera jest uruchamiana przez aplikację kontenera, biblioteki DLL systemu OLE dodają opcję "przełącznikiem/Embedding" do wiersza polecenia serwera. Zachowanie aplikacji serwera różni się w zależności od tego, czy zostało uruchomione przez kontener, więc pierwszy element, który powinien wykonać aplikacja po rozpoczęciu wykonywania, sprawdza obecność opcji "przełącznikiem/Embedding" lub "-osadzania" w wierszu polecenia. Jeśli ten przełącznik istnieje, Załaduj inny zestaw zasobów pokazujący serwer jako aktywny lub w pełni otwarty. Aby uzyskać więcej informacji, zobacz [menu i zasoby: Dodatki do serwera](../mfc/menus-and-resources-server-additions.md).

Aplikacja serwera powinna również wywołać `CWinApp::RunEmbedded` funkcję, aby przeanalizować wiersz polecenia. Jeśli zwraca wartość różną od zera, aplikacja nie powinna wyświetlać jej okna, ponieważ została uruchomiona z aplikacji kontenera, a nie jako aplikacji autonomicznej. Ta funkcja aktualizuje wpis serwera w bazie danych rejestracji systemu i wywołuje `RegisterAll` dla Ciebie funkcję członkowską, wykonując rejestrację wystąpienia.

Po uruchomieniu aplikacji serwera należy upewnić się, że może ona wykonać rejestrację wystąpienia. Rejestracja wystąpienia informuje biblioteki DLL systemu OLE, że serwer jest aktywny i jest gotowy do odbierania żądań z kontenerów. Nie dodaje wpisu do bazy danych rejestracji. Wykonaj rejestrację wystąpienia serwera, wywołując `ConnectTemplate` funkcję członkowską zdefiniowaną przez `COleTemplateServer` . Spowoduje to połączenie `CDocTemplate` obiektu z `COleTemplateServer` obiektem.

`ConnectTemplate`Funkcja przyjmuje trzy parametry: *Identyfikator CLSID* serwera, wskaźnik do `CDocTemplate` obiektu i Flaga wskazująca, czy serwer obsługuje wiele wystąpień. Miniserver musi być w stanie obsługiwać wiele wystąpień, co oznacza, że musi być możliwe jednoczesne uruchamianie wielu wystąpień serwera, po jednym dla każdego kontenera. W związku z tym należy przekazać **wartość true** dla tej flagi podczas uruchamiania miniserver.

W przypadku pisania miniserver, według definicji, będzie zawsze uruchamiany przez kontener. Nadal należy analizować wiersz polecenia w celu sprawdzenia opcji "przełącznikiem/Embedding". Brak tej opcji w wierszu polecenia oznacza, że użytkownik próbował uruchomić miniserver jako autonomiczną aplikację. W takim przypadku należy zarejestrować serwer przy użyciu bazy danych rejestracji systemu, a następnie wyświetlić okno komunikatu informujące użytkownika o konieczności uruchomienia miniserver z aplikacji kontenera.

## <a name="see-also"></a>Zobacz też

[OLE](../mfc/ole-in-mfc.md)<br/>
[Serwery](../mfc/servers.md)<br/>
[CWinApp:: RunAutomated](../mfc/reference/cwinapp-class.md#runautomated)<br/>
[CWinApp:: RunEmbedded](../mfc/reference/cwinapp-class.md#runembedded)<br/>
[Klasa element COleTemplateServer](../mfc/reference/coletemplateserver-class.md)

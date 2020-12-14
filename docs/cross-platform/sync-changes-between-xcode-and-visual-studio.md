---
description: 'Dowiedz się więcej o programie: Synchronizacja zmian między Xcode i Visual Studio'
title: Synchronizacja zmian między środowiskiem XCode a programem Visual Studio
ms.date: 10/17/2019
ms.assetid: c71a4d7c-120e-4559-a114-3a99c4b860a9
ms.openlocfilehash: 60ce41e41f5b6a2a9f877501eaef0d84306dde07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229057"
---
# <a name="sync-changes-between-xcode-and-visual-studio"></a>Synchronizacja zmian między środowiskiem XCode a programem Visual Studio

Tworzenie aplikacji mobilnych za pomocą składników C++ w programie Visual Studio obejmuje zdalne możliwości synchronizacji pracy między komputerem i komputerem Mac. Gdy komputery z programem Visual Studio i komputerów Mac są sparowane, nowe opcje są dostępne dla projektów aplikacji dla systemu iOS w programie Visual Studio, których można użyć do otwierania projektu w Xcode, przenoszenia kodu między Xcode i Visual Studio oraz czyszczenia tymczasowego katalogu projektu Xcode.

Aby można było użyć opcji maszyny zdalnej, projekt musi być projektem aplikacji dla systemu iOS, a program Visual Studio musi być sparowany z komputerem Mac. Aby uzyskać wymagania wstępne i instrukcje dotyczące parowania z komputerem Mac, zobacz [Instalowanie i Konfigurowanie narzędzi do kompilowania przy użyciu systemu iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md).

## <a name="the-remote-machine-menu"></a>Menu maszyny zdalnej

W **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt aplikacji systemu iOS, aby wyświetlić menu kontekstowe. Wybierz element **maszyny zdalnej** , aby wyświetlić dostępne opcje zdalne.

![Element menu maszyny zdalnej w Eksplorator rozwiązań](../cross-platform/media/cppmdd-u2-remotemachine-menu.jpg "Element menu maszyny zdalnej w Eksplorator rozwiązań")

Te polecenia umożliwiają otwieranie projektu w programie Xcode, przenoszenie lokalnych zmian lub całego projektu między programem Visual Studio i Xcode, a także czyszczenie plików tymczasowych na maszynie zdalnej.

## <a name="open-in-xcode"></a>Otwórz w Xcode

Aby otworzyć projekt w programie Xcode z poziomu programu Visual Studio, w podmenu **komputer zdalny** wybierz polecenie **Otwórz w Xcode** , aby otworzyć wybrany projekt na sparowanym komputerze zdalnym. `vcremote`Serwer służy do otwierania Xcode na komputerze Mac i przejdź do katalogu tymczasowego utworzonego na komputerze Mac, który zawiera kopię projektu. Program Visual Studio Wyświetla okno dialogowe, które pokazuje katalog tymczasowy używany dla projektu. Akcje wykonywane na maszynie zdalnej są również wyświetlane w oknie **danych wyjściowych** w programie Visual Studio. Aby je wyświetlić, w górnej części okna **danych wyjściowych** może być konieczne  wybranie opcji **Visual C++ maszyna zdalna** .

![W oknie dane wyjściowe są wyświetlane akcje maszyny zdalnej.](../cross-platform/media/cppmdd-u2-remotemachine-output.png "W oknie dane wyjściowe są wyświetlane akcje maszyny zdalnej")

Na komputerze Mac możesz użyć wszystkich narzędzi Xcode, aby edytować swój kod i zasoby, Scenorysy i akcje. W programie Visual Studio projekt aplikacji systemu iOS jest oznaczony adnotacją "otwarty w Xcode", aby wskazać, że zmiany mogą zostać wprowadzone na komputerze zdalnym. Po zakończeniu edycji można użyć ściągania z zdalnych lub przyrostowych ściągania z poleceń zdalnych, aby skopiować zmiany z powrotem do projektu programu Visual Studio.

## <a name="push-to-remote-and-incremental-push-to-remote"></a>Wypychanie do zdalnego i przyrostowego wypychania do zdalnego

Jeśli wprowadzono zmiany w projekcie aplikacji systemu iOS w programie Visual Studio, można użyć wypychania do zdalnego i przyrostowego wypychania do poleceń zdalnych, aby przenieść zmienione pliki projektu na sparowaną maszynę zdalną. Polecenie push do zdalnego kopiuje wszystkie pliki projektu na maszynę zdalną. Przyrostowe polecenie push do zdalnego kopiuje tylko zmienione pliki na maszynę zdalną. W przypadku dużych projektów z małymi zmianami polecenie przyrostowe może zaoszczędzić czas i przepustowość.

Aby skopiować pliki projektu na komputer Mac, w programie Visual Studio w **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt aplikacji systemu iOS, aby otworzyć menu kontekstowe. Wybierz pozycję **maszyna zdalna** i wybierz opcję **wypychania do zdalnego** lub **przyrostowego wypychania do zdalnego** , aby skopiować pliki projektu z programu Visual Studio na komputer Mac.

## <a name="pull-from-remote-and-incremental-pull-from-remote"></a>Ściąganie z zdalnego i przyrostowego ściągania z zdalnego

Po wprowadzeniu zmian w projekcie w programie Xcode Przenieś zmiany z powrotem do programu Visual Studio, aby zachować synchronizację projektów.

Aby skopiować pliki projektu z komputera Mac, w programie Visual Studio w **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt aplikacji systemu iOS, aby otworzyć menu kontekstowe. Wybierz pozycję **maszyna zdalna** , a następnie wybierz pozycję **ściąganie** lub **przyrostowe ściąganie z dysku zdalnego** , aby skopiować pliki projektu z komputera Mac do programu Visual Studio.

## <a name="clean-remote"></a>Wyczyść zdalne

Możesz użyć czystego polecenia zdalnego, aby usunąć pliki w tymczasowym katalogu projektu na komputerze zdalnym. Zawartość katalogu, w tym wszystkie pliki źródłowe lub produkty kompilacji, jest usuwana na komputerze Mac. Upewnij się, że zostały zsynchronizowane wszystkie zmiany, które chcesz wrócić do programu Visual Studio, używając ściągania z zdalnego lub przyrostowego ściągania z danych zdalnych przed użyciem polecenia Oczyść zdalnie.

Aby wyczyścić tymczasowy katalog projektu na komputerze zdalnym, w programie Visual Studio w **Eksplorator rozwiązań** kliknij prawym przyciskiem myszy projekt aplikacji systemu iOS, aby otworzyć menu kontekstowe. Wybierz pozycję **maszyna zdalna** i wybierz polecenie **Oczyść zdalnie** , aby usunąć pliki katalogu projektu z komputera Mac.

---
title: Konfigurowanie projektu systemu Linux MSBuild C++ w programie Visual Studio
ms.date: 10/16/2020
description: Skonfiguruj projekt systemu Linux oparty na programie MSBuild w programie Visual Studio, aby można było go skompilować.
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
ms.openlocfilehash: 451f34c257c210463ce11b11f27bc218d41b45c8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921818"
---
# <a name="configure-a-linux-msbuild-c-project-in-visual-studio"></a>Konfigurowanie projektu systemu Linux MSBuild C++ w programie Visual Studio

::: moniker range="msvc-140"

Obsługa systemu Linux jest dostępna w programie Visual Studio 2017 i nowszych.

::: moniker-end

W tym temacie opisano sposób konfigurowania projektu systemu Linux opartego na programie MSBuild, zgodnie z opisem w artykule [Tworzenie projektu programu Linux MSBuild C++ w programie Visual Studio](create-a-new-linux-project.md). W przypadku projektów CMake systemu Linux zobacz [Konfigurowanie projektu systemu Linux CMAKE](cmake-linux-project.md).

Istnieje możliwość skonfigurowania projektu systemu Linux, który będzie przeznaczony dla fizycznego komputera z systemem Linux, maszyny wirtualnej lub [podsystemu Windows for Linux](/windows/wsl/about) (WSL).

::: moniker range="msvc-160"

**Program Visual Studio 2019 w wersji 16,1** :

- W przypadku kierowania WSL można uniknąć operacji kopiowania wymaganych do kompilowania i pobierania IntelliSense, które są wymagane w przypadku kierowania zdalnego systemu Linux.

- Można określić oddzielne elementy docelowe systemu Linux na potrzeby kompilowania i debugowania.

::: moniker-end

## <a name="general-settings"></a>Ustawienia ogólne

Aby wyświetlić opcje konfiguracji, zaznacz menu **właściwości > projektu** lub kliknij prawym przyciskiem myszy projekt w **Eksplorator rozwiązań** i wybierz polecenie **Właściwości** z menu kontekstowego. Pojawią się ustawienia **Ogólne** .

![Konfiguracja ogólna](media/settings_general.png)

Domyślnie tworzony jest plik wykonywalny (. out). Aby utworzyć bibliotekę statyczną lub dynamiczną lub użyć istniejącego pliku reguł programu make, użyj ustawienia **typu konfiguracji** .

W przypadku kompilowania dla podsystemu Windows dla systemu Linux (WSL) WSL wersja 1 jest ograniczona do 64 procesów kompilacji równoległej. Jest to regulowane przez ustawienie **Maksymalna liczba równoległych zadań kompilacji** we **właściwościach konfiguracji > C/C++ > ogólne** .

Bez względu na używaną wersję programu WSL, jeśli zamierzasz używać więcej niż 64 procesów kompilacji równoległej, zalecamy skompilowanie z Ninja — który zwykle będzie szybszy i bardziej niezawodny. Aby skompilować przy użyciu ninja, użyj ustawienia **przyrostowej kompilacji** we **właściwościach konfiguracji > ogólne** .

Aby uzyskać więcej informacji na temat ustawień na stronach właściwości, zobacz temat [Informacje o stronie właściwości projektu systemu Linux](prop-pages-linux.md).

## <a name="remote-settings"></a>Ustawienia zdalne

Aby zmienić ustawienia związane ze zdalnym komputerem z systemem Linux, skonfiguruj ustawienia zdalne, które są wyświetlane w obszarze [Ogólne](prop-pages/general-linux.md).

- Aby określić zdalny docelowy komputer z systemem Linux, użyj wpisu **zdalnego komputera kompilacji** . Umożliwi to wybranie jednego z utworzonych wcześniej połączeń. Aby utworzyć nowy wpis, zobacz sekcję [łączenie się z komputerem zdalnym z systemem Linux](connect-to-your-remote-linux-computer.md) .

   ![Maszyna kompilacji](media/remote-build-machine-vs2019.png)

   ::: moniker range="msvc-160"

   **Visual Studio 2019 w wersji 16,7** : aby kierować podsystem Windows dla systemu Linux (WSL), Ustaw listę rozwijaną zestawu **narzędzi platformy** z systemem **Windows dla systemu Linux dla podsystemu Microsoft** . Inne opcje zdalne znikną, a ścieżka do domyślnej powłoki WSL pojawi się w ich miejscu:

   ![Maszyna kompilacji WSL](media/wsl-remote-vs2019.png)

   W przypadku równoległych instalacji WSL można tutaj określić inną ścieżkę. Więcej informacji o zarządzaniu wieloma dystrybucjemi znajduje się w temacie [Zarządzanie i Konfigurowanie podsystemu systemu Windows w systemie Linux](/windows/wsl/wsl-config#set-a-default-distribution).

   Na stronie Debugowanie **Właściwości konfiguracji** można określić inny cel dla debugowania > **Debugging** .

   ::: moniker-end

- **Katalog główny kompilacji zdalnej** określa lokalizację główną, w której projekt jest skompilowany na komputerze zdalnego systemu Linux. Wartość domyślna to **~/projects** , chyba że zostanie zmieniona.

- **Zdalny katalog projektu kompilacji** to miejsce, w którym ten konkretny projekt zostanie skompilowany na zdalnym komputerze z systemem Linux. Spowoduje to przekroczenie wartości **$ (RemoteRootDir)/$ (ProjectName)** , która zostanie rozszerzona do katalogu o nazwie po bieżącym projekcie, w katalogu głównym powyższego.

> [!NOTE]
> Aby zmienić domyślne kompilatory C i C++, lub konsolidator i archiwum używane do kompilowania projektu, należy użyć odpowiednich wpisów w sekcji **ogólnej > C/C++** i **konsolidatora > sekcja ogólna** . Możesz na przykład określić określoną wersję programu w ramach usługi lub Clang. Aby uzyskać więcej informacji, zobacz [Właściwości C/C++ (Linux c++)](prop-pages/c-cpp-linux.md) i [Właściwości konsolidatora (Linux c++)](prop-pages/linker-linux.md).

## <a name="copy-sources-remote-systems-only"></a>Kopiuj źródła (tylko systemy zdalne)

::: moniker range="msvc-160"

Ta sekcja nie ma zastosowania, gdy element docelowy jest WSL.

::: moniker-end

Podczas kompilowania w systemach zdalnych pliki źródłowe na komputerze deweloperskim są kopiowane do komputera z systemem Linux i kompilowane w tym miejscu. Domyślnie wszystkie źródła w projekcie programu Visual Studio są kopiowane do lokalizacji ustawionych w powyższych ustawieniach. Można jednak również dodać do listy dodatkowe źródła lub skopiować źródła, które są domyślnie wyłączone dla projektu reguł programu make.

- **Źródła do skopiowania** określają, które źródła są kopiowane do komputera zdalnego. Domyślnie **\@ (SourcesToCopyRemotely)** domyślne do wszystkich plików kodu źródłowego w projekcie, ale nie zawierają żadnych plików zasobów/zasobu, takich jak obrazy.

- **Źródła kopiowania** można włączać i wyłączać w celu włączenia i wyłączenia kopiowania plików źródłowych na komputer zdalny.

- **Dodatkowe źródła do skopiowania** umożliwiają dodanie dodatkowych plików źródłowych, które zostaną skopiowane do systemu zdalnego. Można określić listę rozdzielaną średnikami lub użyć składni **: =** , aby określić nazwę lokalną i zdalną do użycia:

`C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>Zdarzenia kompilacji

Ponieważ cała kompilacja odbywa się na komputerze zdalnym (lub WSL), kilka dodatkowych zdarzeń kompilacji zostało dodanych do sekcji zdarzenia kompilacji we właściwościach projektu. Są to **zdalne zdarzenie poprzedzające kompilację** , **zdalne zdarzenie poprzedzające konsolidację** i **zdalne zdarzenie po kompilacji** , które nastąpi na komputerze zdalnym przed lub po poszczególnych krokach procesu.

![Zdarzenia kompilacji](media/settings_buildevents.png)

## <a name="intellisense-for-headers-on-remote-systems"></a><a name="remote_intellisense"></a> Funkcja IntelliSense dla nagłówków w systemach zdalnych

Po dodaniu nowego połączenia w **Menedżerze połączeń** program Visual Studio automatycznie wykrywa katalogi dołączania dla kompilatora w systemie zdalnym. Program Visual Studio następnie Zips pliki i skopiuje je do katalogu na lokalnym komputerze z systemem Windows. Po wykonaniu tej operacji, za każdym razem, gdy korzystasz z tego połączenia w projekcie programu Visual Studio lub CMake, nagłówki w tych katalogach są używane do udostępniania technologii IntelliSense.

> [!NOTE]
> W programie Visual Studio 2019 w wersji 16,5 lub nowszej, zdalna kopia nagłówka została zoptymalizowana. Nagłówki są teraz kopiowane na żądanie podczas otwierania projektu systemu Linux lub konfigurowania CMake dla docelowego systemu Linux. Kopia odbywa się w tle dla każdego projektu, na podstawie określonych kompilatorów projektu. Aby uzyskać więcej informacji, zobacz [ulepszenia dokładności i wydajności funkcji IntelliSense systemu Linux](https://devblogs.microsoft.com/cppblog/improvements-to-accuracy-and-performance-of-linux-intellisense/).

Ta funkcja jest zależna od komputera z systemem Linux z zainstalowanym zip. Plik zip można zainstalować za pomocą tego polecenia apt-get:

```cmd
sudo apt install zip
```

Aby zarządzać pamięcią podręczną nagłówków, przejdź do **opcji narzędzia > opcje, Międzyplatformowe > Menedżer połączeń > zdalnych nagłówków programu IntelliSense** . Aby zaktualizować pamięć podręczną nagłówka po wprowadzeniu zmian na komputerze z systemem Linux, wybierz połączenie zdalne, a następnie wybierz pozycję **Aktualizuj** . Wybierz pozycję **Usuń** , aby usunąć nagłówki bez usuwania samego połączenia. Wybierz pozycję **Eksploruj** , aby otworzyć katalog lokalny w **Eksploratorze plików** . Traktuj ten folder jako tylko do odczytu. Aby pobrać nagłówki dla istniejącego połączenia, które zostało utworzone przed Visual Studio 2017 w wersji 15,3, wybierz połączenie, a następnie wybierz pozycję **Pobierz** .

::: moniker range="msvc-150"

![Zrzut ekranu przedstawiający okno dialogowe Opcje z międzyplatformowym Menedżerem połączeń > > wybrano zdalne nagłówki programu IntelliSense.](media/remote-header-intellisense.png)

::: moniker-end

::: moniker range="msvc-160"

![Zrzut ekranu przedstawiający okno dialogowe Opcje z wybranym wieloplatformowym Menedżerem połączeń >.](media/connection-manager-vs2019.png)

Możesz włączyć rejestrowanie, aby pomóc w rozwiązywaniu problemów:

![Rejestrowanie zdalne](media/remote-logging-vs2019.png)

::: moniker-end

## <a name="linux-target-locale"></a><a name="locale"></a> Ustawienia regionalne docelowego systemu Linux

Ustawienia języka programu Visual Studio nie są propagowane do celów systemu Linux, ponieważ program Visual Studio nie zarządza ani nie konfiguruje zainstalowanych pakietów. Komunikaty wyświetlane w oknie **danych wyjściowych** , takie jak błędy kompilacji, są wyświetlane przy użyciu języka i ustawień regionalnych docelowego systemu Linux. Należy skonfigurować cele systemu Linux dla żądanych ustawień regionalnych.

## <a name="see-also"></a>Zobacz także

[Ustawianie właściwości kompilatora i Build](../build/working-with-project-properties.md)<br/>
[Ogólne właściwości języka c++ (Linux C++)](prop-pages/general-linux.md)<br/>
[Katalogi VC + + (Linux C++)](prop-pages/directories-linux.md)<br/>
[Kopiuj właściwości projektu źródła (Linux C++)](prop-pages/copy-sources-project.md)<br/>
[Właściwości zdarzenia kompilacji (Linux C++)](prop-pages/build-events-linux.md)

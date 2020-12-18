---
title: Instalowanie vcpkg w systemach Windows, Linux i macOS
description: Dowiedz się, jak instalować i aktualizować vcpkg w systemach Windows, macOS i Linux.
ms.date: 12/17/2020
ms.topic: reference
ms.technology: cpp-ide
ms.openlocfilehash: aee9561dc94164c08e4d69ec49f60961392c1854
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/18/2020
ms.locfileid: "97684263"
---
# <a name="install-vcpkg-on-windows-linux-and-macos"></a>Instalowanie vcpkg w systemach Windows, Linux i macOS

Instalujesz vcpkg przez utworzenie lokalnego klonu (Copy) z repozytorium GitHub vcpkg.

## <a name="install-vcpkg"></a>Zainstaluj vcpkg

Wybierz platformę, aby uzyskać szczegółowe instrukcje:

### <a name="linux"></a>[Linux](#tab/linux)

Wymagania wstępne dotyczące systemu Linux:

- [Narzędzia](https://git-scm.com/downloads)
- g + + w wersji 6 lub nowszej

#### <a name="to-install-linux-development-tools"></a>Aby zainstalować narzędzia programistyczne dla systemu Linux

Różne dystrybucje systemu Linux mogą wymagać zainstalowania różnych pakietów. Postępuj zgodnie z tymi instrukcjami dotyczącymi Debian, Ubuntu, popOS i innych dystrybucji opartych na Debian:

1. W oknie powłoki Uruchom następujące polecenie:

   **`sudo apt-get update`**

1. Po zakończeniu aktualizacji uruchom następujące polecenie:

   **`sudo apt-get install build-essential tar curl zip unzip`**

Postępuj zgodnie z tymi instrukcjami w witrynie CentOS:

1. W oknie powłoki Uruchom następujące polecenie:

   **`sudo yum install centos-release-scl`**

1. Następnie zainstaluj i Włącz narzędzia programistyczne, uruchamiając następujące polecenia:

   **`sudo yum install devtoolset-7`**

   **`scl enable devtoolset-7 bash`**

W przypadku innych dystrybucji upewnij się, że instalujesz program g + + 6 lub nowszy.

#### <a name="to-copy-and-set-up-vcpkg-on-linux"></a>Aby skopiować i skonfigurować vcpkg w systemie Linux

1. W oknie powłoki Utwórz katalog dla sklonowanego wystąpienia vcpkg. Jeśli planujesz zainstalować biblioteki dla różnych elementów docelowych kompilacji, dobrym pomysłem jest uwzględnienie elementu docelowego w nazwie katalogu. Zalecamy używanie krótkich nazw ścieżek bez spacji, takich jak *`./x64`* lub *`./iot`* , ponieważ w przeciwnym razie może wystąpić problem z ścieżką dla niektórych systemów kompilacji portów. W oknie powłoki przejdź do katalogu, który właśnie został utworzony.

1. Klonuj repozytorium vcpkg z usługi GitHub: [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg) .

   > **`git clone https://github.com/microsoft/vcpkg`**

   To polecenie tworzy lokalną kopię repozytorium w *`vcpkg`* podkatalogu. Ta lokalizacja jest *katalogiem głównym* vcpkg dla tego klonu vcpkg.

1. Następnie przejdź do katalogu głównego vcpkg i uruchom polecenie programu inicjującego vcpkg:

   > **`./bootstrap-vcpkg.sh`**

   Program inicjujący konfiguruje vcpkg z lokalizacjami kompilator, Tools i bibliotekami standardowymi.

### <a name="macos"></a>[macOS](#tab/macos)

Wymagania wstępne dotyczące macOS:

- narzędzia deweloperskie macOS
- W przypadku macOS 10,14 lub jego poniżej wymagane są również następujące czynności:
  - Homebrew
  - g + + w wersji 6 lub nowszej

#### <a name="to-install-macos-developer-tools"></a>Aby zainstalować narzędzia deweloperskie macOS

1. W systemie macOS 10,15 Uruchom to polecenie w terminalu:

   **`xcode-select --install`**

   Następnie postępuj zgodnie z monitami wyświetlanymi w systemie Windows.

W systemie macOS 10,14 i wcześniejszych należy również zainstalować pozycję g + + z oprogramowania homebrew. Ta procedura jest konieczna tylko w przypadku korzystania z wersji macOS przed 10,15.

#### <a name="to-install-gcc-for-macos-before-1015"></a>Aby zainstalować program w zatoce dla programu macOS przed 10,15

1. Aby zainstalować oprogramowania homebrew, Otwórz program Terminal, a następnie uruchom następujące polecenie:

   **`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`**

1. Aby zainstalować aktualną wersję programu w zatoce, Uruchom to polecenie w terminalu:

   **`brew install gcc`**

#### <a name="to-copy-and-set-up-vcpkg-on-macos"></a>Aby skopiować i skonfigurować vcpkg na macOS

1. W obszarze Terminal Utwórz katalog dla sklonowanego wystąpienia vcpkg. Jeśli planujesz zainstalować biblioteki dla różnych elementów docelowych kompilacji, dobrym pomysłem jest uwzględnienie elementu docelowego w nazwie katalogu. Zalecamy używanie krótkich nazw ścieżek bez spacji, takich jak *`./macos`* lub *`./iot`* , ponieważ w przeciwnym razie może wystąpić problem z ścieżką dla niektórych systemów kompilacji portów. W terminalu przejdź do katalogu, który właśnie został utworzony.

1. Klonuj repozytorium vcpkg z usługi GitHub: [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg) .

   > **`git clone https://github.com/microsoft/vcpkg`**

   To polecenie tworzy lokalną kopię repozytorium w *`vcpkg`* podkatalogu. Ta lokalizacja jest *katalogiem głównym* vcpkg dla tego klonu vcpkg.

1. Następnie przejdź do katalogu głównego vcpkg i uruchom polecenie programu inicjującego vcpkg:

   > **`./bootstrap-vcpkg.sh`**

   Program inicjujący konfiguruje vcpkg z lokalizacjami kompilator, Tools i bibliotekami standardowymi.

### <a name="windows"></a>[Windows](#tab/windows)

Wymagania wstępne:

- System Windows 7 lub nowszy
- [Git dla systemu Windows](https://git-scm.com/downloads)
- [Visual Studio](https://visualstudio.microsoft.com/) 2015 Update 3 lub nowszy z pakietem języka angielskiego

#### <a name="to-copy-and-set-up-vcpkg-on-windows"></a>Aby skopiować i skonfigurować vcpkg w systemie Windows

1. W oknie wiersza polecenia Utwórz katalog dla sklonowanego wystąpienia vcpkg. Jeśli planujesz zainstalować biblioteki dla różnych elementów docelowych kompilacji, dobrym pomysłem jest uwzględnienie elementu docelowego w nazwie katalogu. Zalecamy używanie krótkich nazw ścieżek bez spacji, takich jak *`C:\src\win32\`* lub *`C:\dev\iot\`* , ponieważ w przeciwnym razie może wystąpić problem z ścieżką dla niektórych systemów kompilacji portów. W oknie polecenia przejdź do katalogu, który właśnie został utworzony.

1. Klonuj repozytorium vcpkg z usługi GitHub: [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg) .

   > **`git clone https://github.com/microsoft/vcpkg`**

   To polecenie tworzy lokalną kopię repozytorium w *`vcpkg`* podkatalogu. Ta lokalizacja jest *katalogiem głównym* vcpkg dla tego klonu vcpkg.

1. Po zakończeniu pobierania przejdź do *`vcpkg`* katalogu w oknie wiersza polecenia.

1. W katalogu głównym vcpkg Uruchom polecenie programu inicjującego vcpkg:

   > **`bootstrap-vcpkg.bat`**

   Program inicjujący konfiguruje vcpkg z lokalizacjami narzędzi, bibliotek i Windows SDK języka Microsoft C/C++.

---

Po skonfigurowaniu vcpkg można przystąpić do instalowania bibliotek. Aby uzyskać więcej informacji, zobacz [Zarządzanie bibliotekami za pomocą vcpkg](manage-libraries-with-vcpkg.md). vcpkg można także zintegrować z programem Visual Studio w systemie Windows lub z Visual Studio Code na dowolnej platformie. Aby uzyskać więcej informacji, zobacz [integrowanie vcpkg](integrate-vcpkg.md).

## <a name="update-vcpkg"></a>Aktualizacja vcpkg

Menedżer pakietów vcpkg jest regularnie aktualizowany w serwisie GitHub. Aby zaktualizować klon vcpkg do najnowszej wersji, w katalogu głównym vcpkg Uruchom polecenie **`git pull`** . To polecenie synchronizuje kopię vcpkg z wersją w serwisie GitHub. Po zakończeniu pobierania ponownie uruchom program inicjujący. Program inicjujący ponownie kompiluje programu vcpkg, ale pozostawia zainstalowane biblioteki na miejscu.

## <a name="uninstall-vcpkg"></a>Odinstaluj vcpkg

Aby odinstalować vcpkg, po prostu usuń *`vcpkg`* katalog. Usunięcie tego katalogu spowoduje odinstalowanie dystrybucji vcpkg oraz wszystkich bibliotek, które vcpkg zainstalowane.

Jednak jeśli wykonano **`vcpkg integrate install`** , należy wykonać, **`vcpkg integrate remove`** Aby upewnić się, że integracja jest czyszczona, zanim folder zostanie usunięty. Aby uzyskać więcej informacji, zobacz [integrowanie vcpkg](integrate-vcpkg.md).

## <a name="see-also"></a>Zobacz także

[vcpkg: Menedżer pakietów języka C++ dla systemów Windows, Linux i macOS](./vcpkg.md)\
[vcpkg w serwisie GitHub](https://github.com/Microsoft/vcpkg)\
[Integruj vcpkg](integrate-vcpkg.md)\
[Zarządzanie bibliotekami za pomocą vcpkg](manage-libraries-with-vcpkg.md)\
[vcpkg — dokumentacja wiersza polecenia](vcpkg-command-line-reference.md)\
[Szybki Start](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[Często zadawane pytania](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)

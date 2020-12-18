---
title: Integruj vcpkg z programem Visual Studio lub Visual Studio Code
description: Dowiedz się, jak zintegrować vcpkg z programem Visual Studio w systemie Windows lub Visual Studio Code w systemach macOS i Linux.
ms.date: 12/11/2020
ms.technology: cpp-ide
ms.openlocfilehash: b6f092313dde14b10a05d4cff0904adf5174b264
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/18/2020
ms.locfileid: "97684266"
---
# <a name="integrate-vcpkg-with-visual-studio-or-visual-studio-code"></a>Integruj vcpkg z programem Visual Studio lub Visual Studio Code

vcpkg to Międzyplatformowy Menedżer pakietów programu dla bibliotek C i C++. Można zintegrować ją z programem Visual Studio w systemie Windows lub Visual Studio Code w systemach Linux i macOS.

## <a name="integrate-with-visual-studio-on-windows"></a>Integracja z programem Visual Studio w systemie Windows

### <a name="integrate-per-user"></a>Integracja dla poszczególnych użytkowników

W katalogu głównym vcpkg Uruchom polecenie, **`vcpkg integrate install`** Aby skonfigurować program Visual Studio do lokalizowania wszystkich plików nagłówkowych vcpkg i danych binarnych dla poszczególnych użytkowników. Nie ma potrzeby edytowania ścieżek katalogów VC + + w programie Visual Studio. Jeśli masz wiele klonów vcpkg, klon uruchamiający to polecenie otrzymuje nową lokalizację domyślną.

Teraz można dołączać nagłówki, wpisując nazwę folderu lub nagłówka, a także ułatwiają automatyczne uzupełnianie. Nie są wymagane żadne dodatkowe kroki do łączenia się z bibliotekami lub dodawania odwołań do projektu. Na poniższej ilustracji pokazano, jak program Visual Studio odnajduje *`azure-storage-cpp`* nagłówki. vcpkg umieszcza swoje nagłówki w *`/installed`* podfolderze podzielonym przez platformę docelową. Na poniższym diagramie przedstawiono listę plików dołączanych w *`/was`* podfolderze biblioteki:

![Okienko wyskakujące autouzupełniania funkcji IntelliSense w edytorze programu Visual Studio](media/vcpkg-intellisense.png "vcpkg i IntelliSense")

### <a name="integrate-per-project"></a>Integracja na projekt

Jeśli potrzebujesz użyć określonej wersji biblioteki, która różni się od wersji w aktywnym wystąpieniu usługi vcpkg, wykonaj następujące kroki:

1. Utwórz nowy klon vcpkg. Aby uzyskać więcej informacji, zobacz [Install vcpkg](install-vcpkg.md).

1. Przejdź do nowego katalogu głównego vcpkg.

1. Zmodyfikuj Portfile biblioteki, aby uzyskać wymaganą wersję.

1. Uruchom **`vcpkg install <library>`** . Aby uzyskać więcej informacji, zobacz [Zarządzanie bibliotekami za pomocą vcpkg](manage-libraries-with-vcpkg.md).

1. Użyj, **`vcpkg integrate project`** Aby utworzyć pakiet NuGet, który odwołuje się do tej biblioteki na podstawie projektu.

## <a name="integrate-with-visual-studio-code-on-linux-or-macos"></a>Integracja z usługą Visual Studio Code w systemie Linux lub macOS

W oknie powłoki lub terminalu zmień katalogi na katalog główny vcpkg. Następnie uruchom polecenie **`./vcpkg integrate install`** , aby skonfigurować Visual Studio Code w systemie Linux lub macOS. To polecenie ustawia lokalizację narzędzi i bibliotek vcpkg oraz włącza funkcję IntelliSense w plikach źródłowych.

## <a name="remove-vcpkg-integration"></a>Usuń integrację vcpkg

Jeśli została użyta **`integrate`** opcja, należy usunąć integrację przed usunięciem wystąpienia vcpkg. Aby usunąć i oczyścić integrację, należy zmienić katalogi na katalog główny vcpkg. W systemie Windows uruchom polecenie, **`vcpkg integrate remove`** Aby upewnić się, że integracja zostanie wyczyszczona. W systemie Linux lub macOS Uruchom **`./vcpkg integrate remove`** polecenie.

## <a name="see-also"></a>Zobacz także

[vcpkg: Menedżer pakietów języka C++ dla systemów Windows, Linux i macOS](./vcpkg.md)\
[vcpkg w serwisie GitHub](https://github.com/Microsoft/vcpkg)\
[Zainstaluj vcpkg](install-vcpkg.md)\
[Zarządzanie bibliotekami za pomocą vcpkg](manage-libraries-with-vcpkg.md)\
[vcpkg — dokumentacja wiersza polecenia](vcpkg-command-line-reference.md)\
[Szybki Start](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[Często zadawane pytania](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)

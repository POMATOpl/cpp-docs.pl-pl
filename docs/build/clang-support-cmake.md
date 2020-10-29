---
title: Obsługa Clang/LLVM w projektach programu Visual Studio CMake
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ CMake projects
ms.openlocfilehash: e23da02a0c3af624ddb30cec8dbb5afda55660c9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919582"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Obsługa Clang/LLVM w projektach programu Visual Studio CMake

::: moniker range="<=msvc-150"

Obsługa Clang jest dostępna w programie Visual Studio 2019.

::: moniker-end

::: moniker range="msvc-160"

Możesz użyć programu Visual Studio z Clang do edytowania i debugowania projektów C++ CMake przeznaczonych dla systemu Windows lub Linux.

**System Windows** : program Visual Studio 2019 w wersji 16,1 obejmuje obsługę edytowania, kompilowania i debugowania z CLANG/LLVM w projektach cmake, które są przeznaczone dla systemu Windows.

**Linux** : for Linux CMAKE — nie jest wymagane żadne specjalne wsparcie dla programu Visual Studio. Możesz zainstalować Clang za pomocą Menedżera pakietów dystrybucji i dodać odpowiednie polecenia w pliku CMakeLists.txt.

## <a name="install"></a>Zainstaluj

Aby zapewnić najlepszą obsługę środowiska IDE w programie Visual Studio, zalecamy korzystanie z najnowszych narzędzi kompilatora Clang dla systemu Windows. Jeśli jeszcze tego nie zrobiono, możesz je zainstalować, otwierając Instalator programu Visual Studio i wybierając **kompilator C++ Clang dla systemu Windows** w obszarze **Programowanie aplikacji klasycznych za pomocą** opcjonalnych składników języka c++. W przypadku korzystania z niestandardowej instalacji Clang należy sprawdzić składnik **C++ Clang-CL for v142 Build Tools** .

![Instalacja składnika Clang](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>Utwórz nową konfigurację

Aby dodać nową konfigurację Clang do projektu CMake:

1. Kliknij prawym przyciskiem myszy na CMakeLists.txt w **Eksplorator rozwiązań** i wybierz pozycję **Ustawienia CMAKE dla projektu** .

1. W obszarze **konfiguracje** naciśnij przycisk **Dodaj konfigurację** :

   ![Dodawanie konfiguracji](media/cmake-add-config-icon.png)

1. Wybierz żądaną konfigurację Clang (należy zauważyć, że dla systemów Windows i Linux są dostarczane oddzielne konfiguracje Clang), a następnie naciśnij **pozycję Wybierz** :

   ![Konfiguracja CMake Clang](media/cmake-clang-configuration.png)

1. Aby wprowadzić modyfikacje w tej konfiguracji, użyj **edytora ustawień CMAKE** . Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień kompilacji CMAKE w programie Visual Studio](customize-cmake-settings.md).

## <a name="modify-an-existing-configuration-to-use-clang"></a>Zmodyfikuj istniejącą konfigurację, aby użyć Clang

Aby zmodyfikować istniejącą konfigurację, aby użyć Clang, wykonaj następujące kroki:

1. Kliknij prawym przyciskiem myszy na CMakeLists.txt w **Eksplorator rozwiązań** i wybierz pozycję **Ustawienia CMAKE dla projektu** .

1. W obszarze **Ogólne** wybierz listę rozwijaną zestaw **narzędzi** i wybierz żądany zestaw narzędzi Clang:

   ![Zrzut ekranu przedstawiający ogólne okno dialogowe z informacją o tym, że zestaw narzędzi jest wybrany i Clang CL x 86.](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Niestandardowe lokalizacje Clang

Domyślnie program Visual Studio szuka Clang w dwóch miejscach:

- Systemy Zainstalowana wewnętrznie kopia Clang/LLVM, która jest dostarczana z instalatorem programu Visual Studio.
- (Systemy Windows i Linux) Zmienna środowiskowa PATH.

Możesz określić inną lokalizację, ustawiając zmienne **CMAKE_C_COMPILER** i **CMAKE_CXX_COMPILER** CMAKE w **ustawieniach CMAKE** :

![Zrzut ekranu przedstawiający okno dialogowe Ustawienia języka C z wyróżnionym kompilatorem C + X x.](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Tryby zgodności Clang

W przypadku konfiguracji systemu Windows CMake domyślnie wywołuje Clang w trybie [Clang-CL](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) i łączy się z implementacją firmy Microsoft w warstwie Standardowa. Domyślnie **clang-cl.exe** znajduje się w temacie `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin` .

Te wartości można modyfikować w **ustawieniach CMAKE** w obszarze **zmienne CMAKE i pamięć podręczna** . Kliknij przycisk **Pokaż zaawansowane zmienne** . Przewiń w dół, aby znaleźć **CMAKE_CXX_COMPILER** , a następnie kliknij przycisk **Przeglądaj**  , aby określić inną ścieżkę kompilatora.

## <a name="edit-build-and-debug"></a>Edytuj, Kompiluj i Debuguj

Po skonfigurowaniu konfiguracji Clang można skompilować i debugować projekt. Program Visual Studio wykrywa, że używasz kompilatora Clang i udostępnia funkcję IntelliSense, wyróżnianie, nawigację i inne funkcje edycji. Błędy i ostrzeżenia są wyświetlane w **okno dane wyjściowe** .

Podczas debugowania można użyć punktów przerwania, pamięci i wizualizacji danych oraz większości innych funkcji debugowania. Niektóre funkcje zależne od kompilatora, takie jak Edit i Continue, nie są dostępne do konfiguracji Clang.

![Debugowanie CMake Clang](media/clang-debug-visualize.png)

::: moniker-end

---
description: 'Dowiedz się więcej o: wprowadzenie do programu Microsoft C++ dla użytkowników systemu UNIX'
title: Wprowadzenie do języka Microsoft C++ dla użytkowników systemu UNIX
ms.date: 10/23/2019
helpviewer_keywords:
- UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
ms.openlocfilehash: 1047ba4e07803bfd6863a0b7da5d0e8473938586
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159833"
---
# <a name="introduction-to-microsoft-c-for-unix-users"></a>Wprowadzenie do języka Microsoft C++ dla użytkowników systemu UNIX

Ten temat zawiera informacje dla użytkowników wszystkich wersji systemu UNIX, które są nowe dla programu Visual Studio i chcą wydajnie pracować z C++ przy użyciu wiersza polecenia lub programu Visual Studio. Do systemu Windows można użyć programu Visual Studio z kompilatorem języka Microsoft C++. Możesz również użyć środowiska IDE programu Visual Studio z programem w zatoce lub Clang w środowiskach UNIX, takich jak maszyny wirtualne z systemem Linux, MinGW-W64 i podsystem Windows dla systemu Linux. Aby można było używać języka C++ w programie Visual Studio, należy zainstalować **Programowanie aplikacji klasycznych w języku c++** . Otwórz Instalator programu Visual Studio, aby zainstalować obciążenie lub dodać lub usunąć opcjonalne składniki. Zainstaluj także programowanie dla systemu **Linux przy użyciu obciążenia języka C++** , jeśli będziesz ukierunkowanym na zdalny komputer z systemem Linux. W przypadku tworzenia aplikacji dla systemu Android lub iOS należy zainstalować **Programowanie aplikacji mobilnych przy użyciu obciążenia języka C++** .

## <a name="getting-started-on-the-command-line"></a>Wprowadzenie do wiersza polecenia

Kompilator języka Microsoft C++ można użyć z wiersza polecenia w podobny sposób, jak w przypadku korzystania ze środowiska wiersza polecenia systemu UNIX. Kompilowanie z poziomu wiersza polecenia przy użyciu wiersza polecenia kompilator C i C++ (CL.EXE), konsolidator (LINK.EXE) i innych narzędzi, w tym NMAKE.EXE, wersja firmy Microsoft dla systemu UNIX.

W systemie UNIX polecenia są instalowane w folderze wspólnym, takim jak/usr/bin. W programie Visual Studio narzędzia wiersza polecenia są instalowane w katalogu instalacyjnym programu Visual Studio w podkatalogu VC\bin i jego podkatalogach. W przeciwieństwie do systemu UNIX te narzędzia nie są dostępne w zwykłym oknie wiersza polecenia. Aby użyć narzędzi wiersza polecenia, należy użyć specjalnego wiersza polecenia dewelopera, który konfiguruje ścieżkę i inne zmienne środowiskowe, które są niezbędne do kompilowania programów C++. Aby uzyskać więcej informacji, zobacz Kompilowanie [kodu C/C++ w wierszu polecenia](../build/building-on-the-command-line.md) i [instruktażu: kompilowanie natywnego programu C++ w wierszu polecenia](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).

## <a name="debugging-your-code"></a>Debugowanie kodu

Możesz użyć debugera programu Visual Studio dla projektów Microsoft C++ z wiersza polecenia lub z poziomu środowiska IDE. Kompiluj przy użyciu przełącznika [/Z7,/Zi,/ZI (Debug Information Format),](../build/reference/z7-zi-zi-debug-information-format.md) aby umożliwić krokowe przechodzenie przez źródła. Aby uzyskać więcej informacji, zobacz [Debugowanie kodu natywnego](/visualstudio/debugger/debugging-native-code) i [Używanie środowiska IDE programu Visual Studio do tworzenia aplikacji klasycznych w języku C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

W przypadku programów skompilowanych za pomocą usługi w zatoce lub Clang program Visual Studio wywołuje GDB, LLDB lub dowolny niestandardowy debuger, który określisz.

## <a name="visual-studio-project-system"></a>System projektu programu Visual Studio

System projektu programu Visual Studio nosi nazwę MSBuild. Używa plików projektu w formacie XML; Pliki projektu C++ mają rozszerzenie. vcxproj. Aplikacja, która składa się z wielu bibliotek i plików wykonywalnych, z których każdy może być zbudowany przy użyciu innego zestawu opcji kompilatora lub nawet w innym języku, są przechowywane w wielu projektach, które są częścią jednego *rozwiązania*. Rozwiązanie jest abstrakcją kontenera, aby zgrupować wiele projektów jednocześnie. Informacje o rozwiązaniach są przechowywane w pliku rozwiązania z rozszerzeniem sln. Aby uzyskać więcej informacji, zobacz [rozwiązania i projekty w programie Visual Studio](/visualstudio/ide/solutions-and-projects-in-visual-studio) oraz [Korzystanie z programu Visual Studio IDE do tworzenia aplikacji klasycznych](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)w języku C++. Z menu głównego wybierz kolejno pozycje **plik**  >  **Nowy**  >  **projekt** , aby wyświetlić dostępne szablony projektów programu Visual Studio.

Począwszy od programu Visual Studio 2017, dodano obsługę projektów CMake, a także opcje używania kompilatora języka Microsoft C++ z dowolnym dowolnym systemem kompilacji lub z luźnym folderem plików źródłowych i bez plików projektu. Aby uzyskać więcej informacji, zobacz [CMAKE projects in Visual Studio](../build/cmake-projects-in-visual-studio.md) i [Otwórz projekty folderu w programie Visual Studio](../build/open-folder-projects-cpp.md).

## <a name="microsoft-specific-modifiers"></a>Modyfikatory specyficzne dla firmy Microsoft

Kompilator języka Microsoft C++ implementuje kilka rozszerzeń standardowego języka programowania C++, aby obsługiwać Programowanie dla systemów operacyjnych Windows. Rozszerzenia te służą do określania atrybutów klasy magazynu, konwencji wywoływania funkcji i adresowania na podstawie innych elementów. Aby uzyskać pełną listę wszystkich obsługiwanych rozszerzeń języka C++, zobacz [Modyfikatory specyficzne dla firmy Microsoft](../cpp/microsoft-specific-modifiers.md).

Wszystkie rozszerzenia specyficzne dla firmy Microsoft można wyłączyć do języka C++ przy użyciu `/Za` opcji kompilatora. Ta opcja jest zalecana, jeśli chcesz napisać kod do uruchomienia na wielu platformach. Aby uzyskać więcej informacji na temat `/Za` opcji kompilatora, zobacz [/za,/ze (Wyłącz rozszerzenia językowe)](../build/reference/za-ze-disable-language-extensions.md). Aby uzyskać więcej informacji na temat zgodności kompilatora języka C++, zobacz [tabela zgodność języka Microsoft C++](../overview/visual-cpp-language-conformance.md) i [zachowanie niestandardowe](../cpp/nonstandard-behavior.md).

## <a name="precompiled-headers"></a>Wstępnie skompilowane nagłówki

Kompilatory Microsoft C i C++ zapewniają opcje wstępnego kompilowania kodu C lub C++, w tym kodu wbudowanego. Korzystając z tej funkcji wydajności, można skompilować stabilną treść kodu, przechowywać skompilowany stan kodu w pliku i, podczas kolejnych kompilacji, połączyć wstępnie skompilowany kod z kodem, który jest nadal w fazie projektowania. Każda kolejna kompilacja jest szybsza, ponieważ stabilny kod nie musi być ponownie kompilowany.

Domyślnie cały skompilowany kod jest określony w plikach *PCH. h* i *PCH. cpp* (*stdafx. h* i *stdafx. cpp* w programie Visual Studio 2017 i wcześniejszych). Aby uzyskać więcej informacji na temat prekompilowanych nagłówków, zobacz [Tworzenie prekompilowanych plików nagłówkowych](../build/creating-precompiled-header-files.md).

## <a name="related-sections"></a>Sekcje pokrewne

Aby uzyskać więcej informacji, zobacz [Uruchamianie programów systemu Linux w systemie Windows](../porting/porting-from-unix-to-win32.md).

## <a name="see-also"></a>Zobacz też

[Projekty i systemy kompilacji](../build/projects-and-build-systems-cpp.md)

---
description: 'Dowiedz się więcej o programie: Programowanie aplikacji mobilnych dla wielu platform w języku C++'
title: Opracowywanie aplikacji mobilnych na wiele platform w języku C++
ms.date: 11/14/2019
ms.assetid: 0bb872d6-981b-4c96-9143-fcec5336bf0d
ms.openlocfilehash: 98e7124ca8a687a2308a97eb11da80fc0c69483a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213237"
---
# <a name="cross-platform-mobile-development-with-c"></a>Opracowywanie aplikacji mobilnych na wiele platform w języku C++

Możesz tworzyć natywne aplikacje C++ dla urządzeń z systemami iOS, Android i Windows za pomocą międzyplatformowych narzędzi dostępnych w programie Visual Studio. **Programowanie aplikacji mobilnych za pomocą języka C++** to obciążenie dostępne w Instalatorze programu Visual Studio. Instaluje zestawy SDK i narzędzia potrzebne do tworzenia międzyplatformowych bibliotek udostępnionych i aplikacji natywnych. Po zainstalowaniu programu można użyć języka C++ do tworzenia kodu działającego na urządzeniach z systemem iOS lub Android oraz na platformach, w systemie Windows, sklepie Windows i konsoli Xbox.

Pisanie kodu dla wielu platform jest często frustrujące. Podstawowe języki deweloperskie i narzędzia dla systemów iOS, Android i Windows różnią się w zależności od platformy. Jednak wszystkie platformy obsługują pisanie kodu w języku C++. Jest to typowy mianownik, który umożliwia ponowne użycie kodu podstawowego na różnych platformach. Kod natywny zapisany w języku C++ może być jednocześnie bardziej wydajny i odporny na odtwarzanie przez odtwarzanie. Ponowne użycie kodu może zaoszczędzić czas i nakład pracy podczas tworzenia aplikacji dla wielu platform.

Programowanie przy użyciu języka C++ dla wieloplatformowego opracowywania aplikacji mobilnych ma kilka zalet:

- **Łatwa instalacja.** Instalator programu Visual Studio uzyskuje i instaluje wymagane narzędzia innych firm i zestawy SDK potrzebne do kompilowania aplikacji lub bibliotek dla systemów Android i iOS. Konfiguracja i konfiguracja są proste i najczęściej automatyczne.

- **Zaawansowane i znane środowisko kompilacji.** Łatwo twórz udostępnione rozwiązania i projekty dla wielu platform za pomocą szablonów programu Visual Studio. Zarządzanie właściwościami wszystkich projektów przy użyciu jednego wspólnego interfejsu. Edytuj cały kod w edytorze programu Visual Studio i Skorzystaj z wbudowanej wieloplatformowej funkcji IntelliSense do uzupełniania kodu i wyróżniania błędów.

- **Ujednolicone środowisko debugowania.** Korzystaj z światowej klasy narzędzi do debugowania w programie Visual Studio, aby oglądać i przełączać kod języka C++ na wszystkich platformach: urządzenia z systemem Android i emulatory, symulatory systemu iOS i urządzenia oraz emulatory systemu Windows lub Windows.

## <a name="get-the-tools"></a>Pobierz narzędzia

Programowanie aplikacji mobilnych za pomocą języka C++ to z instalowalnym programem Visual Studio. Aby uzyskać wymagania wstępne i instrukcje dotyczące instalacji, zobacz [Instalowanie aplikacji mobilnych dla wielu platform w języku C++](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md). Do utworzenia kodu dla systemu iOS potrzebny jest również komputer Mac i konto dewelopera systemu Apple iOS. Aby uzyskać więcej informacji, zobacz [Instalowanie i Konfigurowanie narzędzi do kompilowania przy użyciu systemu iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md).

## <a name="come-up-to-speed"></a>Szybsze

Jeśli korzystasz z programowania w systemie Android lub iOS, mamy doskonały materiał na temat rozpoczynania pracy. Program Visual Studio jest środowiskiem deweloperskim i obsługującym. Aby dowiedzieć się, jak z niej korzystać, wypróbuj [deweloperów systemu Android](/previous-versions/windows/apps/dn275875\(v=win.10\)) lub Rozpocznij [pracę dla deweloperów systemu iOS](/previous-versions/windows/apps/jj657966\(v=win.10\)). Te artykuły zawierają wprowadzenie do programu Visual Studio i koncepcje potrzebne do tworzenia aplikacji dla wielu platform dla systemu Windows i sklepu Windows. Aby rozpocząć tworzenie pierwszej aplikacji dla wielu platform dla systemów iOS i Android, zobacz [Tworzenie aplikacji OpenGL ES w systemach Android i iOS](../cross-platform/build-an-opengl-es-application-on-android-and-ios.md).

Tworzenie aplikacji mobilnych za pomocą języka C++ obejmuje kilka szablonów, które ułatwiają rozpoczęcie pracy z aplikacjami:

- Aplikacja Native-Activity (Android)

  Tworzy kompletną aplikację języka C++ OpenGL jako projekt natywnych działań systemu Android.

- Aplikacja OpenGLs (Android, iOS)

  Tworzy rozwiązanie z zestawem projektów do kompilowania zarówno aplikacji natywnej aktywności systemu Android, jak i aplikacji systemu iOS. Aplikacje te używają bibliotek specyficznych dla platformy utworzonych przy użyciu wspólnego kodu języka C++ OpenGL ES do rysowania tego samego obracającego się modułu w każdej aplikacji.

- Biblioteka udostępniona (Android, iOS)

  Tworzy rozwiązanie z projektami, aby utworzyć plik biblioteki dynamicznej systemu Android (. so) i plik statycznej biblioteki systemu iOS (. a) przy użyciu wspólnego kodu C++ w projekcie udostępnionym.

- Aplikacja podstawowa (Android, ANT)

  Tworzy projekt aplikacji "Hello, World" dla systemu Android, który używa tylko kodu źródłowego Java i systemu kompilacji ANT.

- Aplikacja podstawowa (Android, Gradle)

  Tworzy projekt aplikacji "Hello, World" dla systemu Android, który używa tylko kodu źródłowego Java i systemu kompilacji Gradle.

- Biblioteka podstawowa (Android, ANT)

  Tworzy projekt biblioteki dla systemu Android "Hello, World", który używa tylko kodu źródłowego Java i systemu kompilacji ANT.

- Biblioteka podstawowa (Android, Gradle)

  Tworzy projekt biblioteki dla systemu Android "Hello, World", który używa tylko kodu źródłowego Java i systemu kompilacji Gradle.

- Dynamiczna biblioteka udostępniona (Android)

  Tworzy plik biblioteki dynamicznej systemu Android (. so) przy użyciu kodu C++.

- Aplikacja OpenGLs 2 (iOS)

  Tworzy rozwiązanie z zestawem projektów do kompilowania aplikacji dla systemu iOS w technologii OpenGL ES 2. Aplikacja używa biblioteki języka C++ z kodem OpenGL ES do rysowania obracającego się modułu w aplikacji systemu iOS. Ta aplikacja może być dobrym punktem wyjścia do wyświetlania sposobu importowania bibliotek C++ do aplikacji systemu iOS.

- Biblioteka statyczna (Android)

  Tworzy projekt do kompilowania biblioteki statycznej dla systemu Android. Można połączyć tylko jedną bibliotekę dynamiczną w aplikacji systemu Android, ale można połączyć dowolną liczbę bibliotek statycznych.

- Biblioteka statyczna (iOS)

  Tworzy projekt do kompilowania biblioteki statycznej dla systemu iOS.

- Projekt pliku reguł programu make (Android)

  Tworzy otokę projektu dla własnych projektów programu make dla systemu Android.

## <a name="try-out-sample-code"></a>Wypróbuj przykładowy kod

Pobierz przykłady pokazujące sposób tworzenia udostępnionych bibliotek kodu, których można używać w aplikacjach dla systemów Windows, Android i iOS. I Zobacz przykłady tworzenia kompletnych natywnych aplikacji aktywności dla systemu Android. Aby rozpocząć, zobacz [przykłady tworzenia aplikacji mobilnych dla wielu platform](../cross-platform/cross-platform-mobile-development-examples.md).

## <a name="see-also"></a>Zobacz też

[Instalowanie aplikacji mobilnych dla wielu platform przy użyciu języka C++](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)\
[Instalowanie i Konfigurowanie narzędzi do kompilowania przy użyciu systemu iOS](../cross-platform/install-and-configure-tools-to-build-using-ios.md)\
[Tworzenie aplikacji dla systemu Android Native Activity](../cross-platform/create-an-android-native-activity-app.md)\
[Tworzenie aplikacji OpenGL ES w systemach Android i iOS](../cross-platform/build-an-opengl-es-application-on-android-and-ios.md)\
[Przykłady programowania międzyplatformowych aplikacji mobilnych](../cross-platform/cross-platform-mobile-development-examples.md)

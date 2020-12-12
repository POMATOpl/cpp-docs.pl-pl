---
description: 'Dowiedz się więcej o: wyborze metody wdrażania'
title: Wybieranie metody wdrażania
ms.date: 03/14/2019
helpviewer_keywords:
- redistributing DLLs
- manifests [C++]
- DLLs [C++], redistributing
- side-by-side assemblies [C++]
- dynamic linking [C++]
- application deployment [C++], methods
- deploying applications [C++], methods
- static linking [C++]
- libraries [C++], application deployment issues
ms.assetid: fd8eb956-f4a0-4ffb-b401-328c73e66986
ms.openlocfilehash: 9b1ae942ff189bf9073059a55a195860bd3efc26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327177"
---
# <a name="choosing-a-deployment-method"></a>Wybieranie metody wdrażania

Jeśli aplikacja Visual C++ nie jest samodzielna i można ją wdrożyć za pomocą polecenia copy, zalecamy użycie Instalator Windows do wdrożenia. Instalator Windows obsługuje instalację, naprawę oraz dezinstalację, a także obsługuje atomowe aktualizowanie plików aplikacji, zależności i wpisów rejestru.

> [!NOTE]
> Chociaż wdrożenie [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) dla Visual C++ aplikacji natywnych jest możliwe w programie Visual Studio, wymaga to dodatkowych kroków. Aby uzyskać więcej informacji, zobacz [wdrażanie ClickOnce dla aplikacji Visual C++](clickonce-deployment-for-visual-cpp-applications.md).

## <a name="visual-c-libraries-are-shared-dlls"></a>Biblioteki Visual C++ to współdzielone biblioteki DLL

Ponieważ biblioteki Visual C++ są instalowane w katalogu %windir%\system32\ przez instalator Visual Studio, podczas tworzenia aplikacji Visual C++, która od nich zależy, będzie ona działała zgodnie z oczekiwaniami. Aby wdrożyć aplikację na komputerach, które nie mają Visual Studio, zalecamy, aby się upewnić, że odpowiednie biblioteki są instalowane wraz z aplikacją.

## <a name="redistributing-visual-c-libraries"></a>Redystrybucja bibliotek Visual C++

We wdrożeniach można redystrybuować dowolną wersję biblioteki Visual C++, której licencja na to pozwala. Poniżej przedstawiono trzy sposoby ich wdrożenia:

- Wdrażanie centralne przy użyciu pakietów redystrybucyjnych, które instalują Visual C++ biblioteki jako udostępnione biblioteki DLL w%windir%\system32 \\ . (Instalacja w tym folderze wymaga uprawnień administratora). Można utworzyć skrypt lub program instalacyjny, który uruchamia pakiet redystrybucyjny przed zainstalowaniem aplikacji na komputerze docelowym. Pakiety redystrybucyjne są dostępne dla platform x86, x64 i ARM (VCRedist_x86.exe, VCRedist_x64.exe lub VCRedist_arm.exe). Program Visual Studio zawiera te pakiety w% ProgramFiles (x86)% \ Microsoft Visual Studio `version` \VC\Redist \\ `locale ID` \\ . Można je również pobrać z [Centrum pobierania Microsoft](https://www.microsoft.com/download). (Użyj pola wyszukiwania w centrum pobierania, aby wyszukać "Visual C++ pakiet redystrybucyjny, *wersja i aktualizacja programu Visual Studio*, który jest zgodny z aplikacją. Jeśli na przykład do kompilowania aplikacji użyto programu Visual Studio 2015 Update 3, wyszukaj ciąg "Visual C++ pakiet redystrybucyjny 2015 Update 3".) Aby uzyskać informacje o sposobach korzystania z pakietu redystrybucyjnego, zobacz [Przewodnik: wdrażanie aplikacji Visual C++ przy użyciu pakietu redystrybucyjnego Visual C++](deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).

- Centralne wdrażanie za pomocą modułów scalania, z których każdy instaluje określoną bibliotekę Visual C++ jako udostępnioną bibliotekę DLL w%windir%\system32 \\ . (Instalacja w tym folderze wymaga uprawnień administratora). Moduły scalania stają się częścią pliku Instalatora MSI dla aplikacji. Visual C++ Redystrybucyjne moduły scalania są zawarte w programie Visual Studio, w folderze \Program Files (x86) \Common Files\Merge modules \\ . Aby uzyskać więcej informacji, zobacz [Redystrybucja przy użyciu modułów scalania](redistributing-components-by-using-merge-modules.md).

- Lokalne wdrożenie, w którym można skopiować konkretne Visual C++ biblioteki DLL z instalacji programu Visual Studio — zwykle w \Program Files (x86) \Microsoft Visual Studio `version` \VC\Redist \\ `platform` \\ `library` \ — i zainstalować je na komputerach docelowych w tym samym folderze, w którym znajduje się plik wykonywalny aplikacji. Możesz użyć tej metody wdrożenia, aby umożliwić instalację przez użytkowników, którzy nie mają praw administratora, lub dla aplikacji, które mogą być uruchamiane z udziału sieciowego.

Jeśli wdrożenie używa redystrybucyjnych modułów scalania, a instalacja jest uruchamiana przez użytkownika, który nie ma uprawnień administracyjnych, Visual C++ dll nie są zainstalowane i aplikacja nie zostanie uruchomiona. Ponadto programy instalacyjne aplikacji, skompilowane z wykorzystaniem modułów scalania, które zezwalają na instalację dla poszczególnych użytkowników, instalują biblioteki we współdzielonej lokalizacji, która wpływa na wszystkich użytkowników systemu. Wdrożenie lokalne służy do instalowania wymaganych Visual C++ bibliotek DLL w katalogu aplikacji określonego użytkownika bez wywierania wpływu na innych użytkowników ani nie wymaga uprawnień administratora. Ponieważ może to powodować problemy z usługą, nie zalecamy lokalnego wdrażania Visual C++ redystrybucyjnych bibliotek DLL.

Nieprawidłowe wdrożenie bibliotek Visual C++ może spowodować błędy w czasie wykonywania aplikacji, która od nich zależy. Gdy system operacyjny ładuje aplikację, używa kolejności wyszukiwania opisanej w [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw).

## <a name="dynamic-linking-is-better-than-static-linking"></a>Łączenie dynamiczne jest lepsze niż łączenie statyczne

Zalecamy uniknięcie konsolidacji statycznej podczas ponownej dystrybucji bibliotek Visual C++. Chociaż łączenie statyczne prawie nigdy nie zwiększa znacznie wydajności aplikacji, to prawie zawsze sprawia, że serwisowanie jest droższe. Rozważmy na przykład aplikację, statycznie połączoną z biblioteką, która to biblioteka została zaktualizowana, aby poprawić jej zabezpieczenia — aplikacja z nich nie skorzysta, chyba że zostanie zrekompilowana i ponownie wdrożona. Zamiast tego zaleca się dynamiczne łączenie aplikacji z bibliotekami, od których zależą, aby można było aktualizować biblioteki, kiedy zostaną wdrożone.

## <a name="see-also"></a>Zobacz też

[Wdrażanie aplikacji klasycznych](deploying-native-desktop-applications-visual-cpp.md)<br>
[Bezpieczeństwo i wdrażanie technologii ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Przykłady wdrożeń](deployment-examples.md)

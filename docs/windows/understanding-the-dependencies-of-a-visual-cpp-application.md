---
description: Dowiedz się więcej o tym, jak zrozumieć zależności aplikacji Visual C++
title: Poznanie zależności aplikacji Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- application deployment [C++], dependencies
- Dependency Walker
- dependencies [C++], application deployment and
- deploying applications [C++], dependencies
- DUMPBIN utility
- DLLs [C++], dependencies
- depends.exe
- libraries [C++], application deployment issues
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
ms.openlocfilehash: ff18d594edf6d35541655075de6f6e951ea42b88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336560"
---
# <a name="understanding-the-dependencies-of-a-visual-c-application"></a>Poznanie zależności aplikacji Visual C++

Aby określić, które biblioteki Visual C++ od których zależy aplikacja, możesz wyświetlić właściwości projektu. (W Eksplorator rozwiązań kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Właściwości** , aby otworzyć okno dialogowe **strony właściwości** .) W systemie Windows 8 i starszych wersjach można również użyć analizatora zależności (depends.exe), który zapewnia bardziej szczegółowy obraz zależności. W przypadku nowszych wersji systemu Windows narzędzie [lucasg/zależności](https://github.com/lucasg/Dependencies) zapewnia podobną funkcjonalność (to narzędzie innej firmy nie jest gwarantowane przez firmę Microsoft).

W oknie dialogowym **strony właściwości** można sprawdzić różne strony w obszarze **Właściwości konfiguracji** , aby zrozumieć zależności. Na przykład jeśli projekt używa bibliotek MFC i wybierasz **użycie MFC**, **Użyj MFC w współdzielonej bibliotece DLL** na stronie **Właściwości konfiguracji**, **Ogólne** , aplikacja w czasie wykonywania zależy od bibliotek DLL MFC, takich jak MFC \<version> . dll. Jeśli aplikacja nie korzysta z MFC, może ona zależeć od biblioteki CRT w przypadku wybrania wartości **biblioteki środowiska uruchomieniowego** dla **wielowątkowej biblioteki DLL (/MDD)** lub **wielowątkowej biblioteki DLL (/MD)** na stronie **Właściwości konfiguracji**, **C/C++**, **generowanie kodu** .

Za pomocą depends.exe można przeanalizować listę bibliotek DLL, które są połączone z aplikacją w czasie ładowania, oraz listę bibliotek DLL załadowanych z opóźnieniem. Jeśli chcesz uzyskać kompletną listę bibliotek DLL, które są ładowane dynamicznie w czasie wykonywania, możesz użyć funkcji profilowania w depends.exe do testowania aplikacji, dopóki nie masz pewności, że wszystkie ścieżki kodu zostały wykonane. Po zakończeniu sesji profilowania depends.exe pokazuje, które biblioteki DLL zostały dynamicznie załadowane w czasie wykonywania.

Korzystając z depends.exe, należy pamiętać, że biblioteka DLL może zależeć od innej biblioteki DLL lub od określonej wersji biblioteki DLL. Można użyć depends.exe na komputerze deweloperskim lub na komputerze docelowym. Na komputerze deweloperskim depends.exe raportuje biblioteki DLL, które są wymagane do obsługi aplikacji. Jeśli masz problemy z uruchomieniem aplikacji na komputerze docelowym, możesz skopiować do niego depends.exe i następnie otworzyć aplikację za pomocą narzędzia, aby określić, czy któryś wymagany plik DLL jest niedostępny lub nieprawidłowy.

Jeśli wiadomo, od których plików DLL zależy aplikacja, możesz określić te, które trzeba rozpowszechniać wraz z aplikacją, kiedy wdraża się ją na innym komputerze. W większości przypadków nie trzeba redystrybuować systemowych bibliotek DLL, ale może być konieczne ponowne dystrybuowanie bibliotek DLL dla bibliotek Visual C++. Aby uzyskać więcej informacji, zobacz [Określanie bibliotek DLL do redystrybucji](determining-which-dlls-to-redistribute.md).

## <a name="see-also"></a>Zobacz też

[Wdrażanie aplikacji klasycznych](deploying-native-desktop-applications-visual-cpp.md)

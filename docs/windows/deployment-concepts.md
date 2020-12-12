---
description: 'Dowiedz się więcej o programie: koncepcje wdrażania'
title: Pojęcia związane z wdrażaniem
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Installer [C++]
- dependencies [C++], application deployment and
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- libraries [C++], application deployment issues
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
ms.openlocfilehash: 441e067a541f375029cdb55321a8ad75d1f03c67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329431"
---
# <a name="deployment-concepts"></a>Pojęcia związane z wdrażaniem

W tej sekcji omówiono główne zagadnienia dotyczące wdrażania aplikacji w języku C++.

## <a name="windows-installer-deployment-in-c"></a>Wdrożenie Instalator Windows w języku C++

Projekty programu Visual Studio C++ zwykle używają tradycyjnego Instalatora Instalator Windows do wdrożenia. Aby przygotować wdrożenie Instalator Windows, należy spakować aplikację w pliku setup.exe i rozesłać ten plik wraz z pakietem Instalatora (msi). Następnie użytkownicy uruchamiają setup.exe, aby zainstalować aplikację.

Możesz spakować aplikację, dodając do rozwiązania projekt konfiguracji; po skompilowaniu tworzy pliki pakietu instalacyjnego i Instalatora, które są dystrybuowane do użytkowników. Aby uzyskać więcej informacji, zobacz [Wybieranie metody wdrożenia](choosing-a-deployment-method.md).

## <a name="library-dependencies"></a>Zależności biblioteki

Po skompilowaniu aplikacji C/C++ przy użyciu funkcjonalności udostępnionej przez Visual C++ biblioteki stają się one zależne od obecności tych bibliotek w czasie wykonywania. Aby można było uruchomić aplikację, musi ona łączyć się statycznie lub dynamicznie z niezbędnymi bibliotekami Visual C++. Jeśli aplikacja łączy się dynamicznie z biblioteką Visual C++, wtedy, gdy została uruchomiona, musi być obecna, aby mogła zostać załadowana. Z drugiej strony, jeśli aplikacja statycznie łączy się z biblioteką Visual C++, wówczas nie potrzebuje odpowiednich bibliotek DLL na komputerze użytkownika. Konsolidacja statyczna ma jednak pewne negatywne skutki, takie jak zwiększenie rozmiaru plików aplikacji i utrudnianie konserwacji. Aby uzyskać więcej informacji, zobacz [zalety korzystania z bibliotek DLL](../build/dlls-in-visual-cpp.md#advantages-of-using-dlls).

## <a name="packaging-and-redistributing"></a>Pakowanie i ponowne dystrybuowanie

Biblioteki Visual C++ są spakowane jako biblioteki DLL, a wszystkie niezbędne biblioteki dla aplikacji C/C++ są instalowane przez program Visual Studio na komputerze dewelopera. Jednak w przypadku wdrażania aplikacji dla użytkowników nie jest to możliwe w większości przypadków, aby wymagać od nich zainstalowania programu Visual Studio w celu uruchomienia aplikacji. Ważne jest, aby można było ponownie rozpowszechniać tylko te części Visual C++, które są wymagane przez aplikację do poprawnego działania.

Aby uzyskać więcej informacji na temat tworzenia pakietów i redystrybucji, zobacz następujące tematy:

- [Określanie bibliotek DLL do redystrybucji](determining-which-dlls-to-redistribute.md).

- [Wybór metody wdrażania](choosing-a-deployment-method.md).

- [Wdrożenie uniwersalnej CRT](universal-crt-deployment.md).

Przykłady wdrażania i sugestie dotyczące rozwiązywania problemów znajdują się w temacie:

- [Przykłady wdrożenia](deployment-examples.md).

- [Rozwiązywanie problemów z aplikacjami izolowanymi C/C++ i zestawami równoległymi](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).

## <a name="see-also"></a>Zobacz też

- [Wdrażanie aplikacji klasycznych](deploying-native-desktop-applications-visual-cpp.md)
- [Poznanie zależności aplikacji Visual C++](understanding-the-dependencies-of-a-visual-cpp-application.md)

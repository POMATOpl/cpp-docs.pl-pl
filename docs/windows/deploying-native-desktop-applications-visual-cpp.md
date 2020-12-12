---
description: 'Dowiedz się więcej o programie: wdrażanie natywnych aplikacji klasycznych (Visual C++)'
title: Wdrażanie natywnych aplikacji komputerowych (Visual C++)
ms.date: 05/11/2018
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
- Visual C++, application deployment
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- distributing applications [C++]
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
ms.topic: overview
ms.openlocfilehash: c3da460266eb630e7ac243f523fa6e89a79fa1f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329439"
---
# <a name="deploying-native-desktop-applications-visual-c"></a>Wdrażanie natywnych aplikacji komputerowych (Visual C++)

Wdrożenie to proces dystrybucji ukończonej aplikacji lub składnika, który ma zostać zainstalowany na innych komputerach. Planowanie wdrożenia jest uruchamiane, gdy aplikacja zostanie utworzona na komputerze dewelopera. Wdrożenie jest zakończone, gdy aplikacja jest zainstalowana i gotowa do uruchomienia na komputerze użytkownika.

Program Visual Studio oferuje różne technologie wdrażania aplikacji systemu Windows. Obejmują one wdrożenie ClickOnce i wdrożenie Instalator Windows.

- Technologii ClickOnce można użyć do wdrożenia aplikacji C++ przeznaczonych dla środowiska uruchomieniowego języka wspólnego (CLR) — mieszanych, czystych i sprawdzalnych zestawów. Mimo że można użyć Instalator Windows do wdrożenia aplikacji zarządzanej, zalecamy korzystanie z technologii ClickOnce, ponieważ wykorzystuje ona .NET Framework funkcje zabezpieczeń, takie jak podpisywanie manifestu. Technologia ClickOnce nie obsługuje wdrażania natywnych aplikacji C++. Aby uzyskać więcej informacji, zobacz [wdrażanie ClickOnce dla aplikacji Visual C++](clickonce-deployment-for-visual-cpp-applications.md).

- Technologii Instalator Windows można użyć do wdrożenia natywnych aplikacji C++ lub aplikacji C++ przeznaczonych dla środowiska CLR.

Artykuły w tej części dokumentacji omawiają, jak zapewnić, że Natywna aplikacja Visual C++ działa na dowolnym komputerze, który zapewnia obsługiwaną platformę docelową, które pliki należy dołączyć do pakietu instalacyjnego, oraz zalecane sposoby na ponowne rozproszenie składników, od których zależy aplikacja.

## <a name="in-this-section"></a>W tej sekcji

- [Wdrożenie w Visual C++](deployment-in-visual-cpp.md)

- [Pojęcia związane z wdrażaniem](deployment-concepts.md)

- [Poznanie zależności aplikacji Visual C++](understanding-the-dependencies-of-a-visual-cpp-application.md)

- [Ustalanie, które biblioteki DLL są przeznaczone do ponownej dystrybucji](determining-which-dlls-to-redistribute.md)

- [Wybieranie metody wdrażania](choosing-a-deployment-method.md)

- [Wdrożenie uniwersalnej CRT](universal-crt-deployment.md).

- [Ponowne dystrybuowanie plików programu Visual C++](redistributing-visual-cpp-files.md)

- [Przykłady wdrożeń](deployment-examples.md)

- [Ponowne dystrybuowanie aplikacji klienta sieci Web](redistributing-web-client-applications.md)

- [Wdrożenie ClickOnce dla aplikacji Visual C++](clickonce-deployment-for-visual-cpp-applications.md)

- [Uruchamianie aplikacji C++/clr w poprzedniej wersji środowiska uruchomieniowego](running-a-cpp-clr-application-on-a-previous-runtime-version.md)

## <a name="related-sections"></a>Sekcje pokrewne

- [Kompilowanie aplikacji izolowanych C/C++ i zestawów równoległych](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

- [Wdrożenie](/dotnet/framework/deployment/index)

- [Rozwiązywanie problemów z aplikacjami izolowanymi C/C++ i zestawami równoległymi](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

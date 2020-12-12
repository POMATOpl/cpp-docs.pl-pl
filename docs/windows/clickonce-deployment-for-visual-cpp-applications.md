---
description: Dowiedz się więcej na temat wdrażania technologii ClickOnce dla aplikacji Visual C++
title: Wdrożenie rozwiązania ClickOnce dla aplikacji Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
ms.openlocfilehash: eb888e9236eec16ba82c82c11a23428163679e97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118215"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Wdrożenie rozwiązania ClickOnce dla aplikacji Visual C++

Program Visual Studio udostępnia dwie różne technologie wdrażania aplikacji systemu Windows: wdrożenie ClickOnce lub wdrożenie [Instalator Windows](/windows/win32/Msi/windows-installer-portal) .

## <a name="clickonce-deployment-in-c"></a>Wdrożenie ClickOnce w języku C++

Środowisko programistyczne Visual C++ nie obsługuje bezpośrednio wdrażania projektów Visual Studio C++ przy użyciu technologii ClickOnce, ale dostępne są narzędzia do ich używania.

> [!NOTE]
> Program Visual Studio obsługuje technologii ClickOnce w środowiskach deweloperskich Visual C# i Visual Basic. Jeśli projekt Visual Studio C++ jest zależnością projektu Visual C#, można opublikować aplikację (łącznie z jej zależnościami) przy użyciu wdrożenia ClickOnce ze środowiska deweloperskiego Visual C#.

Aby wdrożyć aplikację Visual C++ przy użyciu technologii ClickOnce, należy najpierw skompilować [manifest aplikacji ClickOnce](/visualstudio/deployment/clickonce-application-manifest) i [manifest wdrożenia clickonce](/visualstudio/deployment/clickonce-deployment-manifest) przy użyciu [Mage.exe (narzędzie tworzenia i edycji manifestów)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) lub jego graficznej wersji interfejsu użytkownika (Aby uzyskać informacje, zobacz [MageUI.exe (narzędzie tworzenia i edycji manifestów, klient graficzny)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).

Najpierw należy używać Mage.exe do kompilowania manifestu aplikacji; otrzymany plik będzie miał rozszerzenie. manifest. Następnie użyj Mage.exe do skompilowania manifestu wdrożenia. otrzymany plik będzie miał rozszerzenie. Application. Następnie Podpisz manifesty.

Manifest aplikacji musi określać procesor docelowy (**x86**, **x64** lub **ARM**). Aby uzyskać informacje na temat tych opcji, zobacz temat [wdrażanie wymagań wstępnych dla aplikacji 64-bitowych](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) .

Ponadto nazwy aplikacji i manifestów wdrożenia muszą być inne niż nazwa aplikacji C++. Pozwala to uniknąć konfliktu między manifestem aplikacji utworzonym przez Mage.exe a zewnętrznym manifestem, który jest częścią aplikacji C++.

Wdrożenie będzie wymagało zainstalowania wszelkich Visual C++ bibliotek, od których zależy aplikacja. Aby określić zależności dla konkretnej aplikacji, można użyć depends.exe lub narzędzia polecenia DUMPBIN z opcją/DEPENDENTS. Aby uzyskać więcej informacji o zależnościach, zobacz [Omówienie zależności aplikacji Visual C++](understanding-the-dependencies-of-a-visual-cpp-application.md). Może być konieczne uruchomienie VCRedist.exe; to narzędzie służy do instalowania bibliotek Visual C++ na komputerze docelowym.

Może być również konieczne skompilowanie programu inicjującego (Instalator wymagań wstępnych) dla aplikacji w celu wdrożenia składników wymaganych wstępnie. Aby uzyskać informacje na temat programu inicjującego, zobacz [Tworzenie pakietów programu inicjującego](/visualstudio/deployment/creating-bootstrapper-packages).

Aby uzyskać bardziej szczegółowy opis technologii, zobacz [zabezpieczenia i wdrażanie aplikacji ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Aby zapoznać się ze szczegółowym przykładem wdrażania ClickOnce, zobacz [Przewodnik: ręczne wdrażanie aplikacji ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).

## <a name="see-also"></a>Zobacz też

[Mage.exe (Narzędzie tworzenia i edycji manifestów)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)<br>
[MageUI.exe (Narzędzie tworzenia i edycji manifestów, klient graficzny)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)<br>
[Makecert.exe (narzędzie tworzenia certyfikatów)](/windows/win32/SecCrypto/makecert)<br>
[Wdrażanie aplikacji klasycznych](deploying-native-desktop-applications-visual-cpp.md)<br>
[Wdrażanie aplikacji, usług i składników](/visualstudio/deployment/deploying-applications-services-and-components)<br>
[Bezpieczeństwo i wdrażanie technologii ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)<br>
[Tworzenie pakietów programu inicjującego](/visualstudio/deployment/creating-bootstrapper-packages)<br>
[Programowanie .NET w języku C++/interfejsie wiersza polecenia (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br>
[Współdziałanie natywne i .NET](../dotnet/native-and-dotnet-interoperability.md)

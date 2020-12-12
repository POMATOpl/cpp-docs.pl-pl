---
description: 'Dowiedz się więcej o programie: obsługiwane platformy (Visual C++)'
title: Obsługiwane platformy (Visual C++)
ms.date: 12/02/2019
ms.technology: cpp-tools
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
ms.openlocfilehash: 80f8693a8cef7368953779d82100ce02e41f5cd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207517"
---
# <a name="supported-platforms-visual-c"></a>Obsługiwane platformy (Visual C++)

Aplikacje utworzone za pomocą programu Visual Studio mogą być przeznaczone dla różnych platform w następujący sposób.

|System operacyjny|x86|x64|ARM|ARM64\*\*\*\*|
|----------------------|---------|---------|---------|---------|
|Windows XP|Y\*|Y\*|||
|Windows Server 2003|Y\*|Y\*|||
|Windows Vista|X|X|||
|Windows Server 2008|X|X|||
|Windows 7|X|X|||
|Windows Server 2012 z dodatkiem R2|X|X|||
|Windows 8|X|X|X||
|Windows 8.1|X|X|X||
|Windows 10|X|X|X|X|
|Systemów \*\*|X|X|X|X|
|Wykonane \*\*|X|X|X|X|
|System \*\*\*|X|X|X|X|

\* Do tworzenia projektów systemu Windows XP i Windows Server 2003 można użyć zestawu narzędzi platformy systemu Windows XP dołączonego do programów Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 i Visual Studio 2012 Update 1. Aby uzyskać informacje na temat korzystania z tego zestawu narzędzi platformy, zobacz [Konfigurowanie programów dla systemu Windows XP](../build/configuring-programs-for-windows-xp.md). Aby uzyskać dodatkowe informacje na temat zmiany zestawu narzędzi platformy, zobacz [How to: Modify The Target Framework and platform zestaw narzędzi](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

\*\* Możesz zainstalować **Programowanie aplikacji mobilnych za pomocą języka C++** w Instalatorze programu Visual Studio 2017 i nowszych. W Instalatorze programu Visual Studio 2015 wybierz opcjonalny **Visual C++ dla wieloplatformowego programu do tworzenia aplikacji mobilnych** , który będzie przeznaczony dla platform iOS lub Android. Aby uzyskać instrukcje, zobacz [Install Visual C++ dla opracowywania aplikacji mobilnych na wiele platform](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). Aby skompilować kod dla systemu iOS, musisz mieć komputer Mac i spełnić inne wymagania. Aby uzyskać listę wymagań wstępnych i instrukcji instalacji, zobacz [Instalowanie i Konfigurowanie narzędzi do kompilowania przy użyciu systemu iOS](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). Można skompilować kod x86 lub ARM w celu dopasowania go do sprzętu docelowego. Użyj konfiguracji x86, aby skompilować symulatory systemu iOS, Microsoft Visual Studio Emulator for Android i niektóre urządzenia z systemem Android. Użyj konfiguracji usługi ARM do kompilowania urządzeń z systemem iOS i większości urządzeń z systemem Android.

\*\*\* Możesz zainstalować Programowanie dla systemu **Linux przy użyciu obciążenia języka C++** w Instalatorze programu Visual Studio 2017 i nowszych wersjach systemu Linux. Aby uzyskać instrukcje, zobacz [pobieranie, Instalowanie i Konfigurowanie obciążenia systemu Linux](../linux/download-install-and-setup-the-linux-development-workload.md). Ten zestaw narzędzi kompiluje plik wykonywalny na komputerze docelowym, aby można było utworzyć dowolną obsługiwaną architekturę.

\*\*\*\* Obsługa ARM64 jest dostępna w programie Visual Studio 2017 i nowszych.

Aby uzyskać informacje na temat sposobu ustawiania konfiguracji platformy docelowej, zobacz [How to: Configure Visual C++ Projects to target 64-bit i x64 platform](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

## <a name="see-also"></a>Zobacz też

- [Narzędzia i funkcje programu Visual C++ w wydaniach programu Visual Studio](visual-cpp-tools-and-features-in-visual-studio-editions.md)
- [Wprowadzenie](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)

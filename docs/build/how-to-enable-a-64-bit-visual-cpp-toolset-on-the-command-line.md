---
description: 'Dowiedz się więcej na temat: jak włączyć 64-bitowy, MSVC zestaw narzędzi dla architektury x64 w wierszu polecenia'
title: 'Instrukcje: włączanie 64-bitowego zestawu narzędzi MSVC w wierszu polecenia'
ms.date: 07/24/2019
helpviewer_keywords:
- x64 [C++]
- 64-bit compiler [C++], command line usage
- 64-bit compiler [C++], toolset enabling at command line
- command line [C++], 64-bit compiler
- Itanium [C++], command-line compiler
- IPF
- Itanium [C++]
- IPF, command-line compiler
- x64 [C++], command-line compiler
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
ms.openlocfilehash: d5e712802f420d425f4a0291d88220c22d4aeb62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162732"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-msvc-toolset-on-the-command-line"></a>Instrukcje: włączanie 64-bitowego, obsługiwanego przez x64 zestawu narzędzi MSVC w wierszu polecenia

Program Visual Studio obejmuje kompilatory języka C++, linki i inne narzędzia, których można użyć do tworzenia specyficznych dla platformy wersji aplikacji, które mogą być uruchamiane w systemach operacyjnych Windows 32-bitowych, 64-bitowych lub opartych na architekturze ARM. Inne opcjonalne obciążenia programu Visual Studio umożliwiają używanie narzędzi C++ do obsługi innych platform, takich jak iOS, Android i Linux. Domyślna architektura kompilacji używa 32-bitowych i opartych na procesorze x86 narzędzi do kompilowania 32-bitowego kodu systemu Windows w języku x86. Jednak prawdopodobnie masz komputer 64-bitowy. Gdy program Visual Studio jest zainstalowany w 64-bitowym systemie operacyjnym Windows, dostępne są dodatkowe skróty do wiersza polecenia dla deweloperów dla 64-bitowe, obsługiwane przez x64 kompilatory natywne i krzyżowe. Można korzystać z procesora i pamięci dostępnej dla kodu 64-bitowego przy użyciu zestawu narzędzi 64-bit, x64-Hosted podczas kompilowania kodu dla procesorów x86, x64 lub ARM.

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>Użyj 64-bitowego, obsługiwanego skrótu wiersza polecenia dla deweloperów

Aby uzyskać dostęp do tych wierszy poleceń w systemie Windows 10, w menu **Start** Otwórz folder dla używanej wersji programu Visual Studio, na przykład **Visual Studio 2019**, a następnie wybierz jedno z wierszy poleceń dla deweloperów x64 lub wielu narzędzi.

![wiersz polecenia narzędzi x64 Native Tools](media/x64-native-tools-command-prompt.png "Narzędzia x64 Native Tools w menu Start")

Aby uzyskać dostęp do tych wierszy poleceń w systemie Windows 8, na ekranie **startowym** Otwórz **wszystkie aplikacje**. Pod nagłówkiem zainstalowanej wersji programu Visual Studio, Otwórz folder **programu Visual Studio** (w starszych wersjach programu Visual Studio, może mieć nazwę **Visual Studio Tools**). We wcześniejszych wersjach systemu Windows wybierz **Start**, rozwiń **Wszystkie programy**, folder dla używanej wersji programu **Visual Studio** (i starszych wersji programu Visual Studio, **Visual Studio Tools**). Aby uzyskać więcej informacji, zobacz [skróty do wiersza polecenia dla deweloperów](building-on-the-command-line.md#developer_command_prompt_shortcuts).

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Użyj Vcvarsall.bat, aby ustawić 64-bitową architekturę kompilacji hostowanej

Wszystkie konfiguracje kompilacji natywnych lub międzypracujących kompilatorów można użyć w wierszu polecenia, uruchamiając plik poleceń vcvarsall.bat. Ten plik polecenia służy do konfigurowania ścieżki i zmiennych środowiskowych, które umożliwiają konkretną architekturę kompilacji w istniejącym oknie wiersza polecenia. Aby uzyskać szczegółowe instrukcje, zobacz [lokalizacje plików poleceń deweloperskich](building-on-the-command-line.md#developer_command_file_locations).

## <a name="remarks"></a>Uwagi

> [!NOTE]
> Aby uzyskać informacje o określonych narzędziach, które są dołączone do poszczególnych wersji programu Visual Studio, zobacz [Visual C++ narzędzia i funkcje w wersjach programu Visual Studio](../overview/visual-cpp-tools-and-features-in-visual-studio-editions.md).
>
> Aby uzyskać informacje o sposobach tworzenia aplikacji 64-bitowych przy użyciu środowiska IDE programu Visual Studio, zobacz [How to: Configure Visual C++ Projects to Target 64-bit i x64 platform](how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

Podczas instalowania obciążenia języka C++ w Instalatorze programu Visual Studio do tworzenia kodu x86 i x64 są zawsze instalowane 32-bitowe, oparte na architekturze x86, natywne i wielostronicowe narzędzia kompilatora. Jeśli dołączysz obciążenie platforma uniwersalna systemu Windows, instaluje także narzędzia międzykompilatorowe obsługiwane przez architekturę x86 do kompilowania kodu ARM. Jeśli zainstalowano te obciążenia na 64-bitowym procesorze x64, możesz również uzyskać 64-bitowe natywne i krzyżowe narzędzia kompilatora do kompilowania kodu x86, x64 i ARM. Narzędzia 32-bitowe i 64-bitowe generują identyczny kod, ale narzędzia 64-bitowe obsługują więcej pamięci dla wstępnie skompilowanych symboli nagłówka i opcji optymalizacji programu ([/GL](reference/gl-whole-program-optimization.md) i [/LTCG](reference/ltcg-link-time-code-generation.md)). Jeśli podczas korzystania z narzędzi 32-bitowych używasz limitów pamięci, wypróbuj narzędzia 64-bitowe.

## <a name="see-also"></a>Zobacz też

[Konfigurowanie projektów C++ dla 64-bitowych, docelowych procesorów x64](configuring-programs-for-64-bit-visual-cpp.md)<br/>

---
title: Programowanie .NET w języku C++/interfejsie wiersza polecenia
description: Dowiedz się, jak tworzyć aplikacje i składniki platformy .NET w programie Visual Studio przy użyciu języka C++/CLI.
ms.date: 12/08/2020
helpviewer_keywords:
- programming [C++], .NET programming
- .NET Framework [C++]
- .NET applications [C++]
- Visual C++, .NET programming
ms.openlocfilehash: 80a9743016976e307158608134155dc7272d44a8
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933186"
---
# <a name="net-programming-with-ccli"></a>Programowanie .NET w języku C++/interfejsie wiersza polecenia

::: moniker range="msvc-140"

Domyślnie projekty CLR utworzone przy użyciu programu Visual Studio 2015 Target .NET Framework 4.5.2. Podczas tworzenia nowego projektu można wskazać .NET Framework 4,6. W oknie dialogowym **Nowy projekt** Zmień platformę docelową na liście rozwijanej w górnej części okna dialogowego. Aby zmienić platformę docelową dla istniejącego projektu, Zamknij projekt, edytuj plik projektu ( *`.vcxproj`* ) i zmień wartość docelowej wersji platformy na 4,6. Zmiany zaczną obowiązywać przy następnym otwarciu projektu.

::: moniker-end
::: moniker range="msvc-150"

W programie Visual Studio 2017 domyślny .NET Framework docelowy to 4.6.1. Selektor wersji platformy znajduje się u dołu okna dialogowego **Nowy projekt** .

## <a name="install-ccli-support-in-visual-studio-2017"></a>Zainstaluj obsługę języka C++/CLI w programie Visual Studio 2017

Sama/CLI języka c++ nie jest instalowana domyślnie podczas instalowania obciążeń programu Visual Studio C++. Aby zainstalować składnik po zainstalowaniu programu Visual Studio, Otwórz Instalator programu Visual Studio. Wybierz przycisk **Modyfikuj** obok zainstalowanej wersji programu Visual Studio. Wybierz kartę **zainstalowane składniki** . Przewiń w dół do sekcji **kompilatory, narzędzia kompilacji i środowiska uruchomieniowe** , a następnie wybierz opcję **Obsługa języka C++/CLI**. Wybierz pozycję **Modyfikuj** , aby zaktualizować program Visual Studio.

::: moniker-end
::: moniker range="msvc-160"

W programie Visual Studio 2019 domyślną platformą docelową dla projektów .NET Core jest 5,0. W przypadku projektów programu .NET Framework wartością domyślną jest 4.7.2. Selektor wersji .NET Framework znajduje się na stronie **Konfigurowanie nowego projektu** okna dialogowego **Tworzenie nowego projektu** .
## <a name="install-ccli-support-in-visual-studio-2019"></a>Zainstaluj obsługę języka C++/CLI w programie Visual Studio 2019

Sama/CLI języka c++ nie jest instalowana domyślnie podczas instalowania obciążeń programu Visual Studio C++. Aby zainstalować składnik po zainstalowaniu programu Visual Studio, Otwórz Instalator programu Visual Studio. Wybierz przycisk **Modyfikuj** obok zainstalowanej wersji programu Visual Studio. Wybierz kartę **zainstalowane składniki** . Przewiń w dół do sekcji **kompilatory, narzędzia kompilacji i środowiska uruchomieniowe** , a następnie wybierz najnowszą **obsługę języka C++/CLI dla składnika narzędzia kompilacji v142** . Wybierz pozycję **Modyfikuj** , aby zaktualizować program Visual Studio.

::: moniker-end

## <a name="in-this-section"></a>W tej sekcji

[Zadania C++/CLI](../dotnet/cpp-cli-tasks.md)

[Współdziałanie natywne i .NET](../dotnet/native-and-dotnet-interoperability.md)

[Kod czysty i możliwy do zweryfikowania (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)

[Wyrażenia regularne (C++/CLI)](../dotnet/regular-expressions-cpp-cli.md)

[Obsługa plików i we/wy (C++/CLI)](../dotnet/file-handling-and-i-o-cpp-cli.md)

[Operacje graficzne (C++/CLI)](../dotnet/graphics-operations-cpp-cli.md)

[Operacje systemu Windows (C++/CLI)](../dotnet/windows-operations-cpp-cli.md)

[Dostęp do danych za pomocą ADO.NET (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)

[Współdziałanie z innymi językami .NET (C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)

[Serializacja (C++/CLI)](../dotnet/serialization-cpp-cli.md)

[Typy zarządzane (C++/CLI)](../dotnet/managed-types-cpp-cli.md)

[Odbicie (C++/CLI)](../dotnet/reflection-cpp-cli.md)

[Zestawy o silnych nazwach (podpisywanie zestawów) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)

[Debug — Klasa (C++/CLI)](../dotnet/debug-class-cpp-cli.md)

[Dokumentacja biblioteki STL/CLR](../dotnet/stl-clr-library-reference.md)

[Biblioteka obsługi języka C++](../dotnet/cpp-support-library.md)

[Wyjątki w języku C++/CLI](../dotnet/exceptions-in-cpp-cli.md)

[Konwersja boxing (C++/CLI)](../dotnet/boxing-cpp-cli.md)

## <a name="see-also"></a>Zobacz też

[Współdziałanie natywne i .NET](../dotnet/native-and-dotnet-interoperability.md)

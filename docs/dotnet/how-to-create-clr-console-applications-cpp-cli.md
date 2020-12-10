---
title: 'Porady: tworzenie aplikacji do konsoli środowiska CLR (C++/CLI)'
description: Dowiedz się, jak tworzyć projekty aplikacji konsolowych CLR w celu używania języka C++/CLI w programie Visual Studio.
ms.date: 12/08/2020
helpviewer_keywords:
- console applications, templates
- CLR console applications, project template
ms.openlocfilehash: ef74ca4cc31884543ff18d63d981504f36d1838e
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933225"
---
# <a name="how-to-create-clr-console-applications-ccli"></a>Porady: tworzenie aplikacji do konsoli środowiska CLR (C++/CLI)

::: moniker range="msvc-140"

Możesz użyć szablonu  **aplikacji konsoli CLR** w oknie dialogowym **Nowy projekt** , aby utworzyć projekt aplikacji konsoli, który ma już istotne odwołania i pliki projektu.

::: moniker-end
::: moniker range="msvc-150"

Możesz użyć szablonu **aplikacji konsoli CLR** w oknie dialogowym **Nowy projekt** , aby utworzyć projekt aplikacji konsoli, który ma już istotne odwołania i pliki projektu.

Obsługa języka c++/CLI nie jest instalowana domyślnie podczas instalowania obciążeń programu Visual Studio C++. Jeśli nie widzisz nagłówka CLR w obszarze Visual C++ w oknie dialogowym **Nowy projekt** , może być konieczne zainstalowanie obsługi C++/CLI. Aby uzyskać więcej informacji, zobacz [programowanie .NET przy użyciu języka C++/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

::: moniker-end
::: moniker range="msvc-160"

Możesz użyć szablonu **aplikacja konsoli CLR (.NET Framework)** w oknie dialogowym **Utwórz nowy projekt** , aby utworzyć projekt aplikacji konsoli, który ma już istotne odwołania i pliki projektu.

Obsługa języka c++/CLI nie jest instalowana domyślnie podczas instalowania obciążeń programu Visual Studio C++. Jeśli szablony projektów CLR nie są wyświetlane w oknie dialogowym  **Tworzenie nowego projektu** , może być konieczne zainstalowanie obsługi języka C++/CLI. Aby uzyskać więcej informacji, zobacz [programowanie .NET przy użyciu języka C++/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

::: moniker-end

Zazwyczaj Aplikacja konsolowa jest kompilowana w autonomiczny plik wykonywalny, ale nie ma graficznego interfejsu użytkownika. Użytkownicy uruchamiają aplikację konsolową w wierszu polecenia. Mogą używać wiersza polecenia do wydawania instrukcji dla uruchomionej aplikacji. Aplikacja dostarcza informacje wyjściowe jako tekst w oknie poleceń. Natychmiastowa Opinia dotycząca aplikacji konsolowej ułatwia naukę programowania. Nie musisz martwić się o sposób implementacji graficznego interfejsu użytkownika.

::: moniker range="msvc-140"

W przypadku tworzenia projektu przy użyciu szablonu Aplikacja konsolowa CLR program automatycznie dodaje te odwołania i pliki:

- Odwołania do tych przestrzeni nazw .NET Framework:

  - <xref:System>, <xref:System.Data> , <xref:System.Xml> : Te odwołania zawierają podstawowe klasy, które definiują najczęściej używane typy, zdarzenia, interfejsy, atrybuty i wyjątki.

  - *`mscorlib.dll`*: Zestaw DLL, który obsługuje programowanie .NET Framework.

- Pliki źródłowe:

  - *`ConsoleApplicationName.cpp`*: Główny plik źródłowy i punkt wejścia do aplikacji. Ten plik ma nazwę bazową określoną dla projektu. Identyfikuje plik biblioteki DLL projektu i przestrzeń nazw projektu. Podaj własny kod w tym pliku.

  - *`AssemblyInfo.cpp`*: Zawiera atrybuty i ustawienia, których można użyć do zmodyfikowania metadanych zestawu projektu. Aby uzyskać więcej informacji, zobacz [zawartość zestawu](/dotnet/framework/app-domains/assembly-contents).

  - *`stdafx.cpp`*: Służy do kompilowania prekompilowanego pliku nagłówkowego o nazwie *`ConsoleApplicationName.pch`* i prekompilowanego pliku typu o nazwie *`stdafx.obj`* .

- Pliki nagłówkowe:

  - *`stdafx.h`*: Służy do kompilowania prekompilowanego pliku nagłówkowego o nazwie *`ConsoleApplicationName.pch`* i prekompilowanego pliku typu o nazwie *`stdafx.obj`* .

  - *`resource.h`*: Wygenerowany plik dołączany dla *`app.rc`* .

- Pliki zasobów:

  - *`app.rc`*: Plik skryptu zasobu programu.

  - *`app.ico`*: Plik ikony programu.

- *`ReadMe.txt`*: Opisuje pliki w projekcie.

::: moniker-end
::: moniker range=">=msvc-150"

W przypadku tworzenia projektu przy użyciu szablonu aplikacji konsolowej CLR program automatycznie dodaje te odwołania i pliki:

- Odwołania do tych przestrzeni nazw .NET Framework:

  - <xref:System>, <xref:System.Data> , <xref:System.Xml> : Te odwołania zawierają podstawowe klasy, które definiują najczęściej używane typy, zdarzenia, interfejsy, atrybuty i wyjątki.

  - *`mscorlib.dll`*: Zestaw DLL, który obsługuje programowanie .NET Framework.

- Pliki źródłowe:

  - *`ConsoleApplicationName.cpp`*: Główny plik źródłowy i punkt wejścia do aplikacji. Ten plik ma nazwę bazową określoną dla projektu. Identyfikuje plik biblioteki DLL projektu i przestrzeń nazw projektu. Podaj własny kod w tym pliku.

  - *`AssemblyInfo.cpp`*: Zawiera atrybuty i ustawienia, których można użyć do zmodyfikowania metadanych zestawu projektu. Aby uzyskać więcej informacji, zobacz [zawartość zestawu](/dotnet/framework/app-domains/assembly-contents).

  - *`pch.cpp`*: Służy do kompilowania prekompilowanego pliku nagłówkowego o nazwie *`ConsoleApplicationName.pch`* i prekompilowanego pliku typu o nazwie *`pch.obj`* .

- Pliki nagłówkowe:

  - *`pch.h`*: Służy do kompilowania prekompilowanego pliku nagłówkowego o nazwie *`ConsoleApplicationName.pch`* i prekompilowanego pliku typu o nazwie *`pch.obj`* .

  - *`Resource.h`*: Wygenerowany plik dołączany dla *`app.rc`* .

- Pliki zasobów:

  - *`app.rc`*: Plik skryptu zasobu programu.

  - *`app.ico`*: Plik ikony programu.

::: moniker-end

## <a name="to-create-a-clr-console-app-project"></a>Aby utworzyć projekt aplikacji konsoli CLR

::: moniker range="msvc-140"

1. Na pasku menu wybierz pozycję **plik** > **Nowy** > **projekt**.

1. W oknie dialogowym **Nowy projekt** wybierz **zainstalowane** > **Szablony** > **Visual C++** > węźle **CLR** , a następnie wybierz szablon **aplikacja konsoli CLR** .

1. W polu **Nazwa** wprowadź unikatową nazwę aplikacji.

   Możesz określić inne ustawienia projektu i rozwiązania, ale nie są one wymagane.

1. Wybierz przycisk **OK** , aby wygenerować projekt i pliki źródłowe.

::: moniker-end
::: moniker range="msvc-150"

1. Na pasku menu wybierz pozycję **plik** > **Nowy** > **projekt**.

1. W oknie dialogowym **Nowy projekt** wybierz węzeł **zainstalowane** > **Visual C++** > **CLR** , a następnie wybierz szablon **aplikacja konsoli CLR** .

1. W polu **Nazwa** wprowadź unikatową nazwę aplikacji.

   Możesz określić inne ustawienia projektu i rozwiązania, ale nie są one wymagane.

1. Wybierz przycisk **OK** , aby wygenerować projekt i pliki źródłowe.

::: moniker-end
::: moniker range="msvc-160"

1. Na pasku menu wybierz pozycję **plik** > **Nowy** > **projekt**.

1. W oknie dialogowym **Utwórz nowy projekt** w polu wyszukiwania wprowadź ciąg "Konsola CLR". Wybierz szablon **aplikacja konsoli CLR (.NET Framework)** , a następnie wybierz przycisk **dalej**.

1. W polu **Nazwa** wprowadź unikatową nazwę aplikacji.

   Możesz określić inne ustawienia projektu i rozwiązania, ale nie są one wymagane.

1. Wybierz przycisk **Utwórz** , aby wygenerować projekt i pliki źródłowe.

::: moniker-end

## <a name="see-also"></a>Zobacz też

[Projekty CLR](../build/reference/files-created-for-clr-projects.md)

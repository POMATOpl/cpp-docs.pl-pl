---
title: Język C++ w programie Visual Studio
description: Dowiedz się, jak używać kompilatora języka Microsoft C/C++, edytora kodu i narzędzi pokrewnych w programie Visual Studio do tworzenia programów dla systemów Windows, Linux, Android i iOS.
ms.date: 11/05/2020
ms.technology: cpp-ide
helpviewer_keywords:
- Visual C++, home page
ms.openlocfilehash: 32d8f45c1ae0ffeabcfd7b22988f125b138c1f4d
ms.sourcegitcommit: 12eb6a824dd7187a065d44fceca4c410f58e121e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2020
ms.locfileid: "94334159"
---
# <a name="c-in-visual-studio"></a>Język C++ w programie Visual Studio

:::moniker range="msvc-160"

> [!NOTE]
> Ta dokumentacja dotycząca deweloperów ma zastosowanie do programu Visual Studio 2019. Aby wyświetlić dokumentację preferowanej wersji programu Visual Studio, użyj kontrolki selektora **wersji** . Znajduje się w górnej części spisu treści na tej stronie.
>
> Jeśli szukasz pakietu redystrybucyjnego Microsoft Visual C++ 2019, aby można było uruchomić program, przejdź na stronę [pobierania](https://visualstudio.microsoft.com/downloads/) witryny Microsoft Visual Studio. W obszarze **wszystkie pliki do pobrania** rozwiń sekcję **inne narzędzia, struktury i redystrybucyjne** . Wybierz architekturę docelową, a następnie wybierz przycisk **Pobierz** .
>
> W przypadku starszych pakietów redystrybucyjnych Otwórz stronę [starsze pliki do pobrania](https://visualstudio.microsoft.com/vs/older-downloads/) . Rozwiń sekcję **inne narzędzia, struktury i redystrybucyjne** . Znajdź wersję redystrybucyjną, którą chcesz pobrać, wybierz architekturę docelową, a następnie wybierz przycisk **Pobierz** .

:::moniker-end

:::moniker range="msvc-150"

> [!NOTE]
> Ta dokumentacja dotycząca deweloperów ma zastosowanie do programu Visual Studio 2017. Aby wyświetlić dokumentację preferowanej wersji programu Visual Studio, użyj kontrolki selektora **wersji** . Znajduje się w górnej części spisu treści na tej stronie.
>
> Jeśli szukasz Microsoft Visual C++ 2017 lub starszego pakietu redystrybucyjnego, aby można było uruchomić program, przejdź do strony [starsze pliki do pobrania](https://visualstudio.microsoft.com/vs/older-downloads/) w witrynie Microsoft Visual Studio. Rozwiń sekcję **inne narzędzia, struktury i redystrybucyjne** . Znajdź wersję redystrybucyjną, którą chcesz pobrać, wybierz architekturę docelową, a następnie wybierz przycisk **Pobierz** .

:::moniker-end

:::moniker range="msvc-140"

> [!NOTE]
> Ta dokumentacja dotycząca deweloperów ma zastosowanie do programu Visual Studio 2015. Aby wyświetlić dokumentację preferowanej wersji programu Visual Studio, użyj kontrolki selektora **wersji** . Znajduje się w górnej części spisu treści na tej stronie.
>
> Jeśli szukasz Microsoft Visual C++ 2015 lub starszego pakietu redystrybucyjnego, aby można było uruchomić program, przejdź do strony [starsze pliki do pobrania](https://visualstudio.microsoft.com/vs/older-downloads/) w witrynie Microsoft Visual Studio. Rozwiń sekcję **inne narzędzia, struktury i redystrybucyjne** . Znajdź wersję redystrybucyjną, którą chcesz pobrać, wybierz architekturę docelową, a następnie wybierz przycisk **Pobierz** .

:::moniker-end

Microsoft Visual C++ (MSVC) odnosi się do narzędzi deweloperskich i bibliotek języka C++, C i zestawu dostępnych w ramach programu Visual Studio w systemie Windows. Te narzędzia i biblioteki pozwalają tworzyć aplikacje platforma uniwersalna systemu Windows (platformy UWP), natywne aplikacje pulpitu i serwera systemu Windows, biblioteki i aplikacje dla wielu platform, które działają w systemach Windows, Linux, Android i iOS, a także zarządzane aplikacje i biblioteki korzystające z .NET Framework. Możesz użyć MSVC, aby napisać coś z prostych aplikacji konsolowych do najbardziej zaawansowanych i złożonych aplikacji dla komputerów z systemem Windows, ze sterowników urządzeń i składników systemu operacyjnego do gier wieloplatformowych dla urządzeń przenośnych oraz od najmniejszych urządzeń IoT do wieloserwerowych obliczeń o wysokiej wydajności w chmurze platformy Azure.

Program Visual Studio 2015, 2017 i 2019 można zainstalować obok siebie. Do edytowania i kompilowania programów przy użyciu zestawu narzędzi z programu Visual Studio 2017 (najnowsze 141) i Visual Studio 2015 (wersji 140) można użyć programu Visual Studio 2019 (zestawu narzędzi kompilatora v142) lub programu Visual Studio 2017 (najnowsze 141).

## <a name="whats-new-and-conformance-history"></a>Historia informacji o nowościach i zgodności

[Co nowego w języku C++ w programie Visual Studio](what-s-new-for-visual-cpp-in-visual-studio.md)\
Dowiedz się, co nowego w programie Visual Studio.

[Co nowego w języku C++ w programie Visual Studio 2003 do 2015](../porting/visual-cpp-what-s-new-2003-through-2015.md)\
Dowiedz się, co nowego w języku C++ dla każdej wersji programu Visual Studio od 2003 do 2015.

[Ulepszenia zgodności języka C++ w programie Visual Studio](cpp-conformance-improvements.md)\
Dowiedz się więcej na temat ulepszeń zgodności języka C++ w programie Visual Studio.

[Tabela zgodności języka Microsoft C++](visual-cpp-language-conformance.md)\
Lista Stanów zgodności według funkcji w kompilatorze języka MSVC C++.

[Historia zmian języka Microsoft C/C++ 2003-2015](../porting/visual-cpp-change-history-2003-2015.md)\
Dowiedz się więcej o istotnych zmianach w poprzednich wersjach.

## <a name="install-visual-studio-and-upgrade-from-earlier-versions"></a>Zainstaluj program Visual Studio i Uaktualnij go ze starszych wersji

[Zainstaluj obsługę języka C++ w programie Visual Studio](../build/vscpp-step-0-installation.md)\
Pobierz program Visual Studio i Zainstaluj zestaw narzędzi Microsoft C/C++.

[Przewodnik dotyczący przenoszenia i uaktualniania języka Microsoft C++](../porting/visual-cpp-porting-and-upgrading-guide.md)\
Wskazówki dotyczące przenoszenia kodu i uaktualniania projektów do programu Visual Studio 2015 lub nowszego, aby wykorzystać lepszą zgodność kompilatora ze standardem C++ oraz znacznie ulepszone czasy kompilacji i funkcje zabezpieczeń, takie jak Spectre.

[Narzędzia i funkcje języka C++ w wersjach programu Visual Studio](visual-cpp-tools-and-features-in-visual-studio-editions.md)\
Poznaj różne wersje Visual Studio.

[Obsługiwane platformy](supported-platforms-visual-cpp.md)\
Dowiedz się, które platformy obsługują kompilator Microsoft C/C++.

## <a name="learn-c"></a>Poznaj język C++

[Witamy ponownie w języku C++](../cpp/welcome-back-to-cpp-modern-cpp.md)\
Dowiedz się więcej o nowoczesnych technikach programowania C++ opartych na języku C++ 11 i nowszych, które umożliwiają pisanie szybkiego i bezpiecznego kodu oraz uniknięcie wielu pułapek programowania w stylu języka C.

[Standardowa C++](https://isocpp.org/)\
Dowiedz się o języku C++, uzyskaj omówienie nowoczesnego języka C++, znajdź łącza do książek, artykułów, rozmów i imprez

[Poznaj program Visual Studio i Utwórz pierwszy projekt w języku C++](../build/vscpp-step-1-create.md)\
Zacznij uczenie się, jak napisać C++ w programie Visual Studio.

[Visual Studio C++ — przykłady](visual-cpp-samples.md)\
Informacje o przykładach kodu C++ dostarczonych przez firmę Microsoft.

## <a name="c-development-tools"></a>Narzędzia programistyczne języka C++

[Omówienie programowania w języku C++ w programie Visual Studio](overview-of-cpp-development.md)\
Jak za pomocą środowiska IDE programu Visual Studio tworzyć projekty, edytować kod, łączyć się z bibliotekami, kompilować, debugować, tworzyć testy jednostkowe, przeprowadzać analizę statyczną, wdrażać i wykonywać inne czynności.

[Projekty i systemy kompilacji](../build/projects-and-build-systems-cpp.md)\
Jak tworzyć i konfigurować projekty programu Visual Studio C++, projekty CMake oraz inne rodzaje projektów z użyciem kompilatora MSVC i opcji konsolidatora.

[Pisanie i Refaktoryzacja kodu C++](../ide/writing-and-refactoring-code-cpp.md)\
Jak używać funkcji produktywności w edytorze języka C++ do refaktoryzacji, nawigowania, zrozumienia i pisania kodu.

[Debugowanie kodu natywnego](/visualstudio/debugger/debugging-native-code)\
Użyj debugera programu Visual Studio z projektami języka C++.

[Analiza kodu C/C++ — Omówienie](../code-quality/code-analysis-for-c-cpp-overview.md)\
Użyj adnotacji SAL lub podstawowe wytyczne dotyczące języka C++ych elementów sprawdzających, aby przeprowadzić analizę statyczną.

[Zapisz testy jednostkowe dla C/C++ w programie Visual Studio](/visualstudio/test/writing-unit-tests-for-c-cpp)\
Tworzenie testów jednostkowych przy użyciu platformy testów jednostkowych firmy Microsoft dla języka C++, Google Test, zwiększanie wydajności. test lub narzędzia ctest.

## <a name="write-applications-in-c"></a>Pisanie aplikacji w języku C++

[Aplikacje uniwersalne systemu Windows (C++)](../cppcx/universal-windows-apps-cpp.md)\
Znajdź przewodniki i treści referencyjne w Centrum deweloperów systemu Windows. Aby uzyskać informacje na temat tworzenia aplikacji platformy UWP, zobacz [wprowadzenie do platforma uniwersalna systemu Windows](/windows/uwp/get-started/universal-application-platform-guide) i [Tworzenie pierwszej aplikacji platformy UWP przy użyciu języka C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

[Aplikacje klasyczne (C++)](../windows/desktop-applications-visual-cpp.md)\
Dowiedz się, jak utworzyć tradycyjne natywne aplikacje klasyczne C++ dla systemu Windows.

[Programowanie na platformie .NET przy użyciu języka C++/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)\
Dowiedz się, jak tworzyć biblioteki DLL, które umożliwiają współdziałanie między natywnymi programami C++ i .NET zapisanymi w językach, takich jak C# lub Visual Basic.

[Programowanie dla systemu Linux](../linux/index.yml)\
Użyj środowiska IDE programu Visual Studio, aby wykonać kod i wdrożyć go na zdalnej maszynie z systemem Linux na potrzeby kompilacji za pomocą programu w zatoce.

[Tworzenie bibliotek DLL C/C++ w programie Visual Studio](../build/dlls-in-visual-cpp.md)\
Poznaj sposób używania Win32, ATL i MFC do tworzenia bibliotek DLL dla pulpitu systemu Windows, poznaj informacje o sposobach kompilowania i rejestrowania biblioteki DLL.

[Programowanie równoległe](../parallel/parallel-programming-in-visual-cpp.md)\
Dowiedz się, jak używać biblioteki wzorców równoległych, C++ AMP, OpenMP i innych funkcji, które są związane z wielowątkowością w systemie Windows.

[Najlepsze rozwiązania w zakresie zabezpieczeń](../security/security-best-practices-for-cpp.md)\
Dowiedz się, jak chronić aplikacje przed złośliwym kodem i bezprawnym użyciem.

[Programowanie w chmurze i sieci Web](../cloud/cloud-and-web-programming-in-visual-cpp.md)\
W języku C++ istnieje kilka opcji nawiązywania połączenia z siecią Web i chmurą.

[Dostęp do danych](../data/data-access-in-cpp.md)\
Połącz się z bazami danych za pomocą ODBC i OLE DB.

[Tekst i ciągi](../text/text-and-strings-in-visual-cpp.md)\
Dowiedz się więcej na temat pracy z różnymi formatami tekstu i ciągów oraz kodowaniem dla rozwoju lokalnego i międzynarodowego.

## <a name="languages-reference"></a>Dokumentacja języków

[Dokumentacja języka C++](../cpp/cpp-language-reference.md)\
Przewodnik referencyjny dotyczący implementacji języka programowania C++ firmy Microsoft.

[Dokumentacja preprocesora języka C/C++](../preprocessor/c-cpp-preprocessor-reference.md)\
Wspólne odwołanie do udostępnionego elementu preprocesora języka C i C++.

[Dokumentacja języka C](../c-language/c-language-reference.md)\
Przewodnik referencyjny dotyczący implementacji języka C przez firmę Microsoft.

[Funkcje wewnętrzne kompilatora i język asemblera](../intrinsics/compiler-intrinsics-and-assembly-language.md)\
Przewodniki dotyczące wewnętrznych elementów kompilatora obsługiwanych lub implementowanych przez kompilatory języka Microsoft C/C++ na każdej platformie.

## <a name="c-libraries-in-visual-studio"></a>Biblioteki C++ w programie Visual Studio

W poniższych sekcjach znajdują się informacje o różnych bibliotekach C i C++, które znajdują się w programie Visual Studio.

[Dokumentacja biblioteki środowiska uruchomieniowego języka C](../c-runtime-library/c-run-time-library-reference.md)\
Obejmuje alternatywy o zwiększonym bezpieczeństwie dla funkcji, które są znane ze stwarzania problemów dotyczących bezpieczeństwa.

[Standardowa biblioteka języka C++](../standard-library/cpp-standard-library-reference.md)\
Standardowa biblioteka języka C++.

[Active Template Library (ATL)](../atl/atl-com-desktop-components.md)\
Obsługa składników i aplikacji modelu COM.

[Biblioteki Microsoft Foundation Class (MFC)](../mfc/mfc-desktop-applications.md)\
Wsparcie dla tworzenia aplikacji pulpitu, mających interfejs użytkownika tradycyjny lub w stylu pakietu Office.

[Biblioteka równoległych wzorców (PPL)](../parallel/concrt/parallel-patterns-library-ppl.md)\
Algorytmy asynchroniczne i równoległe, wykonywane przez CPU.

[C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)\
Duże równoległe algorytmy, wykonywane przez GPU.

[Biblioteka szablonów środowisko wykonawcze systemu Windows (WRL)](../cppcx/wrl/windows-runtime-cpp-template-library-wrl.md)\
Aplikacje i składniki platforma uniwersalna systemu Windows (platformy UWP).

[Programowanie na platformie .NET przy użyciu języka C++/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)\
Programowanie dla wspólnego środowiska czasu wykonywania (common language runtime — CLR).

## <a name="third-party-open-source-c-libraries"></a>Biblioteki języka C++ Open Source innych firm

Międzyplatformowe narzędzie wiersza polecenia **vcpkg** znacznie upraszcza odnajdywanie i instalację bibliotek typu open source w języku 900 C++. Zobacz [vcpkg: Menedżer pakietów C++ dla systemu Windows](../build/vcpkg.md).

## <a name="feedback-and-community"></a>Opinie i społeczność

[Microsoft Docs Q&](/answers/topics/c%2B%2B.html)\
Microsoft Docs hostuje na forach z możliwością wyszukiwania pytania i odpowiedzi. Dodaj `C++` tag do wpisu na potrzeby pomocy społeczności w przypadku problemów związanych z językiem C++.

[Jak zgłosić problem z zestawem narzędzi Microsoft C/C++](how-to-report-a-problem-with-the-visual-cpp-toolset.md)\
Dowiedz się, jak tworzyć efektywne raporty o błędach względem zestawu narzędzi Microsoft C/C++ (kompilator, konsolidator i inne narzędzia) oraz jak przesłać raport.

[Blog zespołu Microsoft C++](https://devblogs.microsoft.com/cppblog/)\
Dowiedz się więcej na temat nowych funkcji i najnowszych informacji od deweloperów narzędzi C++ w programie Visual Studio.

[Społeczność deweloperów programu Visual Studio C++](https://aka.ms/vsfeedback/browsecpp)\
Uzyskaj pomoc, błędy plików i Utwórz sugestie dotyczące języka C++ w programie Visual Studio.

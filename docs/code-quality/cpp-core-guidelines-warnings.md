---
title: C++Ostrzeżenia dotyczące podstawowych wytycznych
ms.date: 10/16/2019
ms.topic: conceptual
ms.assetid: 7c83814a-f21d-4323-ad5f-13bac40d3e38
ms.openlocfilehash: f499374c84973be09e2f02e6d2f2e6d9a6548363
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77418831"
---
# <a name="using-the-c-core-guidelines-checkers"></a>Korzystanie z kontrolerów podstawowych wytycznych dotyczących języka C++

C++ Podstawowe wytyczne są przenośnym zestawem wytycznych, zasad i najlepszych rozwiązań dotyczących kodowania C++ utworzonego przez C++ ekspertów i projektantów. Program Visual Studio obecnie obsługuje podzbiór tych reguł w ramach narzędzi do analizy kodu dla programu C++. Główne wskazówki sprawdzające podstawowe są instalowane domyślnie w programie Visual Studio 2017 i Visual Studio 2019 i są [dostępne jako pakiet NuGet dla programu Visual studio 2015](#vs2015_corecheck).

## <a name="the-c-core-guidelines-project"></a>Projekt C++ podstawowych wytycznych

Podstawowe wytyczne są tworzone przez Bjarne'a Stroustrupa i C++ inne, ale w sposób C++ bezpieczny i efektywny. Wytyczne podkreślają bezpieczeństwo typu statycznego i bezpieczeństwo zasobów. Identyfikują one sposoby eliminacji lub minimalizowania najbardziej podatnych na błędy części języka, a także sugerują sposób prostszego i bardziej wydajnego wykonywania kodu. Te wytyczne są obsługiwane przez standardową C++ podstawę. Aby dowiedzieć się więcej, zobacz dokumentację, [ C++ podstawowe wytyczne](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)i dostęp do C++ plików projektu dokumentacji podstawowych wytycznych w serwisie [GitHub](https://github.com/isocpp/CppCoreGuidelines).

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>Włącz C++ podstawowe wskazówki dotyczące sprawdzania w analizie kodu

Możesz włączyć analizę kodu w projekcie, zaznaczając pole wyboru **Włącz analizę kodu podczas kompilacji** w sekcji **Analiza kodu** okna dialogowego **strony właściwości** dla projektu.

![Strona właściwości dla ustawień ogólnych analizy kodu](../code-quality/media/cppcorecheck_codeanalysis_general.png)

C++ Podstawowe reguły sprawdzania są rozszerzeniami domyślnych zestawów reguł, które są uruchamiane po włączeniu analizy kodu. Ponieważ C++ podstawowe reguły sprawdzania są opracowywane, niektóre reguły są dobrze ustanowione, a niektóre z nich mogą nie być gotowe do użycia na całym kodzie, ale mogą być nadal niesformatowane. Reguły są podzielone na dwie grupy: wydane i eksperymentalne. Możesz wybrać, czy mają być uruchamiane reguły wydane lub eksperymentalne we właściwościach projektu.

![Strona właściwości dla ustawień rozszerzeń analizy kodu](../code-quality/media/cppcorecheck_codeanalysis_extensions.png)

Aby włączyć lub wyłączyć zestawy C++ reguł sprawdzania podstawowe, Otwórz okno dialogowe **strony właściwości** dla projektu. W obszarze **Właściwości konfiguracji**rozwiń węzeł **Analiza kodu**, **rozszerzenia**. W kontrolce listy rozwijanej **obok C++ pozycji Włącz sprawdzanie podstawowe (wydano)** lub **Włącz C++ sprawdzanie podstawowe (eksperymentalne)** wybierz opcję **tak** lub **nie**. Wybierz **przycisk OK** lub **Zastosuj** , aby zapisać zmiany.

## <a name="examples"></a>Przykłady

Oto przykład niektórych problemów, które mogą znaleźć C++ podstawowe reguły sprawdzania:

```cpp
// CoreCheckExample.cpp
// Add CppCoreCheck package and enable code analysis in build for warnings.

int main()
{
    int arr[10];           // warning C26494
    int* p = arr;          // warning C26485

    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
    {
        int* q = p + 1;    // warning C26481 (suppressed)
        p = q++;           // warning C26481 (suppressed)
    }

    return 0;
}
```

Ten przykład ilustruje kilka ostrzeżeń, które mogą znaleźć C++ podstawowe reguły sprawdzania:

- C26494 jest typem reguły. 5: zawsze Inicjuj obiekt.

- C26485 jest zakresem reguł. 3: brak zanikania tablicy do wskaźnika.

- C26481 jest zakresem reguł. 1: nie używaj arytmetyki wskaźnika. Zamiast tego użyj polecenia cmdlet `span`.

Jeśli C++ podstawowe zestaw reguł analizy kodu są instalowane i włączane podczas kompilowania tego kodu, pierwsze dwa ostrzeżenia są wyjściowe, ale trzeci jest pomijany. Oto dane wyjściowe kompilacji z przykładowego kodu:

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C++ Podstawowe wskazówki ułatwiają pisanie lepszych i bezpieczniejszych kodów. Jeśli jednak istnieje wystąpienie, w którym nie należy stosować reguły lub profilu, można je łatwo pominąć bezpośrednio w kodzie. Można użyć atrybutu `gsl::suppress`, aby zachować C++ podstawowe sprawdzenie w wykrywaniu i raportowaniu naruszeń reguły w poniższym bloku kodu. Można oznaczyć poszczególne instrukcje, aby pominąć określone reguły. Można nawet pominąć profil całego ograniczenia, pisząc `[[gsl::suppress(bounds)]]` bez uwzględniania określonego numeru reguły.

## <a name="supported-rule-sets"></a>Obsługiwane zestawy reguł

W miarę dodawania nowych reguł do narzędzia C++ sprawdzania podstawowych wytycznych liczba ostrzeżeń, które są generowane dla istniejącego kodu, może się zwiększyć. Wstępnie zdefiniowanych zestawów reguł można użyć do filtrowania typów reguł do włączenia. W programie Visual Studio 2017 w wersji 15,3 obsługiwane są następujące zestawy reguł:

- **Reguły wskaźnika właściciela** wymuszają [operacje sprawdzania zarządzania zasobami powiązane z właścicielami\<t > C++ z podstawowych wytycznych](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

- **Reguły const** wymuszają [kontrole związane z wartością stałą C++ z podstawowych wytycznych](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability).

- **Reguły wskaźnika RAW** wymuszają [operacje sprawdzania zarządzania zasobami powiązane ze wskaźnikami nieprzetworzonymi z C++ podstawowych wskazówek](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

- **Reguły unikatowego wskaźnika** wymuszają [operacje sprawdzania zarządzania zasobami powiązane z typami z semantyką unikatowego C++ wskaźnika z podstawowych wytycznych](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management).

- **Reguły związane z ograniczeniami** wymuszają [profil ograniczenia C++ podstawowych wytycznych](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile).

- **Reguły typu** wymuszają [Profil typu C++ podstawowych wytycznych](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile).

Można wybrać ograniczenie ostrzeżeń tylko do jednej lub kilku grup. **Natywne minimalne** i **natywne zalecane** zestawy reguł C++ obejmują podstawowe reguły sprawdzania, a także inne szybkie testy. Aby wyświetlić dostępne zestawy reguł, Otwórz okno dialogowe właściwości projektu, wybierz pozycję **kod Analysis\General**, Otwórz listę rozwijaną w polu kombi **zestawy reguł** i wybierz **pozycję zaznacz wiele zestawów reguł**. Aby uzyskać więcej informacji o korzystaniu z zestawów reguł w programie Visual Studio, zobacz [używanie zestawów C++ reguł do określania reguł do uruchomienia](using-rule-sets-to-specify-the-cpp-rules-to-run.md) i [używania zestawów reguł do grupowania reguł analizy kodu](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules).

## <a name="macros"></a>Makra

Narzędzie C++ sprawdzania podstawowych wytycznych zawiera plik nagłówka definiujący makra, które ułatwiają pomijanie wszystkich kategorii ostrzeżeń w kodzie:

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

Te makra odpowiadają zestawom reguł i rozszerzają je na listę rozdzielonych spacjami. Za pomocą odpowiednich konstrukcji dyrektywy pragma można skonfigurować obowiązujący zestaw reguł, który jest interesujący dla projektu lub sekcji kodu. W poniższym przykładzie Analiza kodu będzie ostrzegał tylko o brakujących modyfikatorach stałych:

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>Atrybuty

Kompilator firmy C++ Microsoft ma ograniczoną obsługę atrybutu pomijania GSL. Może służyć do pomijania ostrzeżeń dotyczących wyrażeń i bloków instrukcji wewnątrz funkcji.

```cpp
// Suppress only warnings from the 'r.11' rule in expression.
[[gsl::suppress(r.11)]] new int;

// Suppress all warnings from the 'r' rule group (resource management) in block.
[[gsl::suppress(r)]]
{
    new int;
}

// Suppress only one specific warning number.
// For declarations, you may need to use the surrounding block.
// Macros are not expanded inside of attributes.
// Use plain numbers instead of macros from the warnings.h.
[[gsl::suppress(26400)]]
{
    int *p = new int;
}
```

## <a name="suppressing-analysis-by-using-command-line-options"></a>Pomijanie analizy przy użyciu opcji wiersza polecenia

Zamiast #pragmas można użyć opcji wiersza polecenia na stronie właściwości pliku, aby pominąć ostrzeżenia dla projektu lub pojedynczego pliku. Na przykład, aby wyłączyć C26400 ostrzegawczy dla pliku:

1. Kliknij prawym przyciskiem myszy plik w **Eksplorator rozwiązań**

1. Wybierz **właściwości | C/C++| Wiersz polecenia**

1. W oknie **Opcje dodatkowe** Dodaj `/wd26400`.

Za pomocą opcji wiersza polecenia można tymczasowo wyłączyć wszystkie analizy kodu dla pliku, określając `/analyze-`. Spowoduje to wygenerowanie ostrzeżenia *D9025 przesłanianie "/ANALYZE" z "/ANALYZE-"* , który będzie przypominać później ponownie włączyć analizę kodu.

## <a name="corecheck_per_file"></a>Włączanie sprawdzania C++ podstawowych wytycznych dla określonych plików projektu

Czasami warto rozważyć skoncentrowaną analizę kodu i nadal korzystać z programu Visual Studio IDE. Poniżej znajduje się przykładowy scenariusz, który może być używany w dużych projektach do zapisywania czasu kompilacji i ułatwiający filtrowanie wyników.

1. W powłoce poleceń Ustaw zmienne środowiskowe `esp.extension` i `esp.annotationbuildlevel`.
1. Otwórz program Visual Studio z powłoki poleceń, aby odziedziczyć te zmienne.
1. Załaduj projekt i otwórz jego właściwości.
1. Włącz analizę kodu, wybierz odpowiednie zestawy reguł, ale nie włączaj rozszerzeń analizy kodu.
1. Przejdź do pliku, który chcesz analizować, za pomocą C++ narzędzia sprawdzania podstawowych wytycznych i otwórz jego właściwości.
1. Wybierz **Opcje liniiC++C/\Command** i Dodaj `/analyze:plugin EspXEngine.dll`
1. Wyłącz używanie prekompilowanego nagłówka (**nagłówki C/C++\Precompiled**). Jest to konieczne, ponieważ aparat rozszerzeń może próbować odczytać swoje wewnętrzne informacje z prekompilowanego nagłówka i, jeśli został on skompilowany przy użyciu domyślnych opcji projektu, nie będzie zgodny.
1. Ponownie skompiluj projekt. Wspólne testy szybkie są uruchamiane na wszystkich plikach. Ponieważ narzędzie C++ sprawdzania podstawowych wytycznych nie jest domyślnie włączone, powinno być uruchamiane tylko na pliku, który jest skonfigurowany do korzystania z niego.

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>Jak używać narzędzia sprawdzania C++ podstawowych wytycznych poza programem Visual Studio

W przypadku zautomatyzowanych C++ kompilacji można użyć testów podstawowych wytycznych.

### <a name="msbuild"></a>MSBuild

Narzędzie sprawdzania kodu natywnego (wstępnie Fast) jest zintegrowane ze środowiskiem MSBuild przez pliki niestandardowych elementów docelowych. Możesz użyć właściwości projektu, aby je włączyć, i dodać C++ najważniejsze wskazówki (które są oparte na szybkim przełożeniu):

```xml
<PropertyGroup>
  <EnableCppCoreCheck>true</EnableCppCoreCheck>
  <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>
  <RunCodeAnalysis>true</RunCodeAnalysis>
</PropertyGroup>
```

Przed zaimportowaniem pliku Microsoft. cpp. targets należy dodać te właściwości. Można wybrać konkretne zestawy reguł lub utworzyć niestandardowy zestaw reguł lub użyć domyślnego zestawu reguł, który zawiera inne szybkie testy.

Program C++ Core Checker można uruchomić tylko dla określonych plików, korzystając z tego samego podejścia jak [opisane wcześniej](#corecheck_per_file), ale przy użyciu plików programu MSBuild. Zmienne środowiskowe można ustawić za pomocą elementu `BuildMacro`:

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <ValueCppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

Jeśli nie chcesz modyfikować pliku projektu, możesz przekazać właściwości w wierszu polecenia:

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>Projekty inne niż MSBuild

W przypadku korzystania z systemu kompilacji, który nie korzysta z programu MSBuild, można nadal uruchomić moduł sprawdzania, ale należy zapoznać się z niektórymi wewnętrznymi konfiguracją aparatu analizy kodu (nie jest to obsługiwane w przyszłości).

Należy ustawić kilka zmiennych środowiskowych i użyć odpowiednich opcji wiersza polecenia dla kompilatora. Lepiej jest używać środowiska "natywnych narzędzi wiersza polecenia", dzięki czemu nie trzeba wyszukiwać określonych ścieżek dla kompilatora, zawierać katalogów itp.

1. **Zmienne środowiskowe**
   - `set esp.extensions=cppcorecheck.dll` to nakazuje aparatowi załadowanie C++ modułu podstawowych wytycznych.
   - `set esp.annotationbuildlevel=ignore` spowoduje to wyłączenie logiki, która przetwarza adnotacje SAL. Adnotacje nie wpływają na analizę kodu C++ w ramach sprawdzania podstawowych wytycznych, ale czas ich przetwarzania (czasami jest to czasochłonne). To ustawienie jest opcjonalne, ale zdecydowanie zalecane.
   - `set caexcludepath=%include%` zdecydowanie zalecamy wyłączenie ostrzeżeń, które są uruchamiane w standardowych nagłówkach. W tym miejscu możesz dodać więcej ścieżek, na przykład ścieżkę do wspólnych nagłówków w projekcie.
1. **Opcje wiersza polecenia**
   - `/analyze` włącza analizę kodu (należy rozważyć także użycie/analyze: Only i/analyze: Quiet).
   - `/analyze:plugin EspXEngine.dll` ta opcja ładuje aparat rozszerzeń analizy kodu do przodu. Ten aparat, z kolei, ładuje C++ najważniejsze wskazówki.

## <a name="use-the-guideline-support-library"></a>Korzystanie z biblioteki podstawowej pomocy technicznej

Podstawowa Biblioteka pomocy technicznej została zaprojektowana w celu ułatwienia przestrzegania podstawowych wytycznych. GSL zawiera definicje, które umożliwiają zamianę konstrukcji podatnych na błędy z bezpieczniejszymi alternatywami. Na przykład można zastąpić `T*, length` parę parametrów `span<T>` typem. GSL jest dostępny w [http://www.nuget.org/packages/Microsoft.Gsl](https://www.nuget.org/packages/Microsoft.Gsl). Biblioteka jest open source, dzięki czemu można przeglądać źródła, wprowadzać komentarze lub współtworzyć. Projekt można znaleźć w [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL).

## <a name="vs2015_corecheck"></a>Korzystanie z C++ podstawowych wskazówek dotyczących sprawdzania w projektach programu Visual Studio 2015

W przypadku korzystania z C++ programu Visual Studio 2015 zestawy reguł analizy kodu podstawowego nie są instalowane domyślnie. Należy wykonać kilka dodatkowych kroków, aby można było włączyć podstawowe C++ narzędzia do analizy kodu w programie Visual Studio 2015. Firma Microsoft zapewnia pomoc techniczną dla projektów programu Visual Studio 2015 przy użyciu pakietu NuGet. Pakiet ma nazwę Microsoft. CppCoreCheck i jest dostępny w [http://www.nuget.org/packages/Microsoft.CppCoreCheck](https://www.nuget.org/packages/Microsoft.CppCoreCheck). Ten pakiet wymaga co najmniej programu Visual Studio 2015 z aktualizacją Update 1.

Pakiet instaluje również inny pakiet jako zależność, tylko w przypadku podstawowej biblioteki obsługi (GSL). GSL jest również dostępna w witrynie GitHub w [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL).

Ze względu na sposób ładowania reguł analizy kodu należy zainstalować pakiet NuGet Microsoft. CppCoreCheck w każdym C++ projekcie, który ma być sprawdzany w programie Visual Studio 2015.

### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Aby dodać pakiet Microsoft. CppCoreCheck do projektu w programie Visual Studio 2015

1. W **Eksplorator rozwiązań**kliknij prawym przyciskiem myszy, aby otworzyć menu kontekstowe projektu w rozwiązaniu, do którego chcesz dodać pakiet. Wybierz pozycję **Zarządzaj pakietami NuGet** , aby otworzyć **Menedżera pakietów NuGet**.

1. W oknie **Menedżer pakietów NuGet** Wyszukaj ciąg Microsoft. CppCoreCheck.

    ![Okno Menedżera pakietów NuGet zawiera pakiet CppCoreCheck](../code-quality/media/cppcorecheck_nuget_window.png)

1. Wybierz pakiet Microsoft. CppCoreCheck, a następnie wybierz przycisk **Instaluj** , aby dodać reguły do projektu.

   Pakiet NuGet dodaje do projektu dodatkowy plik MSBuild. targets, który jest wywoływany po włączeniu analizy kodu dla projektu. Ten plik targets dodaje C++ podstawowe reguły sprawdzania jako dodatkowe rozszerzenie narzędzia do analizy kodu programu Visual Studio. Po zainstalowaniu pakietu można użyć okna dialogowego strony właściwości, aby włączyć lub wyłączyć reguły wydane i eksperymentalne.

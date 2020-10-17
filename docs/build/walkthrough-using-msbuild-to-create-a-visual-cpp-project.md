---
title: 'Przewodnik: Tworzenie projektu Visual Studio C++ przy użyciu programu MSBuild'
description: Przewodnik przedstawiający sposób tworzenia projektu programu MSBuild C++. vcxproj w wierszu polecenia od podstaw.
ms.date: 10/08/2020
helpviewer_keywords:
- 'MSBuild (C++), walkthrough: create a project'
ms.openlocfilehash: 4f17cd8c4f5f48d8be5cd7cb25940db87029e111
ms.sourcegitcommit: 6e5429e076e552b32e8bdc49480c51498d7924c1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2020
ms.locfileid: "92099735"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>Wskazówki: Korzystanie z MSBuild do tworzenia projektu Visual C++

W tym instruktażu pokazano, jak za pomocą programu MSBuild w wierszu polecenia utworzyć projekt Visual Studio C++. Dowiesz się, jak utworzyć plik projektu oparty na języku XML *`.vcxproj`* dla Visual C++ aplikacji konsolowej. Po skompilowaniu projektu dowiesz się, jak dostosować proces kompilacji.

> [!IMPORTANT]
> Nie należy używać tej metody, jeśli zamierzasz edytować plik projektu później za pomocą środowiska IDE programu Visual Studio. Jeśli utworzysz *`.vcxproj`* plik ręcznie, środowisko IDE programu Visual Studio może nie być w stanie go edytować ani ładować, zwłaszcza jeśli projekt używa symboli wieloznacznych w elementach projektu. Aby uzyskać więcej informacji, zobacz [ `.vcxproj` i `.props` Struktura pliku](./reference/vcxproj-file-structure.md) oraz [ `.vcxproj` pliki i symbole wieloznaczne](./reference/vcxproj-files-and-wildcards.md).

Ten Instruktaż ilustruje następujące zadania:

- Tworzenie plików źródłowych języka C++ dla projektu.

- Tworzenie pliku projektu MSBuild języka XML.

- Kompilowanie projektu przy użyciu programu MSBuild.

- Dostosowywanie projektu przy użyciu programu MSBuild.

## <a name="prerequisites"></a>Wymagania wstępne

Te wymagania wstępne są wymagane do wykonania tego przewodnika:

- Kopia programu Visual Studio z zainstalowaną funkcją **tworzenia aplikacji klasycznych w języku C++** .

- Ogólna znajomość systemu MSBuild.

::: moniker range="vs-2015"

> [!NOTE]
> Większość instrukcji kompilacji niskiego poziomu znajduje się w *`.targets`* plikach i, *`.props`* które są zdefiniowane w folderze default targets, przechowywane we właściwości `$(VCTargetsPath)` . Jest to miejsce, w którym znajdują się pliki, takie jak *`Microsoft.Cpp.Common.props`* . Domyślną ścieżką dla tych plików w programie Visual Studio 2015 i starszych wersjach jest poniżej *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\`* .

::: moniker-end

::: moniker range="vs-2017"

> [!NOTE]
> Większość instrukcji kompilacji niskiego poziomu znajduje się w *`.targets`* plikach i, *`.props`* które są zdefiniowane w folderze default targets, przechowywane we właściwości `$(VCTargetsPath)` . Jest to miejsce, w którym znajdują się pliki, takie jak *`Microsoft.Cpp.Common.props`* . Domyślną ścieżką dla tych plików w programie Visual Studio 2017 jest poniżej *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`* . Program Visual Studio 2015 i jego wersje zostały zapisane w ramach programu *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\`* .

::: moniker-end

::: moniker range=">=vs-2019"

> [!NOTE]
> Większość instrukcji kompilacji niskiego poziomu znajduje się w *`.targets`* plikach i, *`.props`* które są zdefiniowane w folderze default targets, przechowywane we właściwości `$(VCTargetsPath)` . Jest to miejsce, w którym znajdują się pliki, takie jak *`Microsoft.Cpp.Common.props`* . Domyślną ścieżką dla tych plików jest *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\`* . `<version>`Element Path jest specyficzny dla wersji programu Visual Studio. Jest to *`v160`* program Visual Studio 2019. Program Visual Studio 2017 zaprzechowywał te pliki w folderze *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`* . Program Visual Studio 2015 i jego wersje zostały zapisane w ramach programu *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\`* .

::: moniker-end

## <a name="create-the-c-source-files"></a>Tworzenie plików źródłowych języka C++

W tym instruktażu utworzysz projekt, który zawiera plik źródłowy i plik nagłówkowy. Plik źródłowy *`main.cpp`* zawiera `main` funkcję dla aplikacji konsolowej. Plik nagłówkowy *`main.h`* zawiera kod do uwzględnienia *`<iostream>`* pliku nagłówkowego. Te pliki C++ można utworzyć przy użyciu programu Visual Studio lub edytora tekstu, takiego jak Visual Studio Code.

### <a name="to-create-the-c-source-files-for-your-project"></a>Aby utworzyć pliki źródłowe języka C++ dla projektu

1. Utwórz folder dla projektu.

1. Utwórz plik o nazwie *`main.cpp`* i Dodaj następujący kod do pliku:

    ```cpp
    // main.cpp : the application source code.
    #include <iostream>
    #include "main.h"
    int main()
    {
       std::cout << "Hello, from MSBuild!\n";
       return 0;
    }
    ```

1. Utwórz plik o nazwie *`main.h`* i Dodaj następujący kod do pliku:

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>Tworzenie pliku projektu MSBuild XML

Plik projektu MSBuild to plik XML, który zawiera element główny projektu ( `<Project>` ). W przykładowym projekcie, który utworzysz, `<Project>` element zawiera siedem elementów podrzędnych:

- Trzy Tagi grupy elementów ( `<ItemGroup>` ), które określają konfigurację projektu i platformę, nazwę pliku źródłowego i nazwę pliku nagłówkowego.

- Trzy znaczniki importu ( `<Import>` ) określające lokalizację Microsoft Visual C++ ustawień.

- Tag grupy właściwości ( `<PropertyGroup>` ), który określa ustawienia projektu.

### <a name="to-create-the-msbuild-project-file"></a>Aby utworzyć plik projektu MSBuild

1. Użyj edytora tekstów, aby utworzyć plik projektu o nazwie *`myproject.vcxproj`* , a następnie Dodaj `<Project>` element główny pokazywany w tym miejscu. (Użyj `ToolsVersion="14.0"` , jeśli używasz programu Visual studio 2015, `ToolsVersion="15.0"` Jeśli używasz programu visual Studio 2017 lub jeśli używasz programu `ToolsVersion="16.0"` Visual Studio 2019).

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

   Wstaw elementy w następnym kroku procedury między tagami głównymi `<Project>` .

1. Dodaj te dwa `<ProjectConfiguration>` elementy podrzędne w `<ItemGroup>` elemencie. Element podrzędny określa konfiguracje debugowania i wydania dla 32-bitowego systemu operacyjnego Windows:

    ```xml
    <ItemGroup>
      <ProjectConfiguration Include="Debug|Win32">
        <Configuration>Debug</Configuration>
        <Platform>Win32</Platform>
      </ProjectConfiguration>
      <ProjectConfiguration Include="Release|Win32">
        <Configuration>Release</Configuration>
        <Platform>Win32</Platform>
      </ProjectConfiguration>
    </ItemGroup>
    ```

1. Dodaj `<Import>` element, który określa ścieżkę domyślnych ustawień języka C++ dla tego projektu:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

1. Dodaj element grupy właściwości ( `<PropertyGroup>` ), który określa dwie właściwości projektu `<ConfigurationType>` i `<PlatformToolset>` . (Użyj `v140` jako `<PlatformToolset>` wartości, jeśli używasz programu visual Studio 2015, jeśli używasz programu `v141` Visual Studio 2017 lub jeśli używasz programu `v142` Visual Studio 2019).

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v142</PlatformToolset>
    </PropertyGroup>
    ```

1. Dodaj `<Import>` element, który określa ścieżkę bieżących ustawień języka C++ dla tego projektu:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

1. Dodaj `<ClCompile>` element podrzędny w `<ItemGroup>` elemencie. Element podrzędny określa nazwę pliku źródłowego C/C++ do skompilowania:

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > `<ClCompile>` jest *elementem docelowym kompilacji* i jest zdefiniowany w domyślnym folderze targets.

1. Dodaj `<ClInclude>` element podrzędny w `<ItemGroup>` elemencie. Element podrzędny określa nazwę pliku nagłówkowego dla pliku źródłowego C/C++:

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

1. Dodaj `<Import>` element, który określa ścieżkę pliku, który definiuje element docelowy dla tego projektu:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>Ukończ plik projektu

Ten kod pokazuje kompletny plik projektu, który został utworzony w poprzedniej procedurze. (Użyj `ToolsVersion="15.0"` dla programu Visual studio 2017 lub `ToolsVersion="14.0"` dla programu visual Studio 2015).

```xml
<Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup>
    <ProjectConfiguration Include="Debug|Win32">
      <Configuration>Debug</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
    <ProjectConfiguration Include="Release|Win32">
      <Configuration>Release</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
  <PropertyGroup>
    <ConfigurationType>Application</ConfigurationType>
    <PlatformToolset>v142</PlatformToolset>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ItemGroup>
    <ClCompile Include="main.cpp" />
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="main.h" />
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
</Project>
```

## <a name="using-msbuild-to-build-your-project"></a>Kompilowanie projektu przy użyciu programu MSBuild

Wprowadź to polecenie w wierszu polecenia, aby skompilować aplikację konsolową:

> `msbuild myproject.vcxproj /p:configuration=debug`

Program MSBuild tworzy folder dla plików wyjściowych, a następnie kompiluje i łączy projekt w celu wygenerowania *`Myproject.exe`* programu. Po zakończeniu procesu kompilacji Użyj tego polecenia, aby uruchomić aplikację z folderu debugowania:

> `myproject`

Aplikacja powinna wyświetlać "Hello, z MSBuild!" w oknie konsoli.

## <a name="customizing-your-project"></a>Dostosowywanie projektu

Program MSBuild umożliwia wykonywanie wstępnie zdefiniowanych celów kompilacji, stosowanie właściwości zdefiniowanych przez użytkownika i używanie niestandardowych narzędzi, zdarzeń i kroków kompilacji. W tej sekcji przedstawiono następujące zadania:

- Korzystanie z programu MSBuild z obiektami docelowymi kompilacji.

- Korzystanie z programu MSBuild z właściwościami kompilacji.

- Korzystanie z programu MSBuild z 64-bitowym kompilatorem i narzędziami.

- Korzystanie z programu MSBuild z różnymi zestawami narzędzi.

- Dodawanie dostosowań MSBuild.

### <a name="using-msbuild-with-build-targets"></a>Korzystanie z programu MSBuild z obiektami docelowymi kompilacji

*Element docelowy kompilacji* to nazwany zestaw wstępnie zdefiniowanych lub zdefiniowanych przez użytkownika poleceń, które mogą być wykonywane podczas kompilacji. Aby określić cel kompilacji, użyj docelowej opcji wiersza polecenia ( **`/t`** ). Dla `myproject` przykładowego projektu wstępnie zdefiniowany **`clean`** element docelowy usuwa wszystkie pliki w folderze debugowania i tworzy nowy plik dziennika.

W wierszu polecenia wprowadź następujące polecenie, aby wyczyścić `myproject` :

> `msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>Korzystanie z programu MSBuild z właściwościami kompilacji

Opcja wiersza polecenia właściwości ( `/p` ) umożliwia przesłonięcie właściwości w pliku kompilacji projektu. W `myproject` przykładzie projekt konfiguracja kompilacji wersji lub debugowania jest określona przez `Configuration` Właściwość. System operacyjny, który będzie używany do uruchamiania skompilowanej aplikacji, jest określony przez `Platform` Właściwość.

W wierszu polecenia wprowadź następujące polecenie, aby utworzyć kompilację debugowania `myproject` aplikacji do uruchamiania w 32-bitowym systemie Windows:

> `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

Załóżmy, że `myproject` przykładowy projekt definiuje również konfigurację dla 64-bitowego systemu Windows i inną konfigurację dla niestandardowego systemu operacyjnego o nazwie `myplatform` .

W wierszu polecenia wprowadź następujące polecenie, aby utworzyć kompilację wydania działającą w 64-bitowym systemie Windows:

> `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

W wierszu polecenia wprowadź następujące polecenie, aby utworzyć kompilację wydania dla `myplatform` :

> `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>Korzystanie z programu MSBuild z 64-bitowym kompilatorem i narzędziami

Jeśli zainstalowano program Visual Studio w systemie 64-bitowym, domyślnie instalowane są narzędzia 64-bit x64 Native i Cross. Program MSBuild można skonfigurować tak, aby korzystał z kompilatora 64-bitowego oraz narzędzi do kompilowania aplikacji przez ustawienie `PreferredToolArchitecture` właściwości. Ta właściwość nie ma wpływu na właściwości konfiguracji projektu ani platformy. Domyślnie używana jest 32-bitowa wersja narzędzi. Aby określić 64-bitową wersję kompilatora i narzędzi, Dodaj ten element grupy właściwości do *`Myproject.vcxproj`* pliku projektu po *`Microsoft.Cpp.default.props`* `<Import />` elemencie pliku:

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

W wierszu polecenia wprowadź następujące polecenie, aby użyć narzędzi 64-bitowych do kompilowania aplikacji:

> `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>Korzystanie z programu MSBuild z innym zestawem narzędzi

Jeśli masz zestawy narzędzi i biblioteki dla innych wersji Visual C++ zainstalowanych, MSBuild może kompilować aplikacje dla bieżącej wersji Visual C++ lub dla innych zainstalowanych wersji. Na przykład jeśli zainstalowano program Visual Studio 2012, aby określić zestaw narzędzi Visual C++ 11,0 dla systemu Windows XP, Dodaj ten element grupy właściwości do *`Myproject.vcxproj`* pliku projektu po *`Microsoft.Cpp.props`* elemencie pliku `<Import />` :

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Aby ponownie skompilować projekt przy użyciu zestawu narzędzi Visual C++ 11,0 systemu Windows XP, wprowadź następujące polecenie:

> `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

### <a name="adding-msbuild-customizations"></a>Dodawanie dostosowań MSBuild

Program MSBuild oferuje różne sposoby dostosowywania procesu kompilacji. W tych artykułach pokazano, jak dodać niestandardowe kroki kompilacji, narzędzia i zdarzenia do projektu MSBuild:

- [Instrukcje: Dodawanie niestandardowego kroku kompilacji do projektów MSBuild](how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [Instrukcje: Dodawanie niestandardowych narzędzi kompilacji do projektów MSBuild](how-to-add-custom-build-tools-to-msbuild-projects.md)

- [Instrukcje: korzystanie ze zdarzeń kompilacji w projektach MSBuild](how-to-use-build-events-in-msbuild-projects.md)

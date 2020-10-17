---
title: Elementy wewnętrzne programu MSBuild dla projektów C++ w programie Visual Studio
description: Pliki, właściwości i obiekty docelowe, które są używane przez program MSBuild dla projektów Visual Studio C++.
ms.date: 10/14/2020
helpviewer_keywords:
- MSBuild overview
ms.openlocfilehash: b08db751bfe04c7cd3ce2c2f4741c9ee8956cf74
ms.sourcegitcommit: 6e5429e076e552b32e8bdc49480c51498d7924c1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2020
ms.locfileid: "92099683"
---
# <a name="msbuild-internals-for-c-projects"></a>Funkcje wewnętrzne aparatu MSBuild dla projektów w języku C++

Po ustawieniu właściwości projektu w IDE, a następnie zapisaniu projektu, program Visual Studio zapisuje ustawienia projektu w pliku projektu. Plik projektu zawiera ustawienia, które są unikatowe dla Twojego projektu. Nie zawiera on jednak wszystkich ustawień wymaganych do skompilowania projektu. Plik projektu zawiera `Import` elementy, które zawierają sieć dodatkowych *plików pomocniczych.* Pliki obsługi zawierają pozostałe właściwości, obiekty docelowe i ustawienia wymagane do skompilowania projektu.

Większość elementów docelowych i właściwości w plikach obsługi istnieje wyłącznie do wdrożenia systemu kompilacji. W tym artykule omówiono przydatne elementy docelowe i właściwości, które można określić w wierszu polecenia programu MSBuild. Aby odnaleźć więcej obiektów docelowych i właściwości, Przejrzyj pliki w katalogach plików pomocy technicznej.

## <a name="support-file-directories"></a>Obsługa katalogów plików

Domyślnie podstawowe pliki obsługi programu Visual Studio znajdują się w następujących katalogach. Te informacje są specyficzne dla wersji.

::: moniker range=">=vs-2019"

### <a name="visual-studio-2019"></a>Visual Studio 2019

- *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\`*

  Zawiera pliki głównych plików docelowych (. targets) i pliki właściwości (. props), które są używane przez obiekty docelowe. Domyślnie makro $ (VCTargetsPath) odwołuje się do tego katalogu. *`<version>`* Symbol zastępczy odwołuje się do programu Visual Studio Version: V160 for Visual studio 2019, V150 for Visual studio 2017.

- *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\Platforms\<platform>\`*

  Zawiera pliki docelowe i właściwości specyficzne dla platformy, które zastępują elementy docelowe i właściwości w katalogu nadrzędnym. Ten katalog zawiera również bibliotekę DLL, która definiuje zadania, które są używane przez obiekty docelowe w tym katalogu. *`<platform>`* Symbol zastępczy reprezentuje PODKATALOG ARM, arm64, Win32 lub x64.

- *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  Zawiera katalogi, które umożliwiają kompilacji generowanie aplikacji C++ przy użyciu określonego *`<toolset>`* . *`<platform>`* Symbol zastępczy reprezentuje PODKATALOG ARM, arm64, Win32 lub x64. *`<toolset>`* Symbol zastępczy reprezentuje podkatalog zestawu narzędzi.

::: moniker-end

::: moniker range=">=vs-2017"

### <a name="visual-studio-2017"></a>Visual Studio 2017

- *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`*

  Zawiera podstawowe pliki docelowe ( *`.targets`* ) i pliki właściwości ( *`.props`* ), które są używane przez obiekty docelowe. Domyślnie `$(VCTargetsPath)` makro odwołuje się do tego katalogu.

- *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\Platforms\<platform>\`*

  Zawiera pliki docelowe i właściwości specyficzne dla platformy, które zastępują elementy docelowe i właściwości w katalogu nadrzędnym. Ten katalog zawiera również bibliotekę DLL, która definiuje zadania, które są używane przez obiekty docelowe w tym katalogu. *`<platform>`* Symbol zastępczy reprezentuje PODKATALOG ARM, arm64, Win32 lub x64.

- *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  Zawiera katalogi, które umożliwiają kompilacji generowanie aplikacji C++ przy użyciu określonego *`<toolset>`* . *`<platform>`* Symbol zastępczy reprezentuje PODKATALOG ARM, Win32 lub x64. *`<toolset>`* Symbol zastępczy reprezentuje podkatalog zestawu narzędzi.

::: moniker-end

### <a name="visual-studio-2015-and-earlier"></a>Visual Studio 2015 i starsze

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\<version>\`*

  Zawiera pliki głównych plików docelowych (. targets) i pliki właściwości (. props), które są używane przez obiekty docelowe. Domyślnie makro $ (VCTargetsPath) odwołuje się do tego katalogu.

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\<version>\Platforms\<platform>\`*

  Zawiera pliki docelowe i właściwości specyficzne dla platformy, które zastępują elementy docelowe i właściwości w katalogu nadrzędnym. Ten katalog zawiera również bibliotekę DLL, która definiuje zadania, które są używane przez obiekty docelowe w tym katalogu. *`<platform>`* Symbol zastępczy reprezentuje PODKATALOG ARM, Win32 lub x64.

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\<version>\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  Zawiera katalogi, które umożliwiają kompilacji generowanie aplikacji C++ przy użyciu określonego *`<toolset>`* . *`<version>`* Symbol zastępczy to v110 dla programu Visual studio 2012, V120 dla Visual Studio 2013 i wersji 140 dla programu Visual studio 2015. *`<platform>`* Symbol zastępczy reprezentuje PODKATALOG ARM, Win32 lub x64. *`<toolset>`* Symbol zastępczy reprezentuje podkatalog zestawu narzędzi. Na przykład jest wersji 140 do kompilowania aplikacji systemu Windows przy użyciu zestawu narzędzi programu Visual Studio 2015. Lub v120_xp do kompilowania dla systemu Windows XP przy użyciu zestawu narzędzi Visual Studio 2013.

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  Ścieżki umożliwiające kompilację do generowania aplikacji programu Visual Studio 2008 lub Visual Studio 2010 nie obejmują *`<version>`* . W tych wersjach *`<platform>`* symbol zastępczy reprezentuje podkatalog Itanium, Win32 lub x64. *`<toolset>`* Symbol zastępczy reprezentuje podkatalog zestawu narzędzi v90 lub V100.

## <a name="support-files"></a>Pliki obsługi

Katalogi plików pomocy technicznej zawierają pliki z następującymi rozszerzeniami:

| Wewnętrzny | Opis |
| --------- | ----------- |
| *`.targets`* | Zawiera `Target` elementy XML, które określają zadania, które są wykonywane przez element docelowy. Mogą również zawierać `PropertyGroup` `ItemGroup` elementy,, `ItemDefinitionGroup` i zdefiniowane przez użytkownika, `Item` które są używane do przypisywania plików i opcji wiersza polecenia do parametrów zadań.<br /><br /> Aby uzyskać więcej informacji, zobacz [Target element (MSBuild)](/visualstudio/msbuild/target-element-msbuild). |
| *`.props`* | Zawiera `Property Group` i zdefiniowane przez użytkownika `Property` elementy XML, które określają ustawienia plików i parametrów, które są używane podczas kompilacji.<br /><br /> Może również zawierać `ItemDefinitionGroup` i zdefiniowane przez użytkownika `Item` elementy XML, które określają dodatkowe ustawienia. Elementy zdefiniowane w grupie definicji elementu przypominają właściwości, ale nie są dostępne z wiersza polecenia. Pliki projektu programu Visual Studio często używają elementów zamiast właściwości do reprezentowania ustawień.<br /><br /> Aby uzyskać więcej informacji, zobacz [itemmanager element (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), [ItemDefinitionGroup element (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild)i [element Item (MSBuild)](/visualstudio/msbuild/item-element-msbuild). |
| *`.xml`* | Zawiera elementy XML, które deklarują i inicjują elementy interfejsu użytkownika IDE. Na przykład arkusze właściwości, strony właściwości, formanty TextBox i kontrolki ListBox.<br /><br /> *`.xml`* Pliki bezpośrednio obsługują IDE, nie MSBuild. Jednak wartości właściwości IDE są przypisywane do właściwości i elementów kompilacji.<br /><br /> Większość *`.xml`* plików znajduje się w podkatalogu specyficznym dla ustawień regionalnych. Na przykład pliki dla regionu angielski (Stany Zjednoczone) znajdują się w temacie `$(VCTargetsPath)\1033\` . |

## <a name="user-targets-and-properties"></a>Obiekty docelowe i właściwości użytkownika

Aby efektywnie korzystać z programu MSBuild, warto wiedzieć, które właściwości i cele są przydatne i istotne. Większość właściwości i obiektów docelowych pomaga zaimplementować system kompilacji programu Visual Studio i w związku z tym nie dotyczy użytkownika. W tej sekcji opisano właściwości zorientowane na użytkownika i cele, które warto znać.

### <a name="platformtoolset-property"></a>`PlatformToolset` wartość

`PlatformToolset`Właściwość określa, który zestaw narzędzi MSVC jest używany w kompilacji. Domyślnie używany jest bieżący zestaw narzędzi. Gdy ta właściwość jest ustawiona, jej wartość jest pobierana z ciągami literału w celu utworzenia ścieżki. Jest to katalog, który zawiera pliki właściwości i obiekty docelowe wymagane do skompilowania projektu dla konkretnej platformy. Zestaw narzędzi platformy musi być zainstalowany do kompilowania przy użyciu tej wersji zestawu narzędzi platformy.

Na przykład ustaw właściwość na, aby `PlatformToolset` `v140` używać narzędzi i bibliotek programu Visual Studio 2015 do kompilowania aplikacji:

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>`PreferredToolArchitecture` wartość

`PreferredToolArchitecture`Właściwość określa, czy kompilator i narzędzia z 32-bitowym, 64-bitowym są używane w kompilacji. Ta właściwość nie ma wpływu na architekturę ani konfigurację platformy wyjściowej. Domyślnie program MSBuild używa wersji x86 kompilatora i narzędzi, jeśli ta właściwość nie jest ustawiona.

Na przykład ustaw właściwość na `PreferredToolArchitecture` `x64` Aby użyć kompilatora 64-bitowego oraz narzędzi do kompilowania aplikacji:

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>`UseEnv` wartość

Domyślnie ustawienia specyficzne dla platformy dla bieżącego projektu zastępują zmienne środowiskowe PATH, INCLUDE, LIB, LIBPATH, CONFIGURATION i PLATFORM. Ustaw `UseEnv` Właściwość na, aby **`true`** zagwarantować, że zmienne środowiskowe nie zostaną zastąpione.

> `msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>Targets (Obiekty docelowe)

Istnieją setki obiektów docelowych w plikach obsługi programu Visual Studio. Większość są jednak ukierunkowanymi na system, które użytkownik może zignorować. Większość obiektów docelowych systemu jest poprzedzona znakiem podkreślenia ( `_` ) lub ma nazwę rozpoczynającą się od `PrepareFor` , `Compute` ,,, `Before` `After` `Pre` lub `Post` .

W poniższej tabeli przedstawiono kilka przydatnych elementów docelowych ukierunkowanych na użytkownika.

| Cel | Opis |
| ------ | ----------- |
| BscMake | Wykonuje narzędzie do konserwacji przeglądanych informacji firmy Microsoft, bscmake.exe. |
| Kompilacja | Kompiluje projekt.<br /><br /> Ten obiekt docelowy jest wartością domyślną dla projektu. |
| ClCompile | Wykonuje narzędzie kompilatora MSVC, cl.exe. |
| Clean | Usuwa tymczasowe i pośrednie pliki kompilacji. |
| Lib | Wykonuje narzędzie Microsoft 32-bit Library Manager, lib.exe. |
| Łącze | Wykonuje narzędzie konsolidatora MSVC, link.exe. |
| ManifestResourceCompile | Wyodrębnia listę zasobów z manifestu, a następnie wykonuje narzędzie kompilatora zasobów systemu Microsoft Windows, rc.exe. |
| MIDL | Wykonuje narzędzie kompilatora Microsoft Interface Definition Language (MIDL), midl.exe. |
| Ponowne kompilowanie | Czyści, a następnie kompiluje projekt. |
| ResourceCompile | Wykonuje narzędzie kompilatora zasobów systemu Microsoft Windows, rc.exe. |
| XdcMake | Wykonuje narzędzie dokumentacji XML xdcmake.exe. |
| XSD | Wykonuje narzędzie definicji schematu XML, xsd.exe. *Zobacz Uwaga.* |

> [!NOTE]
> W programie Visual Studio 2017 lub nowszym obsługa projektu C++ dla plików **XSD** jest przestarzała. Nadal można użyć **programu Microsoft. VisualC. CppCodeProvider** , ręcznie dodając **CppCodeProvider.dll** do pamięci GAC.

## <a name="see-also"></a>Zobacz także

[Odwołanie do zadania programu MSBuild](/visualstudio/msbuild/msbuild-task-reference)\
[BscMake, zadanie](/visualstudio/msbuild/bscmake-task)\
[CL — zadanie](/visualstudio/msbuild/cl-task)\
[CPPClean —, zadanie](/visualstudio/msbuild/cppclean-task)\
[LIB — zadanie](/visualstudio/msbuild/lib-task)\
[Połącz zadanie](/visualstudio/msbuild/link-task)\
[MIDL, zadanie](/visualstudio/msbuild/midl-task)\
[MT — zadanie](/visualstudio/msbuild/mt-task)\
[RC — zadanie](/visualstudio/msbuild/rc-task)\
[SetEnv, zadanie](/visualstudio/msbuild/setenv-task)\
[VCMessage —, zadanie](/visualstudio/msbuild/vcmessage-task)\
[XDCMake, zadanie](/visualstudio/msbuild/xdcmake-task)

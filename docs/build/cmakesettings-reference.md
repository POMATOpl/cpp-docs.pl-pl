---
description: 'Dowiedz się więcej na temat: CMakeSettings.jsw odwołaniu do schematu'
title: CMakeSettings.jsodwołania do schematu
ms.date: 11/22/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 2be5edb616764d56e7c08a51be19aab11a62f227
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156908"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.jsodwołania do schematu

::: moniker range="msvc-140"

Projekty CMake są obsługiwane w programie Visual Studio 2017 i nowszych.

::: moniker-end

::: moniker range=">=msvc-150"

**CMakeSettings.jsw** pliku zawiera informacje, które są używane przez program Visual Studio na potrzeby technologii IntelliSense i konstruowania argumentów wiersza polecenia, które są przekazywane do cmake.exe dla określonej *konfiguracji* i *środowiska* kompilatora. Konfiguracja określa właściwości, które mają zastosowanie do określonej platformy i typu kompilacji, na przykład `x86-Debug` lub `Linux-Release` . Każda konfiguracja określa środowisko, które hermetyzuje informacje o zestawie narzędzi kompilatora, na przykład MSVC, w zatoce lub Clang. CMake używa argumentów wiersza polecenia, aby ponownie wygenerować główny plik *CMakeCache.txt* i inne pliki projektu dla projektu. Wartości można przesłonić w plikach *CMakeLists.txt* .

Można dodać lub usunąć konfiguracje w IDE, a następnie edytować je bezpośrednio w pliku JSON lub użyć **edytora ustawień CMAKE** (Visual Studio 2019 i nowsze). Aby generować różne pliki projektu, można łatwo przełączać się między konfiguracjami w środowisku IDE. Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień kompilacji CMAKE w programie Visual Studio](customize-cmake-settings.md) .

## <a name="configurations"></a>Konfiguracje

`configurations`Tablica zawiera wszystkie konfiguracje dla projektu CMAKE. Aby uzyskać więcej informacji o wstępnie zdefiniowanych konfiguracjach, zobacz CMAKE predefiniowana [Configuration Reference](cmake-predefined-configuration-reference.md) . Do pliku można dodać dowolną liczbę wstępnie zdefiniowanych lub niestandardowych konfiguracji.

`configuration`Ma następujące właściwości:

- `addressSanitizerEnabled`: Jeśli **`true`** kompiluje program z adresem Sanitizer (eksperymentalny w systemie Windows). W systemie Linux Skompiluj przy użyciu elementu-FNO-pominięcia-ramki i optymalizacji kompilatora — OS lub-oo, aby uzyskać najlepsze wyniki.
- `addressSanitizerRuntimeFlags`: flagi środowiska uruchomieniowego przekazane do AddressSanitizer za pośrednictwem zmiennej środowiskowej ASAN_OPTIONS. Format: przedsięwzięcia1 = Value: przedsięwzięcia2 = wartość2.
- `buildCommandArgs`: określa natywne przełączniki kompilacji przesłane do CMake po--Build--. Na przykład przekazywanie-v przy użyciu generatora Ninja wymusza Ninja do danych wyjściowych wiersza polecenia. Zobacz [argumenty wiersza polecenia Ninja](#ninja) , aby uzyskać więcej informacji na temat poleceń ninja.
- `buildRoot`: określa katalog, w którym CMake generuje skrypty kompilacji dla wybranego generatora.  Mapuje do przełącznika **-DCMAKE_BINARY_DIR** i określa, gdzie *CMakeCache.txt* zostanie utworzony. Jeśli folder nie istnieje, zostanie utworzony. Obsługiwane makra obejmują,,,,,, `${workspaceRoot}` `${workspaceHash}` ,, `${projectFile}` `${projectDir}` `${thisFile}` `${thisFileDir}` `${name}` `${generator}` `${env.VARIABLE}` .
- `cacheGenerationCommand`: określa narzędzie i argumenty wiersza polecenia, na przykład *gencache.bat debugowanie* w celu wygenerowania pamięci podręcznej. Polecenie jest uruchamiane z powłoki w określonym środowisku w celu skonfigurowania, gdy użytkownik jawnie zażąda ponownego uruchomienia lub zmodyfikowano CMakeLists.txt lub CMakeSettings.jsw pliku.
- `cacheRoot`: Określa ścieżkę do pamięci podręcznej CMake. Ten katalog powinien zawierać istniejący plik *CMakeCache.txt* .
- `clangTidyChecks`: rozdzielona przecinkami lista ostrzeżeń, które zostaną przesłane do Clang-uporządkowanego; symbole wieloznaczne są dozwolone, a prefiks "-" usunie testy.
- `cmakeCommandArgs`: określa dodatkowe opcje wiersza polecenia przekazaną do CMake, gdy zostanie wywołana w celu wygenerowania plików projektu.
- `cmakeToolchain`: Określa plik łańcucha narzędzi. Ta wartość jest przenoszona do CMake przy użyciu-DCMAKE_TOOLCHAIN_FILE ".
- `codeAnalysisRuleset`: określa zestaw reguł, który ma być używany podczas uruchamiania analizy kodu. Może to być pełna ścieżka lub nazwa pliku zestawu reguł zainstalowanego przez program Visual Studio.
- `configurationType`: określa konfigurację typu kompilacji dla wybranego generatora. Może być jednym z:

  - Debugowanie
  - Release
  - MinSizeRel
  - RelWithDebInfo
  
- `ctestCommandArgs`: określa dodatkowe opcje wiersza polecenia, które przechodzą do narzędzia ctest podczas uruchamiania testów ".
- `description`: Opis tej konfiguracji, która będzie wyświetlana w menu.
- `enableClangTidyCodeAnalysis`: Użyj Clang-Tidy do analizy kodu.
- `enableMicrosoftCodeAnalysis`: Użyj narzędzi analizy kodu firmy Microsoft na potrzeby analizy kodu.
- `generator`: określa Generator CMake, który ma być używany w tej konfiguracji. Może być jednym z:
  
  **Tylko program Visual Studio 2019:**
  - Program Visual Studio 16 2019
  - Program Visual Studio 16 2019 Win64
  - Program Visual Studio 16 2019 ARM

  **Program Visual Studio 2017 lub nowszy:**
  - Program Visual Studio 15 2017
  - Program Visual Studio 15 2017 Win64
  - Program Visual Studio 15 2017 ARM
  - Program Visual Studio 14 2015
  - Program Visual Studio 14 2015 Win64
  - Program Visual Studio 14 2015 ARM
  - Pliki reguł programu make systemu UNIX
  - Ninja

Ponieważ Ninja jest zaprojektowana dla szybkich szybkości kompilacji, a nie elastyczności i funkcji, jest ustawiana jako domyślna. Jednak niektóre projekty CMake mogą nie być w stanie poprawnie skompilować przy użyciu ninja. W takim przypadku można wydać CMake do generowania projektów programu Visual Studio.

Aby określić Generator programu Visual Studio w programie Visual Studio 2017, Otwórz edytor ustawień z menu głównego, wybierając pozycję **CMAKE | Zmień ustawienia CMake**. Usuń "Ninja" i wpisz "V". Pozwala to aktywować funkcję IntelliSense, która umożliwia wybranie generatora, którego chcesz użyć.

Aby określić Generator programu Visual Studio w programie Visual Studio 2019, kliknij prawym przyciskiem myszy plik *CMakeLists.txt* w **Eksplorator rozwiązań** a następnie wybierz pozycję **Ustawienia CMakeymi dla opcji Project** > **Show Advanced Settings** > **CMAKE Generator**.

Gdy aktywna konfiguracja określa Generator programu Visual Studio, domyślnie MSBuild.exe jest wywoływana z `-m -v:minimal` argumentami. Aby dostosować kompilację, wewnątrz  *CMakeSettings.jsw* pliku można określić dodatkowe [argumenty wiersza polecenia MSBuild](../build/reference/msbuild-visual-cpp-overview.md) , które mają być przekazane do systemu kompilacji za pośrednictwem `buildCommandArgs` Właściwości:

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `installRoot`: określa katalog, w którym CMake generuje cele instalacji dla wybranego generatora. Obsługiwane makra obejmują,,,,,, `${workspaceRoot}` `${workspaceHash}` ,, `${projectFile}` `${projectDir}` `${thisFile}` `${thisFileDir}` `${name}` `${generator}` `${env.VARIABLE}` .
- `inheritEnvironments`: określa co najmniej jedno środowisko kompilatora, od którego zależy ta konfiguracja. Może to być dowolne środowisko niestandardowe lub jedno ze wstępnie zdefiniowanych środowisk. Aby uzyskać więcej informacji, zobacz [środowiska](#environments).
- `intelliSenseMode`: Określa tryb używany do obliczania informacji IntelliSense. Może być jednym z:

  - Windows-MSVC — x86
  - Windows-MSVC — x64
  - Windows-MSVC — ARM
  - Windows-MSVC-arm64
  - Android-Clang — x86
  - Android-Clang — x64
  - Android-Clang — ARM
  - Android-Clang-arm64
  - iOS — Clang — x86
  - iOS — Clang — x64
  - iOS — Clang — ARM
  - iOS-Clang-arm64
  - Windows-Clang — x86
  - Windows-Clang — x64
  - Windows-Clang — ARM
  - Windows-Clang-arm64
  - Linux — pozarząd — x86
  - Linux — pozarząd — x64
  - Linux — Zarząd — ARM

- `name`: nazwa konfiguracji.  Aby uzyskać więcej informacji o wstępnie zdefiniowanych konfiguracjach, zobacz CMAKE predefiniowana [Configuration Reference](cmake-predefined-configuration-reference.md) .
- `wslPath`: ścieżka do uruchamiania wystąpienia podsystemu Windows dla systemu Linux.

### <a name="additional-settings-for-cmake-linux-projects"></a>Dodatkowe ustawienia dla projektów CMake Linux

- `remoteMachineName`: Określa nazwę zdalnego komputera z systemem Linux, który obsługuje CMake, kompilacje i debuger. Użyj Menedżera połączeń do dodawania nowych maszyn z systemem Linux. Obsługiwane makra obejmują `${defaultRemoteMachineName}` .
- `remoteCopySourcesOutputVerbosity`: określa poziom szczegółowości operacji kopiowania źródła na maszynę zdalną. Może być jednym z "" normal "," verbose "lub" Diagnostic ".
- `remoteCopySourcesConcurrentCopies`: określa liczbę równoczesnych operacji kopiowania używanych podczas synchronizacji źródeł z maszyną zdalną (tylko SFTP).
- `remoteCopySourcesMethod`: określa metodę kopiowania plików na maszynę zdalną. Może to być "rsync" lub "SFTP".
- `remoteCMakeListsRoot`: określa katalog na komputerze zdalnym, który zawiera projekt CMake. Obsługiwane makra obejmują,,,,,, `${workspaceRoot}` `${workspaceHash}` ,, `${projectFile}` `${projectDir}` `${thisFile}` `${thisFileDir}` `${name}` `${generator}` `${env.VARIABLE}` .
- `remoteBuildRoot`: określa katalog na komputerze zdalnym, w którym CMake generuje skrypty kompilacji dla wybranego generatora. Obsługiwane makra obejmują,,,,,, `${workspaceRoot}` `${workspaceHash}` ,, `${projectFile}` `${projectDir}` `${thisFile}` `${thisFileDir}` `${name}` `${generator}` `${env.VARIABLE}` .
- `remoteInstallRoot`: określa katalog na komputerze zdalnym, w którym program CMake generuje cele instalacji dla wybranego generatora. Obsługiwane makra obejmują,,,,,,, `${workspaceRoot}` `${workspaceHash}` `${projectFile}` `${projectDir}` `${thisFile}` `${thisFileDir}` `${name}` `${generator}` i `${env.VARIABLE}` gdzie `VARIABLE` jest zmienną środowiskową, która została zdefiniowana na poziomie systemu, użytkownika lub sesji.
- `remoteCopySources`: `boolean` Określa, czy program Visual Studio ma kopiować pliki źródłowe na maszynę zdalną. Wartość domyślna to true. Ustaw wartość false, jeśli chcesz samodzielnie zarządzać synchronizacją plików.
- `remoteCopyBuildOutput`: A `boolean` , który określa, czy dane wyjściowe kompilacji mają być kopiowane z systemu zdalnego.
- `remoteCopyAdditionalIncludeDirectories`: Dodatkowe katalogi dołączane do skopiowania z komputera zdalnego do obsługi technologii IntelliSense. Sformatuj jako "/path1;/path2...".
- `remoteCopyExcludeDirectories`: Uwzględnij katalogi, które nie mają być kopiowane z maszyny zdalnej. Sformatuj jako "/path1;/path2...".
- `remoteCopyUseCompilerDefaults`: Określa, czy ma być używane domyślnie zdefiniowane i dołączone ścieżki kompilatora dla IntelliSense. Powinien mieć wartość false tylko wtedy, gdy kompilatory używane do nie obsługują argumentów w stylu w ramach programu.
- `rsyncCommandArgs`: określa zestaw dodatkowych opcji wiersza polecenia przekazaną do rsync.
- `remoteCopySourcesExclusionList`: `array` Określa listę ścieżek, które mają zostać wykluczone podczas kopiowania plików źródłowych ': ścieżka może być nazwą pliku/katalogu lub ścieżką względną do katalogu głównego kopii. Symbole wieloznaczne \\ \" * \\ \" i \\ \" ? \\ \" mogą służyć do dopasowywania wzorców globalizowania.
- `cmakeExecutable`: Określa pełną ścieżkę do pliku wykonywalnego programu CMake, w tym nazwę i rozszerzenie pliku.
- `remotePreGenerateCommand`: Określa polecenie do uruchomienia przed uruchomieniem CMake w celu przeanalizowania pliku *CMakeLists.txt* .
- `remotePrebuildCommand`: Określa polecenie do uruchomienia na maszynie zdalnej przed kompilacją.
- `remotePostbuildCommand`: Określa polecenie do uruchomienia na maszynie zdalnej po kompilacji.
- `variables`: zawiera parę nazwa-wartość zmiennych cmake, które będą przekazywać *= _wartość_ nazwy* jako **D** do cmake. Jeśli instrukcje dotyczące kompilacji projektu CMake określają dodanie jakichkolwiek zmiennych bezpośrednio do pliku *CMakeCache.txt* , zaleca się ich dodanie zamiast tego. Poniższy przykład pokazuje, jak określić pary nazwa-wartość dla zestawu narzędzi 14.14.26428 MSVC:

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    }
  ]
```

Należy pamiętać, że jeśli nie zdefiniujesz `"type"` , `"STRING"` Typ zostanie domyślnie przyjęty.

- `remoteCopyOptimizations`: **Program Visual Studio 2019 w wersji 16,5 lub nowszej** służący do kontrolowania kopiowania źródła do zdalnego obiektu docelowego. Optymalizacje są domyślnie włączone. Obejmuje `remoteCopyUseOptimizations` , `rsyncSingleDirectoryCommandArgs` i `remoteCopySourcesMaxSmallChange` .

## <a name="environments"></a><a name="environments"></a> Wiejski

*Środowisko* hermetyzuje zmienne środowiskowe, które są ustawiane w procesie, którego program Visual Studio używa do wywoływania cmake.exe. W przypadku projektów MSVC zmienne są te, które są ustawiane w [wierszu polecenia dewelopera](building-on-the-command-line.md) dla określonej platformy. Na przykład `msvc_x64_x64` środowisko jest takie samo jak uruchamianie **wiersz polecenia dla deweloperów dla programu vs 2017** lub **wiersz polecenia dla deweloperów dla programu vs 2019** z argumentami **-Arch = amd64-host_arch = amd64** . Możesz użyć `env.{<variable_name>}` składni w *CMakeSettings.jsna* , aby odwołać się do poszczególnych zmiennych środowiskowych, na przykład w celu skonstruowania ścieżek do folderów.  Dostępne są następujące wstępnie zdefiniowane środowiska:

- linux_arm: kierowanie do zdalnego systemu ARM Linux.
- linux_x64: system TARGET x64 Linux zdalnie.
- linux_x86: zdalny system x86 Linux.
- msvc_arm: docelowa wersja systemu Windows ARM przy użyciu kompilatora MSVC.
- msvc_arm_x64: docelowa architektura ARM systemu Windows przy użyciu 64-bitowego kompilatora MSVC.
- msvc_arm64: docelowa ARM64 systemu Windows za pomocą kompilatora MSVC.
- msvc_arm64_x64: docelowa ARM64 systemu Windows przy użyciu 64-bitowego kompilatora MSVC.
- msvc_x64: docelowa wersja x64 systemu Windows za pomocą kompilatora MSVC.
- msvc_x64_x64: docelowa wersja x64 systemu Windows z 64-bitowym kompilatorem MSVC.
- msvc_x86: docelowa wersja architektury x86 systemu Windows przy użyciu kompilatora MSVC.
- msvc_x86_x64: docelowy system Windows x86 z 64-bitowym kompilatorem MSVC.

### <a name="accessing-environment-variables-from-cmakeliststxt"></a>Uzyskiwanie dostępu do zmiennych środowiskowych z CMakeLists.txt

W pliku CMakeLists.txt wszystkie zmienne środowiskowe są przywoływane przez składnię `$ENV{variable_name}` . Aby wyświetlić dostępne zmienne dla środowiska, otwórz odpowiedni wiersz polecenia i wpisz `SET` . Niektóre informacje w zmiennych środowiskowych są również dostępne za pomocą zmiennych CMake systemu introspekcji, ale może być wygodniejsze użycie zmiennej środowiskowej. Na przykład wersja kompilatora MSVC lub wersja Windows SDK są łatwo pobierane za pomocą zmiennych środowiskowych.

### <a name="custom-environment-variables"></a>Niestandardowe zmienne środowiskowe

W programie  `CMakeSettings.json` można definiować niestandardowe zmienne środowiskowe globalnie lub dla konfiguracji w `environments` tablicy. Środowisko niestandardowe jest wygodnym sposobem grupowania zestawu właściwości, których można użyć zamiast wstępnie zdefiniowanego środowiska lub w celu rozbudowania lub zmodyfikowania wstępnie zdefiniowanego środowiska. Każdy element w `environments` tablicy składa się z:

- `namespace`: Nazwa środowiska, tak aby jego zmienne mogły być przywoływane z konfiguracji w formularzu `namespace.variable` . Domyślny obiekt środowiska jest wywoływany `env` i jest wypełniany przy użyciu określonych zmiennych środowiskowych systemu, takich jak `%USERPROFILE%` .
- `environment`: jednoznacznie identyfikuje tę grupę zmiennych. Zezwala, aby grupa była dziedziczona w dalszej części `inheritEnvironments` wpisu.
- `groupPriority`: Liczba całkowita, która określa priorytet tych zmiennych podczas ich oceniania. Elementy o większej liczbie są oceniane jako pierwsze.
- `inheritEnvironments`: Tablica wartości, które określają zestaw środowisk, które są dziedziczone przez tę grupę. Ta funkcja umożliwia dziedziczenie domyślnych środowisk i tworzenie niestandardowych zmiennych środowiskowych, które są przesyłane do CMake.exe podczas jego uruchamiania.

**Program Visual Studio 2019 w wersji 16,4 lub nowszej:** Elementy docelowe debugowania są automatycznie uruchamiane przy użyciu środowiska określonego w *CMakeSettings.jsna*. Zmienne środowiskowe można przesłonić lub dodać na podstawie poszczególnych zadań w [launch.vs.js](launch-vs-schema-reference-cpp.md) i [tasks.vs.jsna](tasks-vs-json-schema-reference-cpp.md).

W poniższym przykładzie zdefiniowano jedną zmienną globalną, **BuildDir**, która jest dziedziczona zarówno w konfiguracji x86, jak i x64-Debug. Każda konfiguracja używa zmiennej do określenia wartości właściwości **element buildroot** dla danej konfiguracji. Należy pamiętać, że każda konfiguracja używa właściwości **inheritEnvironments** , aby określić zmienną, która ma zastosowanie tylko do tej konfiguracji.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

W następnym przykładzie konfiguracja programu x86-Debug definiuje własną wartość właściwości **BuildDir** . Ta wartość zastępuje wartość ustawioną przez globalną Właściwość **BuildDir** , dzięki czemu **element buildroot** daje w wyniku `D:\custom-builddir\x86-Debug` .

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir"
          // This environment does not specify a namespace, hence by default "env" will be assumed.
          // "namespace" : "name" would require that this variable be referenced with "${name.BuildDir}".
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ],
      // Since this configuration doesn't modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="macros"></a>Makra

Następujące makra mogą być używane w *CMakeSettings.jsna*:

- `${workspaceRoot}` — Pełna ścieżka folderu obszaru roboczego
- `${workspaceHash}` — skrót lokalizacji obszaru roboczego; przydatne do tworzenia unikatowych identyfikatorów dla bieżącego obszaru roboczego (na przykład do użycia w ścieżkach folderów)
- `${projectFile}` — Pełna ścieżka pliku głównego CMakeLists.txt
- `${projectDir}` — Pełna ścieżka folderu głównego pliku CMakeLists.txt
- `${thisFile}` — Pełna ścieżka  `CMakeSettings.json` pliku
- `${name}` — Nazwa konfiguracji
- `${generator}` — nazwa generatora CMake użyta w tej konfiguracji.

Wszystkie odwołania do makr i zmiennych środowiskowych w *CMakeSettings.jsna* są rozwinięte przed przekazaniem do cmake.exe wiersza polecenia.

## <a name="ninja-command-line-arguments"></a><a name="ninja"></a> Ninja argumenty wiersza polecenia

Jeśli elementy docelowe nie są określone, kompiluje obiekt docelowy "default".

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Opcja|Opis|
|--------------|------------|
| --Version  | Drukuj wersję Ninja ("1.7.1")|
|   -C DIR   | Zmień na DIR przed wykonaniem jakichkolwiek innych czynności|
|   -PLIK f  | Określ plik wejściowy kompilacji (domyślnie = Build. ninja)|
|   -j N     | równoległe Uruchamianie zadań N (domyślnie = 14, pochodzących z dostępnych procesorów CPU)|
|   -k N     | Kontynuuj, dopóki N zadań nie powiedzie się (wartość domyślna to 1)|
|   -l N     | nie uruchamiaj nowych zadań, jeśli średnia obciążenia jest większa niż N|
|   -n       | uruchomienie suche (nie uruchamiaj poleceń, ale działa podobnie jak w przypadku powodzenia)|
|   -v       | Pokaż wszystkie wiersze poleceń podczas kompilowania|
|   -d — tryb  | Włącz debugowanie (Użyj listy do trybów listy)|
|   -t — narzędzie  | Uruchom podnarzędzie (Użyj-t list, aby wyświetlić podnarzędzia). kończy opcje najwyższego poziomu; dalsze flagi są przesyłane do narzędzia|
|   -w — flaga  | Dostosowywanie ostrzeżeń (lista użycia do wyświetlania ostrzeżeń)|

::: moniker-end

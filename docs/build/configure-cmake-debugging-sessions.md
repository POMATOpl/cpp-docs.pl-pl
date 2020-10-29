---
title: Konfigurowanie sesji debugowania CMake w programie Visual Studio
description: Opisuje sposób korzystania z programu Visual Studio w celu skonfigurowania ustawień debugera CMake.
ms.date: 04/02/2020
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: a790e26e5bf3980ffb81a3ba778577afacff95b4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922234"
---
# <a name="configure-cmake-debugging-sessions"></a>Konfigurowanie sesji debugowania narzędzia CMake

::: moniker range="msvc-140"

Natywna obsługa CMake jest dostępna w programie Visual Studio 2017 i nowszych. Aby zapoznać się z dokumentacją tych wersji, ustaw kontrolkę selektora **wersji** programu Visual Studio dla tego artykułu na visual Studio 2017 lub visual Studio 2019. Znajduje się w górnej części spisu treści na tej stronie.

::: moniker-end

::: moniker range=">=msvc-150"

Wszystkie elementy wykonywalne CMake są wyświetlane na liście rozwijanej **elementu startowego** na pasku narzędzi **Ogólne** . Wybierz jeden z nich, aby rozpocząć sesję debugowania i uruchomić debuger.

![Lista rozwijana elementu startowego CMake](media/cmake-startup-item-dropdown.png "Lista rozwijana elementu startowego CMake")

Możesz również uruchomić sesję debugowania z poziomu Eksplorator rozwiązań. Najpierw przejdź do **widoku CMAKE targets** w oknie **Eksplorator rozwiązań** .

![Przycisk Widok elementów docelowych CMake](media/cmake-targets-view.png  "Element menu Widok elementów docelowych CMake")

Następnie kliknij prawym przyciskiem myszy plik wykonywalny i wybierz polecenie **Debuguj** . To polecenie automatycznie uruchamia debugowanie wybranego elementu docelowego na podstawie aktywnej konfiguracji.

## <a name="customize-debugger-settings"></a>Dostosuj ustawienia debugera

Możesz dostosować ustawienia debugera dla dowolnego elementu wykonywalnego CMake w projekcie. Znajdują się one w pliku konfiguracji o nazwie *launch.vs.jsna* , znajdującym się w *`.vs`* folderze w katalogu głównym projektu. Plik konfiguracji uruchamiania jest przydatny w większości scenariuszy debugowania, ponieważ można skonfigurować i zapisać szczegóły konfiguracji debugowania. Istnieją trzy punkty wejścia do tego pliku:

- **Menu Debuguj:** Wybierz pozycję **debuguj > Debuguj i Uruchom ustawienia dla $ {activeDebugTarget}** z menu głównego, aby dostosować konfigurację debugowania specyficzną dla aktywnego celu debugowania. Jeśli nie wybrano elementu docelowego debugowania, ta opcja jest wyszarzona.

![Punkt wejścia menu debugowania](media/cmake-debug-menu.png "Punkt wejścia menu debugowania")

- **Widok elementów docelowych:** Przejdź do **widoku obiektów docelowych** w Eksplorator rozwiązań. Następnie kliknij prawym przyciskiem myszy element docelowy debugowania i wybierz polecenie **Dodaj konfigurację debugowania** , aby dostosować konfigurację debugowania specyficzną dla wybranego obiektu docelowego.

![Punkt wejścia widoku elementów docelowych](media/cmake-targets-add-debug-configuration.png "Punkt wejścia widoku elementów docelowych")

- **CMakeLists.txt główny:** Kliknij prawym przyciskiem myszy węzeł główny *CMakeLists.txt* a następnie wybierz polecenie **Dodaj konfigurację debugowania** , aby otworzyć okno dialogowe **Wybierz debuger** . Okno dialogowe umożliwia dodanie *dowolnego* typu konfiguracji debugowania, ale należy ręcznie określić element docelowy CMAKE do wywołania za pośrednictwem `projectTarget` właściwości.

![Okno dialogowe Wybieranie debugera](media/cmake-select-a-debugger.png "Okno dialogowe Wybieranie debugera")

Można edytować *launch.vs.jsw* pliku, aby utworzyć konfiguracje debugowania dla dowolnej liczby elementów docelowych CMAKE. Po zapisaniu pliku program Visual Studio tworzy wpis dla każdej nowej konfiguracji na liście rozwijanej **elementu startowego** .

## <a name="reference-keys-in-cmakesettingsjson"></a>Klucze odwołań w CMakeSettings.jsna

Aby odwołać się do dowolnego klucza w *CMakeSettings.js* w pliku, należy go dołączać `cmake.` do *launch.vs.jsna* . W poniższym przykładzie przedstawiono prostą *launch.vs.jsw* pliku, który ściąga wartość `remoteCopySources` klucza w *CMakeSettings.jsna* pliku dla aktualnie wybranej konfiguracji:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

**Zmienne środowiskowe** zdefiniowane w *CMakeSettings.json* mogą być również używane w launch.vs.jsprzy użyciu składni `${env.VARIABLE_NAME}` . W programie Visual Studio 2019 w wersji 16,4 i nowszych elementy docelowe debugowania są automatycznie uruchamiane przy użyciu środowiska określonego w *CMakeSettings.jsna* . Można cofnąć ustawienia zmiennej środowiskowej przez ustawienie jej na **wartość null** .

## <a name="launchvsjson-reference"></a>Launch.vs.jsna temat odwołania

Istnieje wiele *launch.vs.js* właściwości, które obsługują wszystkie scenariusze debugowania. Następujące właściwości są wspólne dla wszystkich konfiguracji debugowania, zarówno zdalnych, jak i lokalnych:

- `projectTarget`: Określa element docelowy CMake, który ma zostać wywołany podczas kompilowania projektu. Program Visual Studio automatycznie wypełnia tę właściwość, jeśli wprowadzasz *polecenielaunch.vs.jsw* **menu Debugowanie** lub **widoku elementów docelowych** . Ta wartość musi być zgodna z nazwą istniejącego elementu docelowego debugowania wyświetlaną na liście rozwijanej **elementu startowego** .

- `env`: Dodatkowe zmienne środowiskowe do dodania przy użyciu składni:

  ```json
  "env": {
        "DEBUG_LOGGING_LEVEL": "trace;info",
        "ENABLE_TRACING": "true"
      }
  ```

- `args`: Argumenty wiersza polecenia przekazane do programu w celu debugowania.

## <a name="launchvsjson-reference-for-remote-projects-and-wsl"></a>Launch.vs.jsw odniesieniu do projektów zdalnych i WSL

W programie Visual Studio 2019 w wersji 16,6 dodaliśmy nową konfigurację debugowania, `type: cppgdb` Aby uprościć debugowanie w systemach zdalnych i WSL. Stare konfiguracje debugowania `type: cppdbg` są nadal obsługiwane.

### <a name="configuration-type-cppgdb"></a>Typ konfiguracji `cppgdb`

- `name`: Przyjazna nazwa identyfikująca konfigurację na liście rozwijanej **elementu startowego** .
- `project`: Określa ścieżkę względną do pliku projektu. Zwykle nie trzeba zmieniać tej ścieżki podczas debugowania projektu CMake.
- `projectTarget`: Określa element docelowy CMake, który ma zostać wywołany podczas kompilowania projektu. Program Visual Studio automatycznie wypełnia tę właściwość, jeśli wprowadzasz *polecenielaunch.vs.jsw* **menu Debugowanie** lub **widoku elementów docelowych** . Ta wartość docelowa musi być zgodna z nazwą istniejącego elementu docelowego debugowania wymienionego na liście rozwijanej **elementu startowego** .
- `debuggerConfiguration`: Wskazuje, który zestaw domyślnych wartości debugowania ma być używany. W programie Visual Studio 2019 w wersji 16,6 jedyną prawidłową opcją jest `gdb` . Program Visual Studio 2019 w wersji 16,7 lub nowszej obsługuje także `gdbserver` .
- `args`: Argumenty wiersza polecenia przekazane podczas uruchamiania do debugowanego programu.
- `env`: Dodatkowe zmienne środowiskowe przechodzą do debugowanego programu. Na przykład `{"DISPLAY": "0.0"}`.
- `processID`: Identyfikator procesu systemu Linux do dołączenia. Używany tylko podczas dołączania do procesu zdalnego. Aby uzyskać więcej informacji, zobacz [Rozwiązywanie problemów z dołączaniem do procesów przy użyciu GDB](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB).

#### <a name="additional-options-for-the-gdb-configuration"></a>Dodatkowe opcje `gdb` konfiguracji

- `program`: Domyślnie `"${debugInfo.fullTargetPath}"` . Ścieżka systemu UNIX do aplikacji do debugowania. Wymagany tylko wtedy, gdy jest inny niż docelowy plik wykonywalny w lokalizacji kompilacji lub wdrożenia.
- `remoteMachineName`: Domyślnie `"${debugInfo.remoteMachineName}"` . Nazwa systemu zdalnego, który hostuje program do debugowania. Wymagane tylko w przypadku, gdy różni się od systemu kompilacji. Musi mieć istniejący wpis w [Menedżerze połączeń](../linux/connect-to-your-remote-linux-computer.md). Naciśnij **klawisze CTRL + SPACJA** , aby wyświetlić listę wszystkich istniejących połączeń zdalnych.
- `cwd`: Domyślnie `"${debugInfo.defaultWorkingDirectory}"` . Ścieżka systemu UNIX do katalogu w systemie zdalnym, gdzie `program` jest uruchomiony. Ten katalog musi istnieć.
- `gdbpath`: Domyślnie `/usr/bin/gdb` . Pełna ścieżka systemu UNIX do `gdb` używanej do debugowania. Wymagane tylko w przypadku korzystania z niestandardowej wersji programu `gdb` .
- `preDebugCommand`: Polecenie systemu Linux do uruchomienia bezpośrednio przed wywołaniem `gdb` . `gdb` nie rozpoczyna się do momentu zakończenia wykonywania polecenia. Możesz użyć opcji, aby uruchomić skrypt przed wykonaniem `gdb` .

#### <a name="additional-options-allowed-with-the-gdbserver-configuration-167-or-later"></a>Dodatkowe opcje dozwolone w przypadku `gdbserver` konfiguracji (16,7 lub nowszej)

- `program`: Domyślnie `"${debugInfo.fullTargetPath}"` . Ścieżka systemu UNIX do aplikacji do debugowania. Wymagany tylko wtedy, gdy jest inny niż docelowy plik wykonywalny w lokalizacji kompilacji lub wdrożenia.
- `remoteMachineName`: Domyślnie `"${debugInfo.remoteMachineName}"` . Nazwa systemu zdalnego, który hostuje program do debugowania. Wymagane tylko w przypadku, gdy różni się od systemu kompilacji. Musi mieć istniejący wpis w [Menedżerze połączeń](../linux/connect-to-your-remote-linux-computer.md). Naciśnij **klawisze CTRL + SPACJA** , aby wyświetlić listę wszystkich istniejących połączeń zdalnych.
- `cwd`: Domyślnie `"${debugInfo.defaultWorkingDirectory}"` . Pełna ścieżka systemu UNIX do katalogu w systemie zdalnym, gdzie `program` jest uruchomiony. Ten katalog musi istnieć.
- `gdbPath`: Domyślnie `${debugInfo.vsInstalledGdb}` . Pełna ścieżka systemu Windows do `gdb` używanej do debugowania. Domyślnie jest `gdb` instalowany z programowaniem w systemie Linux przy użyciu obciążenia C/C++.
- `gdbserverPath`: Domyślnie `usr/bin/gdbserver` . Pełna ścieżka systemu UNIX do `gdbserver` używanej do debugowania.
- `preDebugCommand`: Polecenie systemu Linux do uruchomienia bezpośrednio przed uruchomieniem `gdbserver` . `gdbserver` nie rozpoczyna się do momentu zakończenia wykonywania polecenia.

#### <a name="deployment-options"></a>Opcje wdrożenia

Użyj następujących opcji, aby rozdzielić maszynę kompilacji (zdefiniowaną w CMakeSettings.json) z komputera zdalnego debugowania.

- `remoteMachineName`: Zdalna maszyna debugowania. Wymagane tylko w przypadku, gdy jest inny niż maszyna kompilacji. Musi mieć istniejący wpis w [Menedżerze połączeń](../linux/connect-to-your-remote-linux-computer.md). Naciśnij **klawisze CTRL + SPACJA** , aby wyświetlić listę wszystkich istniejących połączeń zdalnych.
- `disableDeploy`: Domyślnie **`false`** . Wskazuje, czy separacja kompilacji/debugowania jest wyłączona. Gdy **`false`** Ta opcja umożliwia kompilowanie i debugowanie na dwóch oddzielnych komputerach.
- `deployDirectory`: Pełna ścieżka systemu UNIX do katalogu `remoteMachineName` , w którym plik wykonywalny jest kopiowany do.
- `deploy`: Tablica zaawansowanych ustawień wdrożenia. Te ustawienia wystarczy skonfigurować tylko wtedy, gdy potrzebujesz bardziej szczegółowej kontroli nad procesem wdrażania. Domyślnie tylko te pliki, które są niezbędne, aby proces debugowania został wdrożony na maszynie zdalnego debugowania.
  - `sourceMachine`: Maszyna, z której jest kopiowany plik lub katalog. Naciśnij **klawisze CTRL + SPACJA** , aby wyświetlić listę wszystkich połączeń zdalnych przechowywanych w Menedżerze połączeń. W przypadku natywnego kompilowania w WSL ta opcja jest ignorowana.
  - `targetMachine`: Komputer, do którego kopiowany jest plik lub katalog. Naciśnij **klawisze CTRL + SPACJA** , aby wyświetlić listę wszystkich połączeń zdalnych przechowywanych w Menedżerze połączeń.
  - `sourcePath`: Lokalizacja pliku lub katalogu w systemie `sourceMachine` .
  - `targetPath`: Lokalizacja pliku lub katalogu w systemie `targetMachine` .
  - `deploymentType`: Opis typu wdrożenia. `LocalRemote` i `RemoteRemote` są obsługiwane. `LocalRemote` oznacza kopiowanie z lokalnego systemu plików do systemu zdalnego określonego przez program `remoteMachineName` w *launch.vs.json* . `RemoteRemote` oznacza kopiowanie ze zdalnego systemu kompilacji określonego w *CMakeSettings.jsna* inny system zdalny określony w *launch.vs.jsna* .
  - `executable`: Wskazuje, czy wdrożony plik jest plikiem wykonywalnym.

### <a name="execute-custom-gdb-commands"></a>Wykonywanie `gdb` poleceń niestandardowych

Program Visual Studio obsługuje wykonywanie `gdb` poleceń niestandardowych w celu bezpośredniej współpracy z podstawowym debugerem. Aby uzyskać więcej informacji, zobacz [wykonywanie niestandardowych `gdb` poleceń LLDB](https://github.com/microsoft/MIEngine/wiki/Executing-custom-gdb-lldb-commands).

### <a name="enable-logging"></a>Włącz rejestrowanie

Włącz rejestrowanie MIEngine, aby zobaczyć, jakie polecenia są wysyłane do `gdb` , co zwraca dane wyjściowe `gdb` i jak długo trwa każde polecenie. [Dowiedz się więcej](https://github.com/microsoft/MIEngine/wiki/Logging)

### <a name="configuration-type-cppdbg"></a>Typ konfiguracji `cppdbg`

Podczas debugowania w systemie zdalnym lub WSL przy użyciu typu konfiguracji można użyć następujących opcji `cppdbg` . W programie Visual Studio 2019 w wersji 16,6 lub nowszej `cppgdb` jest zalecany typ konfiguracji.

- `name`: Przyjazna nazwa identyfikująca konfigurację na liście rozwijanej **elementu startowego** .

- `project`: Określa ścieżkę względną do pliku projektu. Zwykle nie trzeba zmieniać tej wartości podczas debugowania projektu CMake.

- `projectTarget`: Określa element docelowy CMake, który ma zostać wywołany podczas kompilowania projektu. Program Visual Studio automatycznie wypełnia tę właściwość, jeśli wprowadzasz *polecenielaunch.vs.jsw* **menu Debugowanie** lub **widoku elementów docelowych** . Ta wartość musi być zgodna z nazwą istniejącego elementu docelowego debugowania wyświetlaną na liście rozwijanej **elementu startowego** .

- `args`: Argumenty wiersza polecenia przekazane podczas uruchamiania do debugowanego programu.

- `processID`: Identyfikator procesu systemu Linux do dołączenia. Używany tylko podczas dołączania do procesu zdalnego. Aby uzyskać więcej informacji, zobacz [Rozwiązywanie problemów z dołączaniem do procesów przy użyciu GDB](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB).

- `program`: Domyślnie `"${debugInfo.fullTargetPath}"` . Ścieżka systemu UNIX do aplikacji do debugowania. Wymagany tylko wtedy, gdy jest inny niż docelowy plik wykonywalny w lokalizacji kompilacji lub wdrożenia.

- `remoteMachineName`: Domyślnie `"${debugInfo.remoteMachineName}"` . Nazwa systemu zdalnego, który hostuje program do debugowania. Wymagane tylko w przypadku, gdy różni się od systemu kompilacji. Musi mieć istniejący wpis w [Menedżerze połączeń](../linux/connect-to-your-remote-linux-computer.md). Naciśnij **klawisze CTRL + SPACJA** , aby wyświetlić listę wszystkich istniejących połączeń zdalnych.

- `cwd`: Domyślnie `"${debugInfo.defaultWorkingDirectory}"` . Pełna ścieżka systemu UNIX do katalogu w systemie zdalnym, gdzie `program` jest uruchomiony. Ten katalog musi istnieć.

- `environment`: Dodatkowe zmienne środowiskowe przechodzą do debugowanego programu. Przykład:

  ```json
    "environment": [
        {
          "name": "ENV1",
          "value": "envvalue1"
        },
        {
          "name": "ENV2",
          "value": "envvalue2"
        }
      ]
  ```

- `pipeArgs`: Tablica argumentów wiersza polecenia przenoszona do programu potoku w celu skonfigurowania połączenia. Program potoku służy do przekazywania standardowych danych wejściowych/wyjściowych między programem Visual Studio i programem `gdb` . Większość tej tablicy **nie należy dostosowywać** podczas debugowania projektów CMAKE. Wyjątkiem jest `${debuggerCommand}` , który jest uruchamiany `gdb` w systemie zdalnym. Można go zmodyfikować, aby:

  - Wyeksportuj wartość zmiennej środowiskowej WYŚWIETLAnej w systemie Linux. W poniższym przykładzie ta wartość jest `:1` .

    ```json
    "pipeArgs": [
        "/s",
        "${debugInfo.remoteMachineId}",
        "/p",
        "${debugInfo.parentProcessId}",
        "/c",
        "export DISPLAY=:1;${debuggerCommand}",
        "--tty=${debugInfo.tty}"
      ],
    ```

  - Uruchom skrypt przed wykonaniem operacji `gdb` . Upewnij się, że w skrypcie są ustawione uprawnienia do wykonywania.

    ```json
    "pipeArgs": [
        "/s",
        "${debugInfo.remoteMachineId}",
        "/p",
        "${debugInfo.parentProcessId}",
        "/c",
        "/path/to/script.sh;${debuggerCommand}",
        "--tty=${debugInfo.tty}"
      ],
    ```

- `stopOnEntry`: Wartość logiczna określająca, czy ma zostać przerwana zaraz po uruchomieniu procesu. Wartością domyślną jest false.

- `visualizerFile`: [Plik. Natvis](/visualstudio/debugger/create-custom-views-of-native-objects) do użycia podczas debugowania tego procesu. Ta opcja jest niezgodna z funkcją `gdb` drukowania przez. Ustawia się również `showDisplayString` podczas ustawiania tej właściwości.

- `showDisplayString`: Wartość logiczna, która włącza ciąg wyświetlania, gdy `visualizerFile` jest określony. Ustawienie tej opcji **`true`** może spowodować wolniejszą wydajność podczas debugowania.

- `setupCommands`: Co najmniej jedno `gdb` polecenie (s) do wykonania, aby skonfigurować podstawowy debuger.

- `miDebuggerPath`: Pełna ścieżka do `gdb` . Gdy nie zostanie określony, program Visual Studio szuka najpierw ścieżki dla debugera.

- Na koniec wszystkie opcje wdrażania zdefiniowane dla danego `cppgdb` typu konfiguracji mogą również być używane przez `cppdbg` Typ konfiguracji.

### <a name="debug-using-gdbserver"></a>Debuguj przy użyciu `gdbserver`

Konfigurację można skonfigurować `cppdbg` do debugowania przy użyciu programu `gdbserver` . Więcej szczegółów i przykładową konfigurację uruchamiania można znaleźć w blogu zespołu języka Microsoft C++ [debugowanie CMAKE projekty w `gdbserver` systemie Linux ](https://devblogs.microsoft.com/cppblog/debugging-linux-cmake-projects-with-gdbserver/).

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="see-also"></a>Zobacz także

[CMake projekty w programie Visual Studio](cmake-projects-in-visual-studio.md)\
[Konfigurowanie projektu CMake systemu Linux](../linux/cmake-linux-project.md)\
[Nawiązywanie połączenia ze zdalnym komputerem z systemem Linux](../linux/connect-to-your-remote-linux-computer.md)\
[Dostosuj ustawienia kompilacji CMake](customize-cmake-settings.md)\
[Konfigurowanie sesji debugowania CMake](configure-cmake-debugging-sessions.md)\
[Wdrażanie, uruchamianie i debugowanie projektu systemu Linux](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake wstępnie zdefiniowanej konfiguracji](cmake-predefined-configuration-reference.md)

::: moniker-end

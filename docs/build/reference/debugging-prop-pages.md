---
description: 'Dowiedz się więcej na temat: strony właściwości debugowania C++'
title: Strony właściwości debugowania języka C++
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 78115a6b-3799-4515-814e-8566b5bdc55d
f1_keywords:
- VC.Project.IVCLocalDebugPageObject.Command
- VC.Project.IVCLocalDebugPageObject.CommandArguments
- VC.Project.IVCLocalDebugPageObject.WorkingDirectory
- VC.Project.IVCLocalDebugPageObject.Attach
- VC.Project.IVCLocalDebugPageObject.DebuggerType
- VC.Project.IVCLocalDebugPageObject.Environment
- VC.Project.IVCLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCLocalDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCLocalDebugPageObject.EnvironmentMerge
- VC.Project.IVCLocalDebugPageObject.SQLDebugging
- VC.Project.IVCLocalDebugPageObject.AmpDefaultAccelerator
- VC.Project.IVCRemoteDebugPageObject.RemoteCommand
- VC.Project.IVCRemoteDebugPageObject.CommandArguments
- VC.Project.IVCRemoteDebugPageObject.WorkingDirectory
- VC.Project.IVCRemoteDebugPageObject.RemoteMachine
- VC.Project.IVCRemoteDebugPageObject.Remote
- VC.Project.IVCRemoteDebugPageObject.DebuggerType
- VC.Project.IVCRemoteDebugPageObject.Environment
- VC.Project.IVCRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCRemoteDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCRemoteDebugPageObject.Attach
- VC.Project.IVCRemoteDebugPageObject.SQLDebugging
- VC.Project.IVCRemoteDebugPageObject.DeploymentDirectory
- VC.Project.IVCRemoteDebugPageObject.AdditionalFiles
- VC.Project.IVCRemoteDebugPageObject.Remote
- VC.Project.IVCRemoteDebugPageObject.AmpDefaultAccelerator
- VC.Project.VCDebugSettings.WebBrowser.WebBrowserDebuggerHttpUrl
- VC.Project.VCDebugSettings.WebBrowser.DebuggerType
- VC.Project.IVCWebSvcDebugPageObject.HttpUrl
- VC.Project.IVCWebSvcDebugPageObject.DebuggerType
- VC.Project.IVCWebSvcDebugPageObject.SQLDebugging
ms.openlocfilehash: 16a7fec317485dd20a430baab9a413586f913fa3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201745"
---
# <a name="c-debugging-property-pages"></a>Strony właściwości debugowania języka C++

Te strony właściwości są dostępne we właściwościach **projektu**  >    >    >  **debugowanie** właściwości. Wybierz typ debugera w kontrolce listy rozwijanej. Aby uzyskać więcej informacji na temat debugowania kodu C++, zobacz [Samouczek: informacje na temat debugowania kodu c++ przy użyciu programu Visual Studio](/visualstudio/debugger/getting-started-with-the-debugger-cpp) i [debugowania kodu natywnego](/visualstudio/debugger/debugging-native-code).

## <a name="local-windows-debugger-property-page"></a>Strona właściwości lokalnego debugera systemu Windows

### <a name="command"></a>Polecenie

Polecenie debugowania do wykonania.

### <a name="command-arguments"></a>Argumenty polecenia

Argumenty wiersza polecenia do przekazania do aplikacji.

### <a name="working-directory"></a>Katalog roboczy

Katalog roboczy aplikacji. Domyślnie katalog zawierający plik projektu.

### <a name="attach"></a>Dołącz

Określa, czy debuger powinien podjąć próbę dołączenia do istniejącego procesu, gdy debugowanie rozpocznie się.

### <a name="debugger-type"></a>Typ debugera

Określa typ debugera do użycia. Po ustawieniu na wartość autodebuger typ zostanie wybrany na podstawie zawartości pliku exe.

**Choices**

- Tylko **natywny** — tylko natywny
- **Tylko zarządzane** — tylko zarządzane
- **Mieszany** — mieszany
- **Autowybieranie**
- **Skrypt — skrypt**
- **Tylko procesor GPU (C++ amp)** — tylko procesor gpu (C++ amp)

### <a name="environment"></a>Środowisko

Określa środowisko do debugowania programu lub zmienne, które mają zostać scalone z istniejącym środowiskiem.

### <a name="debugging-accelerator-type"></a>Typ akceleratora debugowania

Typ akceleratora debugowania, który ma być używany do debugowania kodu GPU. (Dostępne, gdy debuger GPU jest aktywny).

### <a name="gpu-default-breakpoint-behavior"></a>Domyślne zachowanie punktu przerwania procesora GPU

Ustawia częstotliwość przerwy między debugerem GPU.

**Choices**

- **Przerwij raz na wypaczenie** , raz na osnowę
- **Przerwij dla każdego wątku (takie jak zachowanie procesora CPU)** — Przerwij dla każdego wątku (takie jak zachowanie procesora CPU)

### <a name="merge-environment"></a>Scal środowisko

Scala określone zmienne środowiskowe z istniejącym środowiskiem.

### <a name="sql-debugging"></a>Debugowanie SQL

Dołącz debuger SQL.

### <a name="amp-default-accelerator"></a>Akcelerator domyślny amp

Zastąp domyślny wybór akceleratora C++ AMP. Właściwość nie ma zastosowania podczas debugowania kodu zarządzanego.

## <a name="remote-windows-debugger-property-page"></a>Strona właściwości zdalnego debugera systemu Windows

Aby uzyskać więcej informacji na temat debugowania zdalnego, zobacz [debugowanie zdalne projektu Visual C++ w programie Visual Studio](/visualstudio/debugger/remote-debugging-cpp).

### <a name="remote-command"></a>Polecenie zdalne

Polecenie debugowania do wykonania.

### <a name="remote-command-arguments"></a>Argumenty polecenia zdalnego

Argumenty wiersza polecenia do przekazania do aplikacji.

### <a name="working-directory"></a>Katalog roboczy

Katalog roboczy aplikacji. Domyślnie katalog zawierający plik projektu.

### <a name="remote-server-name"></a>Nazwa serwera zdalnego

Określa nazwę serwera zdalnego.

### <a name="connection"></a>Połączenie

Określa typ połączenia.

**Choices**

- **Zdalne z uwierzytelnianiem systemu Windows** — zdalne z [uwierzytelnianiem systemu Windows](/windows-server/security/windows-authentication/windows-authentication-overview).
- **Zdalne bez uwierzytelniania** — zdalne i bez uwierzytelniania.

### <a name="debugger-type"></a>Typ debugera

Określa typ debugera do użycia. Po ustawieniu na wartość autodebuger typ zostanie wybrany na podstawie zawartości pliku exe.

**Choices**

- Tylko **natywny** — tylko natywny
- **Tylko zarządzane** — tylko zarządzane
- **Mieszany** — mieszany
- **Autowybieranie**
- **Skrypt — skrypt**
- **Tylko procesor GPU (C++ amp)** — tylko procesor gpu (C++ amp)

### <a name="environment"></a>Środowisko

Określa środowisko do debugowania programu lub zmienne, które mają zostać scalone z istniejącym środowiskiem.

### <a name="debugging-accelerator-type"></a>Typ akceleratora debugowania

Typ akceleratora debugowania, który ma być używany do debugowania kodu GPU. (Dostępne, gdy debuger GPU jest aktywny).

### <a name="gpu-default-breakpoint-behavior"></a>Domyślne zachowanie punktu przerwania procesora GPU

Ustawia częstotliwość przerwy między debugerem GPU.

**Choices**

- **Przerwij raz na wypaczenie** , raz na osnowę
- **Przerwij dla każdego wątku (takie jak zachowanie procesora CPU)** — Przerwij dla każdego wątku (takie jak zachowanie procesora CPU)

### <a name="attach"></a>Dołącz

Określa, czy debuger powinien podjąć próbę dołączenia do istniejącego procesu, gdy debugowanie rozpocznie się.

### <a name="sql-debugging"></a>Debugowanie SQL

Dołącz debuger SQL.

### <a name="deployment-directory"></a>Katalog wdrażania

W przypadku debugowania na komputerze zdalnym, jeśli chcesz, aby zawartość danych wyjściowych projektu (z wyjątkiem plików PDB) była kopiowana do maszyny zdalnej, określ tutaj ścieżkę.

### <a name="additional-files-to-deploy"></a>Dodatkowe pliki do wdrożenia

Podczas debugowania na maszynie zdalnej pliki i katalogi określone tutaj (oprócz danych wyjściowych projektu) są kopiowane do katalogu wdrażania, jeśli został on określony.

### <a name="deploy-visual-c-debug-runtime-libraries"></a>Wdróż biblioteki środowiska uruchomieniowego debugowania Visual C++

Określa, czy wdrożyć biblioteki środowiska uruchomieniowego debugowania dla aktywnej platformy (Win32, x64 lub ARM).

### <a name="amp-default-accelerator"></a>Akcelerator domyślny amp

Zastąp domyślny wybór akceleratora C++ AMP. Właściwość nie ma zastosowania podczas debugowania kodu zarządzanego.

## <a name="web-browser-debugger-property-page"></a>Strona właściwości debugera przeglądarki sieci Web

### <a name="http-url"></a>ADRES URL HTTP

Określa adres URL projektu.

### <a name="debugger-type"></a>Typ debugera

Określa typ debugera do użycia. Po ustawieniu na wartość autodebuger typ zostanie wybrany na podstawie zawartości pliku exe.

**Choices**

- Tylko **natywny** — tylko natywny
- **Tylko zarządzane** — tylko zarządzane
- **Mieszany** — mieszany
- **Autowybieranie**
- **Skrypt — skrypt**

## <a name="web-service-debugger-property-page"></a>Strona właściwości debugera usługi sieci Web

### <a name="http-url"></a>ADRES URL HTTP

Określa adres URL projektu.

### <a name="debugger-type"></a>Typ debugera

Określa typ debugera do użycia. Po ustawieniu na wartość autodebuger typ zostanie wybrany na podstawie zawartości pliku exe.

**Choices**

- Tylko **natywny** — tylko natywny
- **Tylko zarządzane** — tylko zarządzane
- **Mieszany** — mieszany
- **Autowybieranie**
- **Skrypt — skrypt**

### <a name="sql-debugging"></a>Debugowanie SQL

Dołącz debuger SQL.

---
description: Dowiedz się więcej na temat:/VERBOSE (drukowanie komunikatów o postępie)
title: /VERBOSE (Drukuj komunikaty o postępie)
ms.date: 06/13/2019
f1_keywords:
- /verbose
- VC.Project.VCLinkerTool.ShowProgress
helpviewer_keywords:
- -VERBOSE linker option
- linking [C++], session progress information
- Print Progress Messages linker option
- linker [C++], output dependency information
- /VERBOSE linker option
- dependencies [C++], dependency information in linker output
- VERBOSE linker option
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
ms.openlocfilehash: 9d1a22a1b05f42a707b2449fbb114ba06db85ff5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176421"
---
# <a name="verbose-print-progress-messages"></a>/VERBOSE (Drukuj komunikaty o postępie)

Wyświetla komunikaty o postępie podczas procesu linku.

## <a name="syntax"></a>Składnia

> **/Verbose** \[ **:**{**CLR** | **ICF** | **incr** | **lib** | **ref** |  | **UNUSEDDELAYLOAD** | **UNUSEDLIBS**}\]

## <a name="remarks"></a>Uwagi

Konsolidator wysyła informacje o postępie sesji łączenia do okna **danych wyjściowych** . W wierszu polecenia informacje są wysyłane do wyjścia standardowego i mogą być przekierowywane do pliku.

| Opcja | Opis |
| ------------ | ----------------- |
| /VERBOSE | Wyświetla szczegółowe informacje o procesie łączenia. |
| /VERBOSE: ŚRODOWISKO CLR | Wyświetla informacje o działaniu konsolidatora specyficznym dla obiektów i metadanych skompilowanych za pomocą [/CLR](clr-common-language-runtime-compilation.md). |
| /VERBOSE: ICF | Wyświetla informacje o działaniu konsolidatora, które wynikają z używania [/OPT: ICF](opt-optimizations.md). |
| /VERBOSE: INCR | Wyświetla informacje o procesie linku przyrostowego. |
| /VERBOSE: LIB | Wyświetla komunikaty o postępie wskazujące tylko przeszukiwane biblioteki.<br/> Wyświetlane informacje obejmują proces wyszukiwania biblioteki. Zawiera listę wszystkich bibliotek i nazw obiektów (z pełną ścieżką), symbol rozpoznawany z biblioteki oraz listę obiektów odwołujących się do symbolu. |
| /VERBOSE: REF | Wyświetla informacje o działaniu konsolidatora, które wynikają z użycia [/OPT: ref](opt-optimizations.md). |
| /VERBOSE: SAFESEH | Wyświetla informacje o modułach, które są niezgodne z bezpieczną strukturalną obsługą wyjątków, gdy nie określono [/SAFESEH](safeseh-image-has-safe-exception-handlers.md) . |
| /VERBOSE: UNUSEDDELAYLOAD | Wyświetla informacje o wszelkich załadowanej z opóźnieniem bibliotek DLL, które nie mają symboli używanych podczas tworzenia obrazu. |
| /VERBOSE: UNUSEDLIBS | Wyświetla informacje o wszystkich plikach bibliotek, które nie są używane podczas tworzenia obrazu. |

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **Konfiguracja właściwości**  >    >  **wiersza polecenia** konsolidatora.

1. Dodaj opcję do pola **dodatkowe opcje** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

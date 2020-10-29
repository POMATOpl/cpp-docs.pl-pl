---
title: /QIntel-jcc-erratum
description: Opisuje opcję/QIntel-jcc-erratum kompilatora Microsoft C/C++ (MSVC).
ms.date: 01/07/2020
f1_keywords:
- QIntel-jcc-erratum
helpviewer_keywords:
- /QIntel-jcc-erratum
- -QIntel-jcc-erratum
ms.openlocfilehash: c66dd4bb25647ce193bce4db5dc4ebb1268277c0
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921376"
---
# <a name="qintel-jcc-erratum"></a>/QIntel-jcc-erratum

::: moniker range="<=msvc-150"

Opcja **/QIntel-JCC-Erratum** jest dostępna w programie Visual Studio 2019 w wersji 16,5 lub nowszej.

::: moniker-end

::: moniker range=">=msvc-160"

Określa, że kompilator generuje instrukcje w celu ograniczenia wpływu na wydajność spowodowany przez kod warunkowy Intel skoku (JCC) sprawdzenia erraty włączenia mikrokodu Update w niektórych procesorach Intel.

## <a name="syntax"></a>Składnia

> **/QIntel-jcc-erratum**

## <a name="remarks"></a>Uwagi

W obszarze **/QIntel-JCC-Erratum** kompilator wykrywa Instrukcje skoku i odrzucania makr, które przecinają się lub kończą na 32-bajtowych granicach. Wyrównuje te instrukcje do granicy. Ta zmiana zmniejsza wpływ na wydajność aktualizacji włączenia mikrokodu, które uniemożliwiają JCC sprawdzenia erraty w niektórych procesorach Intel. Aby uzyskać więcej informacji na temat sprawdzenia erraty, zobacz środki [zaradcze dla sprawdzenia erraty kodu warunkowego](https://www.intel.com/content/dam/support/us/en/documents/processors/mitigations-jump-conditional-code-erratum.pdf) w witrynie sieci Web firmy Intel.

Opcja **/QIntel-JCC-Erratum** jest dostępna w programie Visual Studio 2019 w wersji 16,5 lub nowszej. Ta opcja jest dostępna tylko w kompilatorach przeznaczonych dla procesorów x86 i x64. Opcja jest niedostępna w kompilatorach przeznaczonych dla procesorów ARM.

Opcja **/QIntel-JCC-Erratum** jest domyślnie wyłączona i działa tylko w zoptymalizowanych kompilacjach. Ta opcja umożliwia zwiększenie rozmiaru kodu.

**/QIntel-JCC-Erratum** jest niezgodny z [/CLR](clr-common-language-runtime-compilation.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz **Configuration Properties** > stronę właściwości konfiguracja generowania kodu **C/C++** > **Code Generation** .

1. Wybierz wartość właściwości **enable Intel JCC sprawdzenia erraty** . Wybierz **przycisk OK** , aby zastosować zmianę.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz także

[/Q opcje (operacje na niskim poziomie)](q-options-low-level-operations.md)\
[Opcje kompilatora MSVC](compiler-options.md)\
[Składnia wiersza polecenia kompilatora MSVC](compiler-command-line-syntax.md)

::: moniker-end

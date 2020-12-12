---
description: Dowiedz się więcej na temat:/arch (ARM)
title: /arch (ARM)
ms.date: 11/04/2016
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
ms.openlocfilehash: 885b624eb6a470d24d691641d0be63515ee76a49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179567"
---
# <a name="arch-arm"></a>/arch (ARM)

Określa architekturę generowania kodu w usłudze ARM. Zobacz również [/arch (x86)](arch-x86.md) i [/arch (x64)](arch-x64.md).

## <a name="syntax"></a>Składnia

```
/arch:[ARMv7VE|VFPv4]
```

## <a name="arguments"></a>Argumenty

**/arch: ARMv7VE**<br/>
Umożliwia korzystanie z instrukcji rozszerzeń wirtualizacji ARMv7VE.

**/arch: VFPv4**<br/>
Umożliwia korzystanie z instrukcji ARM VFPv4. Jeśli ta opcja nie jest określona, VFPv3 jest wartością domyślną.

## <a name="remarks"></a>Uwagi

`_M_ARM_FP`Makro (tylko dla ARM) wskazuje, które, w przypadku użycia opcji kompilatora **/Arch** . Aby uzyskać więcej informacji, zobacz [wstępnie zdefiniowane makra](../../preprocessor/predefined-macros.md).

W przypadku użycia opcji [/CLR](clr-common-language-runtime-compilation.md) do kompilowania **/Arch** nie ma wpływu na generowanie kodu dla funkcji zarządzanych. **/Arch** ma wpływ tylko na generowanie kodu dla funkcji natywnych.

### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Aby ustawić/arch: ARMv7VE lub/arch: VFPv4 — opcja kompilatora w programie Visual Studio

1. Otwórz okno dialogowe **strony właściwości** dla projektu. Aby uzyskać więcej informacji, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **C/C++** .

1. Wybierz stronę właściwości **wiersza polecenia** .

1. W polu **dodatkowe opcje** Dodaj `/arch:ARMv7VE` lub `/arch:VFPv4` .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Zobacz też

[/arch (minimalna architektura procesora CPU)](arch-minimum-cpu-architecture.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)

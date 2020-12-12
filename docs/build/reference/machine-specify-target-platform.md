---
description: Dowiedz się więcej o:/MACHINE (Określ platformę docelową)
title: /MACHINE (Określ platformę docelową)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TargetMachine
- /machine
helpviewer_keywords:
- mapfiles, creating linker
- target platform
- -MACHINE linker option
- /MACHINE linker option
- MACHINE linker option
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
ms.openlocfilehash: a1bf87142fb99577672391356a43a2771ea0b09f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190812"
---
# <a name="machine-specify-target-platform"></a>/MACHINE (Określ platformę docelową)

```
/MACHINE:{ARM|EBC|X64|X86}
```

## <a name="remarks"></a>Uwagi

Opcja/MACHINE określa docelową platformę dla programu.

Zwykle nie trzeba określać opcji/MACHINE. LINK wnioskuje typ maszyny z plików. obj. Jednak w niektórych okolicznościach LINK nie może określić typu maszyny i wystawia [błąd narzędzia konsolidatora LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md). Jeśli wystąpi błąd, określ/MACHINE.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **Zaawansowane** .

1. Zmodyfikuj właściwość **maszyny docelowej** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

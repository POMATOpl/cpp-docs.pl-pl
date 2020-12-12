---
description: Dowiedz się więcej o:/RELEASE (Ustaw sumę kontrolną)
title: /RELEASE (Ustaw sumę kontrolną)
ms.date: 11/04/2016
f1_keywords:
- /release
- VC.Project.VCLinkerTool.SetChecksum
helpviewer_keywords:
- -RELEASE linker option
- /RELEASE linker option
- checksum setting
- RELEASE linker option
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
ms.openlocfilehash: ed1e55dffb02ace26e91e262bd3e9514f056196e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225326"
---
# <a name="release-set-the-checksum"></a>/RELEASE (Ustaw sumę kontrolną)

```
/RELEASE
```

## <a name="remarks"></a>Uwagi

Opcja/RELEASE ustawia sumę kontrolną w nagłówku pliku. exe.

System operacyjny wymaga sumy kontrolnej dla sterowników urządzeń. Ustaw sumę kontrolną dla wersji wydań sterowników urządzeń, aby zapewnić zgodność z przyszłymi systemami operacyjnymi.

Opcja/RELEASE jest domyślnie ustawiona, gdy jest określona opcja [/SUBSYSTEM: Native](subsystem-specify-subsystem.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **Zaawansowane** .

1. Modyfikuj Właściwość **Ustaw sumę kontrolną** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

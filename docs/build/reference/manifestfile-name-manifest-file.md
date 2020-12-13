---
description: Dowiedz się więcej o:/MANIFESTFILE (Nazwij plik manifestu)
title: /MANIFESTFILE (Podaj nazwę pliku manifestu)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ManifestFile
helpviewer_keywords:
- MANIFESTFILE linker option
- -MANIFESTFILE linker option
- /MANIFESTFILE linker option
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
ms.openlocfilehash: a0d3a4ba1d17c4aa8c97cb09cc768e614e46c864
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138024"
---
# <a name="manifestfile-name-manifest-file"></a>/MANIFESTFILE (Podaj nazwę pliku manifestu)

```
/MANIFESTFILE:filename
```

## <a name="remarks"></a>Uwagi

/MANIFESTFILE pozwala zmienić domyślną nazwę pliku manifestu.  Domyślną nazwą pliku manifestu jest nazwa pliku z dołączonym manifestem.

/MANIFESTFILE nie będzie działać, jeśli nie zostanie również połączony z [/manifest](manifest-create-side-by-side-assembly-manifest.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji** .

1. Rozwiń węzeł **konsolidatora** .

1. Wybierz stronę właściwości **plik manifestu** .

1. Zmodyfikuj właściwość **pliku manifestu** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

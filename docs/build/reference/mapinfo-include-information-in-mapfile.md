---
description: Dowiedz się więcej na temat:/MAPINFO (Dołącz informacje do Mapfile)
title: /MAPINFO (Dołącz informacje do Mapfile)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.MapLines
- VC.Project.VCLinkerTool.MapInfoFixups
- VC.Project.VCLinkerTool.MapExports
- /mapinfo
helpviewer_keywords:
- /MAPINFO linker option
- MAPINFO linker option
- -MAPINFO linker option
ms.assetid: 533d2bce-f9b7-4fea-ae1c-0b4864c9d10b
ms.openlocfilehash: 5cf785182bd91923c3398d542d7e60d9afdb4a4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137907"
---
# <a name="mapinfo-include-information-in-mapfile"></a>/MAPINFO (Dołącz informacje do Mapfile)

```
/MAPINFO:EXPORTS
```

## <a name="remarks"></a>Uwagi

Opcja/MAPINFO nakazuje konsolidatorowi dołączenie określonych informacji do Mapfile, który jest tworzony w przypadku określenia opcji [/map](map-generate-mapfile.md) .  EKSPORTy nakazuje konsolidatorowi uwzględnienie wyeksportowanych funkcji.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **debugowania** .

1. Modyfikowanie właściwości **eksportu mapy** :

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapExports%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

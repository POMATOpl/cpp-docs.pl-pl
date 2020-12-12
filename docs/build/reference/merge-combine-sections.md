---
description: Dowiedz się więcej na temat:/MERGE (Połącz sekcje)
title: /MERGE (Połącz sekcje)
ms.date: 11/04/2016
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
ms.openlocfilehash: 579e5432facd6deb8d2b26b997d9b61f167d2b3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199106"
---
# <a name="merge-combine-sections"></a>/MERGE (Połącz sekcje)

```
/MERGE:from=to
```

## <a name="remarks"></a>Uwagi

Opcja/MERGE łączy pierwszą sekcję (*od*) z drugą sekcją (*do*), nazywaną sekcją *.* Na przykład `/merge:.rdata=.text`.

Jeśli druga sekcja nie istnieje, LINK zmienia nazwę sekcji *z* *na*.

Opcja/MERGE jest przydatna do tworzenia VxDs i przesłaniania nazw sekcji generowanych przez kompilator.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **Zaawansowane** .

1. Zmodyfikuj właściwość **scalone sekcje** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

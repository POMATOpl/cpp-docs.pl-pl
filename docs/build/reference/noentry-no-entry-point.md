---
description: Dowiedz się więcej o:/NOENTRY (brak punktu wejścia)
title: /NOENTRY (Brak punktu wejścia)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
ms.openlocfilehash: c3d1f725a4e185a052d443010894ff2dc2261675
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196688"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (Brak punktu wejścia)

```
/NOENTRY
```

## <a name="remarks"></a>Uwagi

Opcja/NOENTRY jest wymagana do utworzenia biblioteki DLL zawierającej tylko zasoby, która nie zawiera kodu wykonywalnego. Aby uzyskać więcej informacji, zobacz [tworzenie Resource-Only dll](../creating-a-resource-only-dll.md).

Użyj tej opcji, aby zapobiec łączeniu łącza z odwołaniem do `_main` biblioteki DLL.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **konsolidatora** .

1. Wybierz stronę właściwości **Zaawansowane** .

1. Zmodyfikuj właściwość **Brak punktu wejścia** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.

## <a name="see-also"></a>Zobacz też

[Tworzenie Resource-Only DLL](../creating-a-resource-only-dll.md)<br/>
[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

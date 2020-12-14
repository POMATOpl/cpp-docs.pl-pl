---
description: Dowiedz się więcej na temat:/DEF (Określ plik Module-Definition)
title: /DEF (Określ plik definicji modułu)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
ms.openlocfilehash: 3b9178004621a55f999f7c2636eaa5b697d2de98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201706"
---
# <a name="def-specify-module-definition-file"></a>/DEF (Określ plik definicji modułu)

```
/DEF:filename
```

## <a name="arguments"></a>Argumenty

*Nazwa pliku*<br/>
Nazwa pliku definicji modułu (. def), która ma zostać przeniesiona do konsolidatora.

## <a name="remarks"></a>Uwagi

Opcja/DEF przekazuje plik definicji modułu (. def) do konsolidatora. Tylko jeden plik. def może być określony do łączenia. Aby uzyskać szczegółowe informacje na temat plików. def, zobacz [pliki definicji modułów](module-definition-dot-def-files.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **dane wejściowe** .

1. Zmodyfikuj właściwość **pliku definicji modułu** .

Aby określić plik. def w środowisku deweloperskim, należy dodać go do projektu wraz z innymi plikami, a następnie określić plik jako opcję/DEF.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

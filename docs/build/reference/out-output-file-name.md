---
description: Dowiedz się więcej o:/OUT (nazwa pliku wyjściowego)
title: /OUT (Nazwa pliku wyjściowego)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
ms.openlocfilehash: 1773b4b2dd340bc105495c1b05211c018548976f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226405"
---
# <a name="out-output-file-name"></a>/OUT (Nazwa pliku wyjściowego)

```
/OUT:filename
```

## <a name="arguments"></a>Argumenty

*Nazwa pliku*<br/>
Nazwa pliku wyjściowego określona przez użytkownika. Zastępuje domyślną nazwę.

## <a name="remarks"></a>Uwagi

Opcja/OUT zastępuje domyślną nazwę i lokalizację programu tworzonego przez konsolidatora.

Domyślnie konsolidator tworzy nazwę pliku przy użyciu nazwy bazowej pierwszego określonego pliku. obj i odpowiedniego rozszerzenia (exe lub dll).

Ta opcja jest domyślną nazwą podstawową dla biblioteki. mapfile lub importu. Aby uzyskać szczegółowe informacje, zobacz [generowanie mapfile](map-generate-mapfile.md) (/map) i [/IMPLIB](implib-name-import-library.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **Ogólne** .

1. Zmodyfikuj właściwość **pliku wyjściowego** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

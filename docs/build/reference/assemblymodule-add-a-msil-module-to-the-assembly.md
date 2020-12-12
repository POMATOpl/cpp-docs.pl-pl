---
description: Dowiedz się więcej o:/ASSEMBLYMODULE (Dodaj moduł MSIL do zestawu)
title: /ASSEMBLYMODULE (Dodaj moduł MSIL do zestawu)
ms.date: 11/04/2016
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
ms.openlocfilehash: d56895b6bec05efda1104e319e93a040f818e06e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182947"
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (Dodaj moduł MSIL do zestawu)

```
/ASSEMBLYMODULE:filename
```

## <a name="arguments"></a>Argumenty

*Nazwa pliku*<br/>
Moduł, który ma zostać uwzględniony w tym zestawie.

## <a name="remarks"></a>Uwagi

Opcja/ASSEMBLYMODULE umożliwia dodanie odwołania modułu do zestawu. Informacje o typie w module nie będą dostępne dla programu zestawu, który dodał odwołanie do modułu. Jednak informacje o typie w module będą dostępne dla każdego programu, który odwołuje się do zestawu.

Użyj [#using](../../preprocessor/hash-using-directive-cpp.md) , aby dodać odwołanie do modułu do zestawu i udostępnić informacje o typie modułu dla programu zestawu.

Na przykład rozważmy następujący scenariusz:

1. Utwórz moduł z [/LN](ln-create-msil-module.md).

1. Użyj/ASSEMBLYMODULE w innym projekcie w celu uwzględnienia modułu w bieżącej kompilacji, który spowoduje utworzenie zestawu. Ten projekt nie będzie odwoływać się do modułu za pomocą `#using` .

1. Każdy projekt odwołujący się do tego zestawu może teraz również używać typów z modułu.

Inne Opcje konsolidatora, które wpływają na generowanie zestawu, to:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

MSVC konsolidator akceptuje pliki. module jako dane wejściowe i plik wyjściowy utworzony przez konsolidator będzie zestawem lub modułem, który nie jest zależny od czasu wykonywania w żadnym z modułów.  Aby uzyskać więcej informacji, zobacz [. moduły plików jako dane wejściowe konsolidatora](netmodule-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **dane wejściowe** .

1. Zmodyfikuj właściwość **Dodaj moduł do zestawu** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

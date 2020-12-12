---
description: Dowiedz się więcej o:/KEYCONTAINER (Określ kontener klucza do podpisania zestawu)
title: /KEYCONTAINER (Określ klucz kontenera, aby podpisać zestaw)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
ms.openlocfilehash: 5f32fdc5400103d4038139fa2dfe9409c9740236
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199587"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (Określ klucz kontenera, aby podpisać zestaw)

```
/KEYCONTAINER:name
```

## <a name="arguments"></a>Argumenty

*Nazwij*<br/>
Kontener, który zawiera klucz. Umieść ciąg w podwójnym cudzysłowie (""), jeśli zawiera spację.

## <a name="remarks"></a>Uwagi

Konsolidator tworzy podpisany zestaw przez wstawianie klucza publicznego do manifestu zestawu i podpisywanie końcowego zestawu przy użyciu klucza prywatnego. Aby wygenerować plik klucza, wpisz [SN-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* w wierszu polecenia. **SN —** instaluje parę kluczy w kontenerze.

W przypadku kompilowania z [/LN](ln-create-msil-module.md)nazwa pliku klucza jest przechowywana w module i dołączona do zestawu, który jest tworzony podczas kompilowania zestawu, który zawiera jawne odwołanie do modułu, za pośrednictwem [#using](../../preprocessor/hash-using-directive-cpp.md)lub podczas łączenia z [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md).

Możesz również przekazać informacje o szyfrowaniu do kompilatora za pomocą [/KeyFile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md). Użyj [/delaysign](delaysign-partially-sign-an-assembly.md) , jeśli chcesz użyć częściowo podpisanego zestawu. Zobacz [zestawy o silnych nazwach (podpisywanie zestawów) (C++/CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) , aby uzyskać więcej informacji na temat podpisywania zestawu.

Inne Opcje konsolidatora, które wpływają na generowanie zestawu, to:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję w polu **dodatkowe opcje** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

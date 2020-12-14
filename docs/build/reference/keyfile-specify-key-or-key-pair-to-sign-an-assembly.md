---
description: Dowiedz się więcej o:/KEYFILE (Określ klucz lub parę kluczy, aby podpisać zestaw)
title: /KEYFILE (Określ klucz lub parę kluczy, aby podpisać zestaw)
ms.date: 11/04/2016
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
ms.openlocfilehash: 23c4962ab57688f5d8c1af27fd412d7d36be01a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191163"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE (Określ klucz lub parę kluczy, aby podpisać zestaw)

```
/KEYFILE:filename
```

## <a name="arguments"></a>Argumenty

*Nazwa pliku*<br/>
Plik, który zawiera klucz. Umieść ciąg w podwójnym cudzysłowie (""), jeśli zawiera spację.

## <a name="remarks"></a>Uwagi

Konsolidator wstawia klucz publiczny do manifestu zestawu, a następnie podpisuje końcowy zestaw kluczem prywatnym. Aby wygenerować plik klucza, wpisz [SN-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* w wierszu polecenia. Podpisany zestaw ma silną nazwę.

W przypadku kompilowania z [/LN](ln-create-msil-module.md)nazwa pliku klucza jest przechowywana w module i dołączona do zestawu, który jest tworzony podczas kompilowania zestawu, który zawiera jawne odwołanie do modułu, za pośrednictwem [#using](../../preprocessor/hash-using-directive-cpp.md)lub podczas łączenia z [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md).

Możesz również przekazać informacje o szyfrowaniu do konsolidatora przy użyciu [/keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md). Użyj [/delaysign](delaysign-partially-sign-an-assembly.md) , jeśli chcesz użyć częściowo podpisanego zestawu. Zobacz [zestawy o silnych nazwach (podpisywanie zestawów) (C++/CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) , aby uzyskać więcej informacji na temat podpisywania zestawu.

Jeśli **/KeyFile** i **/keycontainer** są określone (za pomocą opcji wiersza polecenia lub przez atrybut niestandardowy), konsolidator najpierw spróbuje kontener kluczy. Jeśli to się powiedzie, zestaw zostanie podpisany przy użyciu informacji z kontenera kluczy. Jeśli konsolidator nie odnajdzie kontenera kluczy, podejmie próbę pliku określonego za pomocą/KEYFILE. Jeśli to się powiedzie, zestaw zostanie podpisany przy użyciu informacji w pliku klucza, a informacje o kluczu zostaną zainstalowane w kontenerze kluczy (podobnym do SN-i), tak aby w następnej kompilacji kontener kluczy będzie prawidłowy.

Należy pamiętać, że plik klucza może zawierać tylko klucz publiczny.

Zobacz [Tworzenie i używanie zestawów Strong-Named,](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies) Aby uzyskać więcej informacji na temat podpisywania zestawu.

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

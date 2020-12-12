---
description: Dowiedz się więcej na temat:/ASSEMBLYRESOURCE (osadzanie zarządzanego zasobu)
title: /ASSEMBLYRESOURCE (Osadź zarządzany zasób)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.EmbedManagedResourceFile
- /ASSEMBLYRESOURCE
helpviewer_keywords:
- ASSEMBLYRESOURCE linker option
- assemblies [C++]
- -ASSEMBLYRESOURCE linker option
- assemblies [C++], linking resource files
- /ASSEMBLYRESOURCE linker option
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
ms.openlocfilehash: 3f79cc177df72bb83288a0a229fdf47adb0e7fc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182921"
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE (Osadź zarządzany zasób)

```
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]
```

## <a name="parameters"></a>Parametry

*Nazwa pliku*<br/>
Zasób zarządzany, który ma zostać osadzony w tym zestawie.

*Nazwij*<br/>
Opcjonalny. Nazwa logiczna zasobu; Nazwa używana do ładowania zasobu. Wartość domyślna to nazwa pliku.

Opcjonalnie można określić, czy plik powinien być prywatny w manifeście zestawu. Domyślnie *Nazwa* jest publiczna w zestawie.

## <a name="remarks"></a>Uwagi

Użyj opcji/ASSEMBLYRESOURCE, aby osadzić zasób w zestawie.

Zasoby są publiczne w zestawie po utworzeniu za pomocą konsolidatora. Konsolidator nie pozwala na zmianę nazwy zasobu w zestawie.

Jeśli *Nazwa pliku* to plik zasobów .NET Framework (Resources) utworzony na przykład przez [Generator plików zasobów (Resgen.exe)](/dotnet/framework/tools/resgen-exe-resource-file-generator) lub w środowisku programistycznym, dostęp do niego można uzyskać za pomocą elementów członkowskich w przestrzeni nazw **System.** [resources](/dotnet/api/system.resources.resourcemanager) (zobacz System W przypadku wszystkich innych zasobów Użyj metod **metod GetManifestResource** \* w klasie **System. odbicie. Assembly** , aby uzyskać dostęp do zasobu w czasie wykonywania.

Inne Opcje konsolidatora, które wpływają na generowanie zestawu, to:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **konsolidator** .

1. Kliknij stronę właściwości **dane wejściowe** .

1. Zmodyfikuj właściwość **Osadź plik zasobu zarządzanego** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

1. Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)

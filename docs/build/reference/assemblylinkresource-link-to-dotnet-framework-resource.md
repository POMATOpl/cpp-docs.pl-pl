---
description: Dowiedz się więcej na temat:/ASSEMBLYLINKRESOURCE (łącze do zasobu .NET Framework)
title: /ASSEMBLYLINKRESOURCE (Łącze do Zasobów .NET Framework)
ms.date: 11/04/2016
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
ms.openlocfilehash: 32761cb16e8428d5e3c18330dffb49a50a42903c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183012"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE (Łącze do Zasobów .NET Framework)

```
/ASSEMBLYLINKRESOURCE:filename
```

## <a name="arguments"></a>Argumenty

*Nazwa pliku*<br/>
Plik zasobów .NET Framework, do którego chcesz utworzyć łącze z zestawu.

## <a name="remarks"></a>Uwagi

Opcja/ASSEMBLYLINKRESOURCE tworzy łącze do zasobu .NET Framework w pliku wyjściowym; plik zasobu nie jest umieszczany w pliku wyjściowym. [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) osadza plik zasobów w pliku wyjściowym.

Połączone zasoby są publiczne w zestawie po utworzeniu za pomocą konsolidatora.

/ASSEMBLYLINKRESOURCE wymaga, aby kompilacja zawierała [/CLR](clr-common-language-runtime-compilation.md); [/LN](ln-create-msil-module.md) lub [/NOASSEMBLY](noassembly-create-a-msil-module.md) są niedozwolone w przypadku/ASSEMBLYLINKRESOURCE.

Jeśli *Nazwa* pliku to .NET Framework utworzony plik zasobów, na przykład przez [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) lub w środowisku deweloperskim, dostęp do niego można uzyskać za pomocą elementów członkowskich w przestrzeni nazw **System. resources** . Aby uzyskać więcej informacji, zobacz artykuł System. resources [. ResourceManager](/dotnet/api/system.resources.resourcemanager). W przypadku wszystkich innych zasobów Użyj metod **metod GetManifestResource** \* w klasie **System. odbicie. Assembly** , aby uzyskać dostęp do zasobu w czasie wykonywania.

*Nazwa* pliku może być dowolnym formatem pliku. Można na przykład utworzyć natywną bibliotekę DLL zestawu, aby można ją było zainstalować w globalnej pamięci podręcznej zestawów i uzyskać do niej dostęp z kodu zarządzanego w zestawie.

Inne Opcje konsolidatora, które wpływają na generowanie zestawu, to:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

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

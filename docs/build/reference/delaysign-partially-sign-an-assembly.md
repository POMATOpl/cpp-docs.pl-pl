---
description: Dowiedz się więcej o:/DELAYSIGN (częściowo podpisz zestaw)
title: /DELAYSIGN (Częściowo podpisz zestaw)
ms.date: 11/04/2016
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
ms.openlocfilehash: 40eeaef958b6a188fd4739fcdc0f5ef5123b220a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201485"
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN (Częściowo podpisz zestaw)

```
/DELAYSIGN[:NO]
```

## <a name="arguments"></a>Argumenty

**ZNALEZIONO**<br/>
Określa, że zestaw nie powinien być częściowo podpisany.

## <a name="remarks"></a>Uwagi

Użyj **/delaysign** , jeśli chcesz umieścić klucz publiczny w zestawie. Wartość domyślna to **/delaysign: No**.

Opcja **/delaysign** nie ma żadnego efektu, chyba że jest używana z [/KeyFile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) lub [/keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md).

Po zażądaniu w pełni podpisanego zestawu, kompilator skrótów pliku, który zawiera manifest (metadane zestawu) i podpisuje ten skrót z kluczem prywatnym. Wynikowy podpis cyfrowy jest przechowywany w pliku, który zawiera manifest. Gdy zestaw jest podpisany z opóźnieniem, konsolidator nie oblicza i nie przechowuje podpisu, ale rezerwuje miejsce w pliku, aby podpis mógł zostać dodany później.

Na przykład użycie **/delaysign** umożliwia testerowi umieszczenie zestawu w globalnej pamięci podręcznej. Po przetestowaniu można w pełni podpisać zestaw, umieszczając klucz prywatny w zestawie.

Zobacz [zestawy o silnych nazwach (podpisywanie zestawów) (C++/CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) i [opóźnienie podpisywania zestawu](/dotnet/framework/app-domains/delay-sign-assembly) , aby uzyskać więcej informacji na temat podpisywania zestawu.

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

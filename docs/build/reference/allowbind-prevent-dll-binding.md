---
description: Dowiedz się więcej o:/ALLOWBIND (Zapobiegaj powiązaniu biblioteki DLL)
title: /ALLOWBIND (Zapobiegaj powiązaniu biblioteki DLL)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
ms.openlocfilehash: 727f1cae7d1b0a94a8f7faba90ee6994df8657e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187237"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (Zapobiegaj powiązaniu biblioteki DLL)

```
/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Uwagi

/ALLOWBIND: NO ustawia bit w nagłówku DLL, który Bind.exe wskazuje, że nie można powiązać obrazu. Nie ma potrzeby powiązania DLL, jeśli został podpisany cyfrowo (powiązanie unieważnia sygnaturę).

Istniejącą bibliotekę DLL dla funkcji/ALLOWBIND można edytować za pomocą opcji [/ALLOWBIND](allowbind.md) narzędzia polecenia EDITBIN.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Rozwiń węzeł **Właściwości konfiguracji**, **konsolidator**, a następnie wybierz pozycję **wiersz polecenia**.

1. Wprowadź `/ALLOWBIND:NO` **dodatkowe opcje**.

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)<br/>
[BindImage, funkcja](/windows/win32/api/imagehlp/nf-imagehlp-bindimage)<br/>
[BindImageEx, funkcja](/windows/win32/api/imagehlp/nf-imagehlp-bindimageex)

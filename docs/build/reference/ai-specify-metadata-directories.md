---
description: Dowiedz się więcej na temat:/AI (Określ katalogi metadanych)
title: /AI (Określ katalogi metadanych)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
ms.openlocfilehash: e30711b1da2d41204bf56520d56dd5101f3168b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179749"
---
# <a name="ai-specify-metadata-directories"></a>/AI (Określ katalogi metadanych)

Określa katalog, który będzie przeszukiwany przez kompilator w celu rozpoznania odwołań do plików przesłanych do `#using` dyrektywy.

## <a name="syntax"></a>Składnia

> _Katalog_ /AI

## <a name="arguments"></a>Argumenty

*katalogi*<br/>
Katalog lub ścieżka, w której kompilator będzie wyszukiwał.

## <a name="remarks"></a>Uwagi

Tylko jeden katalog można przesłać do wywołania **/AI** . Określ jedną opcję **/AI** dla każdej ścieżki, która ma być wyszukiwany przez kompilator. Na przykład, aby dodać zarówno C:\Project\Meta, jak i C:\Common\Meta do ścieżki wyszukiwania kompilatora dla `#using` dyrektyw, należy dodać `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` do wiersza polecenia kompilatora lub dodać każdy katalog do właściwości **Dodatkowe katalogi #using** w programie Visual Studio.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości ogólne **C/C++** właściwości konfiguracji  >   .

1. Zmodyfikuj właściwość **Dodatkowe katalogi #using** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[#using — dyrektywa](../../preprocessor/hash-using-directive-cpp.md)

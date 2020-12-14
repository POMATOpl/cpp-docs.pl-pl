---
description: Dowiedz się więcej na temat:/FI (nazwa pliku wymuszonego dołączenia)
title: /FI (Nazwa pliku wymuszonego dołączenia)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
ms.openlocfilehash: 614a06511df1b407adc39bb8ec567a9674ffb3cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200653"
---
# <a name="fi-name-forced-include-file"></a>/FI (Nazwa pliku wymuszonego dołączenia)

Powoduje, że preprocesor przetwarza określony plik nagłówkowy.

## <a name="syntax"></a>Składnia

```
/FI[ ]pathname
```

## <a name="remarks"></a>Uwagi

Ta opcja ma ten sam skutek jak określenie pliku z podwójnym cudzysłowem w `#include` dyrektywie w pierwszym wierszu każdego pliku źródłowego określonego w wierszu polecenia, w zmiennej środowiskowej CL lub w pliku poleceń. Jeśli używasz wielu opcji **/Fi** , pliki są uwzględniane w kolejności, w jakiej są przetwarzane przez CL.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **Zaawansowane** .

1. Zmodyfikuj właściwość **wymuszonego dołączanego pliku** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje pliku wyjściowego (/F)](output-file-f-options.md)<br/>
[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[Określanie nazwy ścieżki](specifying-the-pathname.md)

---
description: 'Dowiedz się więcej na temat: `/X` (Ignoruj standardowe ścieżki dołączania)'
title: /X (Ignoruj standardowe ścieżki dołączanych plików)
ms.date: 07/31/2020
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLCompilerTool.IgnoreStandardIncludePath
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
ms.openlocfilehash: 69936b80893de2c45622ec9973a218a94e8029a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261011"
---
# <a name="x-ignore-standard-include-paths"></a>`/X` (Ignoruj standardowe ścieżki dołączane)

Uniemożliwia kompilatorowi wyszukiwanie plików dołączanych w katalogach określonych w ścieżce i zawiera zmienne środowiskowe.

## <a name="syntax"></a>Składnia

> **`/X`**

## <a name="remarks"></a>Uwagi

Możesz użyć tej opcji z opcją [ `/I` (Dodatkowe katalogi dołączane)](i-additional-include-directories.md) , aby określić alternatywną ścieżkę do standardowych plików dołączanych.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracji preprocesora **C/C++**  >   .

1. Zmodyfikuj właściwość **Ignorowanie standardowej ścieżki dołączania** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.

## <a name="example"></a>Przykład

W poniższym poleceniu **`/X`** nakazuje kompilatorowi ignorowanie lokalizacji określonych przez ścieżkę i uwzględnianie zmiennych środowiskowych, a **`/I`** także określa katalog, w którym mają być wyszukiwane pliki dołączane:

```cmd
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia wiersza polecenia kompilatora MSVC](compiler-command-line-syntax.md)

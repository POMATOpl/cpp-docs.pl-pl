---
description: Dowiedz się więcej na temat:/doc (Przetwarzaj komentarze dokumentacji) (C/C++)
title: /doc (Przetwarzaj komentarze dokumentacji) (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
ms.openlocfilehash: ed811edff544c4b5b28baa67ed216fa09ea51092
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192879"
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (Przetwarzaj komentarze dokumentacji) (C/C++)

Powoduje, że kompilator przetwarza komentarze dokumentacji w plikach kodu źródłowego i tworzy plik. xdc dla każdego pliku kodu źródłowego, który zawiera komentarze dokumentacji.

## <a name="syntax"></a>Składnia

> **/doc**[*Nazwa*]

## <a name="arguments"></a>Argumenty

*Nazwij*<br/>
Nazwa pliku. xdc, który zostanie utworzony przez kompilator. Prawidłowy tylko wtedy, gdy jeden plik. cpp jest przesyłany w kompilacji.

## <a name="remarks"></a>Uwagi

Pliki. xdc są przetwarzane do pliku XML przy użyciu xdcmake.exe. Aby uzyskać więcej informacji, zobacz [xdcmake Reference](xdcmake-reference.md).

Komentarze dokumentacji można dodawać do plików kodu źródłowego. Aby uzyskać więcej informacji, zobacz [zalecane Tagi dla komentarzy do dokumentacji](recommended-tags-for-documentation-comments-visual-cpp.md).

Aby użyć wygenerowanego pliku XML z technologią IntelliSense, należy wprowadzić nazwę pliku. XML tak samo jak zestaw, który ma być obsługiwany, i umieścić plik. XML znajduje się w tym samym katalogu, w którym znajduje się zestaw. Gdy zestaw jest przywoływany w projekcie programu Visual Studio, zostanie również znaleziony plik XML. Aby uzyskać więcej informacji, zobacz [Używanie technologii IntelliSense](/visualstudio/ide/using-intellisense) i [dostarczanie komentarzy do kodu XML](/visualstudio/ide/supplying-xml-code-comments).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości pliki wyjściowe **C/C++** właściwości konfiguracji  >   .

1. Zmodyfikuj właściwość **Generuj pliki dokumentacji XML** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)

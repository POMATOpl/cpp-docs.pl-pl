---
description: Dowiedz się więcej o:/I (Dodatkowe katalogi dołączane)
title: /I (Dodatkowe katalogi dołączenia)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
ms.openlocfilehash: ad44abec28bbb87f91f449765a9ea2f30f2bffa8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191345"
---
# <a name="i-additional-include-directories"></a>/I (Dodatkowe katalogi dołączenia)

Dodaje katalog do listy katalogów przeszukiwanych dla plików dołączanych.

## <a name="syntax"></a>Składnia

> **/I**[]*katalog*

### <a name="arguments"></a>Argumenty

*katalogi*<br/>
Katalog, który ma zostać dodany do listy katalogów przeszukiwanych w poszukiwaniu plików dołączanych.

## <a name="remarks"></a>Uwagi

Aby dodać więcej niż jeden katalog, Użyj tej opcji więcej niż raz. Katalogi są przeszukiwane tylko do momentu znalezienia określonego pliku dołączenia.

Tej opcji można użyć z opcją ([/x (Ignoruj standardowe ścieżki dołączania)](x-ignore-standard-include-paths.md)).

Kompilator Przeszukuje katalogi w następującej kolejności:

1. Jeśli określono za pomocą [dyrektywy #include](../../preprocessor/hash-include-directive-c-cpp.md) w formularzu z podwójnym cudzysłowem, najpierw przeszukuje katalogi lokalne. Wyszukiwanie rozpoczyna się w tym samym katalogu, w którym znajduje się plik, który zawiera instrukcję **#include** . Jeśli plik nie zostanie znaleziony, Przeszukuje katalogi aktualnie otwartych plików dołączanych w kolejności odwrotnej, w której zostały otwarte. Wyszukiwanie rozpoczyna się w katalogu nadrzędnego pliku dołączanego i kontynuuje w górę przez katalogi dowolnych plików dołączania.

1. Jeśli określono za pomocą dyrektywy **#include** w postaci nawiasu ostrego lub jeśli wyszukiwanie w katalogu lokalnym nie powiodło się, Przeszukuje katalogi określone przy użyciu **/i** opcji w kolejności, w jakiej CL je napotyka w wierszu polecenia.

1. Katalogi określone w zmiennej środowiskowej **include** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości ogólne **C/C++** właściwości konfiguracji  >   .

1. Zmodyfikuj właściwość **Dodatkowe katalogi dołączane** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.

## <a name="example"></a>Przykład

Poniższe polecenie szuka plików dołączanych wymaganych przez MAIN. c w następującej kolejności: najpierw, jeśli określono przy użyciu podwójnych cudzysłowów, przeszukiwane są pliki lokalne. Następnie wyszukiwanie kontynuuje się w katalogu \INCLUDE, a następnie w katalogu \MY\INCLUDE, a wreszcie w katalogach przypisanych do zmiennej środowiskowej INCLUDE.

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)

---
description: 'Dowiedz się więcej o:/EP (wstępnie przetwórz do stdout bez dyrektyw #line)'
title: '/EP (Wstępnie przetwórz do stdout bez dyrektyw #line)'
ms.date: 11/04/2016
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
ms.openlocfilehash: cbd36cd6bdafe315a7a6ef01b46857725033bd69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201004"
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP (Wstępnie przetwórz do stdout bez dyrektyw #line)

Wstępnie przetwarza pliki źródłowe C i C++ i kopiuje wstępnie przetworzone pliki na standardowe urządzenie wyjściowe.

## <a name="syntax"></a>Składnia

```
/EP
```

## <a name="remarks"></a>Uwagi

W procesie wszystkie dyrektywy preprocesora są przeprowadzane, są wykonywane rozwinięcia makr, a Komentarze są usuwane. Aby zachować komentarze w wstępnie przetworzonym danych wyjściowych, należy użyć opcji [/c (Zachowaj komentarze podczas przetwarzania wstępnego)](c-preserve-comments-during-preprocessing.md) z **/EP**.

Opcja **/EP** pomija kompilację. Musisz ponownie przesłać wstępnie przetworzony plik do kompilacji. **/EP** również pomija pliki wyjściowe z opcji **/FA**, **/FA** i **/FM** . Aby uzyskać więcej informacji, zobacz [/FA,/FA (Listing File)](fa-fa-listing-file.md) i [/FM (Name Mapfile)](fm-name-mapfile.md).

Błędy generowane podczas późniejszych etapów przetwarzania odnoszą się do numerów wierszy wstępnie przetworzonego pliku, a nie oryginalnego pliku źródłowego. Jeśli chcesz, aby numery wierszy odwołują się do oryginalnego pliku źródłowego, zamiast tego użyj [/e (wstępnie przetwórz do STDOUT)](e-preprocess-to-stdout.md) . Opcja **/e** dodaje `#line` dyrektywy do danych wyjściowych do tego celu.

Aby wysłać wstępnie przetworzone dane wyjściowe z `#line` dyrektywami do pliku, należy zamiast tego użyć [/p (preproces do pliku)](p-preprocess-to-a-file.md) .

Aby wysłać wstępnie przetworzone dane wyjściowe do stdout, z `#line` dyrektywami, należy użyć **/P** i **/EP** razem.

Nie można używać prekompilowanych nagłówków z opcją **/EP** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **preprocesora** .

1. Zmodyfikuj właściwość **Generuj wstępnie przetworzony plik** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Przykład

Poniższy wiersz polecenia wstępnie przetwarza plik `ADD.C` , zachowuje komentarze i wyświetla wynik na standardowym urządzeniu wyjściowym:

```
CL /EP /C ADD.C
```

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)

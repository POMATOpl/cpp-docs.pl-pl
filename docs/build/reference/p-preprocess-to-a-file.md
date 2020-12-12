---
description: Dowiedz się więcej na temat:/P (Przetwarzaj wstępnie do pliku)
title: /P (Przetwarzaj wstępnie do pliku)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
ms.openlocfilehash: 20bca03694c866baa0575445271fc4f587268096
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226197"
---
# <a name="p-preprocess-to-a-file"></a>/P (Przetwarzaj wstępnie do pliku)

Wstępnie przetwarza pliki źródłowe C i C++ oraz zapisuje wstępnie przetworzone dane wyjściowe do pliku.

## <a name="syntax"></a>Składnia

```
/P
```

## <a name="remarks"></a>Uwagi

Plik ma taką samą nazwę bazową jak plik źródłowy i rozszerzenie. i. W procesie wszystkie dyrektywy preprocesora są przeprowadzane, są wykonywane rozwinięcia makr, a Komentarze są usuwane. Aby zachować komentarze w wstępnie przetworzonym danych wyjściowych, należy użyć opcji [/c (Zachowaj komentarze podczas przetwarzania wstępnego)](c-preserve-comments-during-preprocessing.md) wraz z **parametrem/p**.

**/P** dodaje `#line` dyrektywy do danych wyjściowych na początku i na końcu każdego dołączonego pliku i wokół wierszy usuniętych przez dyrektywy preprocesora dla kompilacji warunkowej. Dyrektywy te ponownie przenoszą wiersze wstępnie przetworzonego pliku. W związku z tym błędy generowane podczas późniejszych etapów przetwarzania odnoszą się do numerów wierszy oryginalnego pliku źródłowego, a nie wierszy w pliku wstępnie przetworzonym. Aby pominąć generowanie `#line` dyrektyw, należy użyć [/EP (wstępnie przetwórz do stdout bez dyrektyw #line)](ep-preprocess-to-stdout-without-hash-line-directives.md) , a także **/p**.

Opcja **/p** pomija kompilację. Nie produkuje pliku. obj, nawet jeśli używasz [/FO (nazwa pliku obiektu)](fo-object-file-name.md). Musisz ponownie przesłać wstępnie przetworzony plik do kompilacji. **/P** Ponadto pomija pliki wyjściowe z opcji **/FA**, **/FA** i **/FM** . Aby uzyskać więcej informacji, zobacz [/FA,/FA (Listing File)](fa-fa-listing-file.md) i [/FM (Name Mapfile)](fm-name-mapfile.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **preprocesora** .

1. Zmodyfikuj właściwość **Generuj wstępnie przetworzony plik** .

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Przykład

Następujące wstępnie przetwarzane wiersze polecenia `ADD.C` , zachowuje komentarze, dodaje `#line` dyrektywy i zapisuje wynik do pliku `ADD.I` :

```
CL /P /C ADD.C
```

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)<br/>
[/Fi (Przetwarzaj wstępnie nazwę pliku wyjściowego)](fi-preprocess-output-file-name.md)

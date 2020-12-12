---
description: Dowiedz się więcej o:/E (Przetwarzaj wstępnie do STDOUT)
title: /E (Przetwarzaj wstępnie do stdout)
ms.date: 11/04/2016
f1_keywords:
- /e
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
ms.openlocfilehash: 9d6c9ea3a5fcf8e7ba06ede6e7e70d933b5c921a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192613"
---
# <a name="e-preprocess-to-stdout"></a>/E (Przetwarzaj wstępnie do stdout)

Wstępnie przetwarza pliki źródłowe C i C++ i kopiuje wstępnie przetworzone pliki na standardowe urządzenie wyjściowe.

## <a name="syntax"></a>Składnia

```
/E
```

## <a name="remarks"></a>Uwagi

W tym procesie wszystkie dyrektywy preprocesora są wykonywane, rozwinięcia makr i komentarze są usuwane. Aby zachować komentarze w wstępnie przetworzonym danych wyjściowych, należy użyć opcji [/c (Zachowaj komentarze podczas przetwarzania wstępnego)](c-preserve-comments-during-preprocessing.md) .

**/E** dodaje `#line` dyrektywy do danych wyjściowych na początku i na końcu każdego dołączonego pliku oraz wokół wierszy usuniętych przez dyrektywy preprocesora dla kompilacji warunkowej. Dyrektywy te ponownie przenoszą wiersze wstępnie przetworzonego pliku. W związku z tym błędy generowane podczas późniejszych etapów przetwarzania odnoszą się do numerów wierszy oryginalnego pliku źródłowego, a nie wierszy w pliku wstępnie przetworzonym.

Opcja **/e** pomija kompilację. Musisz ponownie przesłać wstępnie przetworzony plik do kompilacji. **/E** również pomija pliki wyjściowe z opcji **/FA**, **/FA** i **/FM** . Aby uzyskać więcej informacji, zobacz [/FA,/FA (Listing File)](fa-fa-listing-file.md) i [/FM (Name Mapfile)](fm-name-mapfile.md).

Aby pominąć `#line` dyrektywy, należy zamiast tego użyć opcji [/EP (wstępnie przetwórz do stdout bez dyrektyw #line)](ep-preprocess-to-stdout-without-hash-line-directives.md) .

Aby wysłać wstępnie przetworzone dane wyjściowe do pliku zamiast do, należy `stdout` zamiast tego użyć [/p (wstępnie przetwórz plik do pliku)](p-preprocess-to-a-file.md) .

Aby pominąć `#line` dyrektywy i wysłać wstępnie przetworzone dane wyjściowe do pliku, należy użyć **/P** i **/EP** razem.

Nie można używać prekompilowanych nagłówków z opcją **/e** .

Należy pamiętać, że podczas wstępnego przetwarzania do oddzielnego pliku spacje nie są emitowane po tokenach. Może to spowodować niedozwolony program lub mieć niezamierzone efekty uboczne. Pomyślnie skompilowano następujący program:

```
#define m(x) x
m(int)main( )
{
   return 0;
}
```

Jednak w przypadku kompilowania przy użyciu:

```
cl -E test.cpp > test2.cpp
```

`int main` w TEST2. cpp będzie nieprawidłowo `intmain` .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Kliknij folder **C/C++** .

1. Kliknij stronę właściwości **wiersza polecenia** .

1. Wpisz opcję kompilatora w polu **dodatkowe opcje**.

### <a name="to-set-this-compiler-option-programmatically"></a>Aby programowo ustawić tę opcję kompilatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.

## <a name="example"></a>Przykład

Następujące wstępnie przetwarzane wiersze polecenia `ADD.C` , zachowuje komentarze, dodaje `#line` dyrektywy i wyświetla wynik na standardowym urządzeniu wyjściowym:

```
CL /E /C ADD.C
```

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Składnia Command-Line kompilatora MSVC](compiler-command-line-syntax.md)

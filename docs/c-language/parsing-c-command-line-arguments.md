---
title: Analizowanie argumentów wiersza polecenia języka C
description: Dowiedz się, jak kod uruchomienia środowiska uruchomieniowego Microsoft C interpretuje argumenty wiersza polecenia, aby utworzyć parametry argv i argc.
ms.date: 11/09/2020
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- double quote marks
- command line, parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
ms.openlocfilehash: 92921e91ee6bb37b2bf7b702a1b31ed045187b59
ms.sourcegitcommit: b38485bb3a9d479e0c5d64ffc3d841fa2c2b366f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441258"
---
# <a name="parsing-c-command-line-arguments"></a>Analizowanie argumentów wiersza polecenia języka C

**Specyficzne dla firmy Microsoft**

Kod uruchamiania języka Microsoft C używa następujących reguł podczas interpretacji argumentów podanych w wierszu polecenia systemu operacyjnego:

- Argumenty są rozdzielane znakami odstępu, który jest spacją lub tabulatorem.

- Pierwszy argument ( `argv[0]` ) jest traktowany specjalnie. Reprezentuje nazwę programu. Ponieważ musi być prawidłową nazwą ścieżki, części ujęte w podwójne cudzysłowy ( **`"`** ) są dozwolone. Znaki podwójnego cudzysłowu nie są uwzględniane w `argv[0]` danych wyjściowych. Części ujęte w podwójne cudzysłowy uniemożliwiają interpretację spacji lub znaku tabulacji jako końca argumentu. Późniejsze reguły na tej liście nie mają zastosowania.

- Ciąg otoczony podwójnym cudzysłowem jest interpretowany jako pojedynczy argument, niezależnie od tego, czy zawiera on biały znak. Ciąg w cudzysłowie może być osadzony w argumencie. Karetka ( **`^`** ) nie jest rozpoznawana jako znak ucieczki ani ogranicznik. W ciągu ujętym w cudzysłów para podwójnych cudzysłowów jest interpretowana jako pojedynczy znak cudzysłowu podwójnego ucieczki. Jeśli wiersz polecenia zakończy się przed znalezieniem znaku cudzysłowu zamykającego, wszystkie znaki odczytane do tej pory są wyprowadzane jako ostatni argument.

- Podwójny znak cudzysłowu poprzedzony ukośnikiem odwrotnym ( **`\"`** ) jest interpretowany jako znak podwójnego cudzysłowu ( **`"`** ).

- Ukośniki odwrotne są interpretowane dosłownie, chyba że od razu poprzedzają podwójny cudzysłów.

- Jeśli parzysta liczba kresek ułamkowych jest poprzedzona znakiem podwójnego cudzysłowu, to jeden ukośnik odwrotny ( **`\`** ) jest umieszczany w `argv` tablicy dla każdej pary ukośników odwrotnych ( **`\\`** ), a znak cudzysłowu ( **`"`** ) jest interpretowany jako ogranicznik ciągu.

- Jeśli po parzystej liczbie ukośników odwrotnych następuje znak podwójnego cudzysłowu, to jeden ukośnik odwrotny ( **`\`** ) zostanie umieszczony w `argv` tablicy dla każdej pary ukośników odwrotnych ( **`\\`** ). Znak podwójnego cudzysłowu jest interpretowany jako sekwencja ucieczki przez resztę odwrotnego ukośnika, co powoduje umieszczenie znaku cudzysłowu podwójnego ( **`"`** ) `argv` .

Na tej liście przedstawiono reguły opisane powyżej, pokazując wynik interpretowany przekazane do `argv` kilku przykładów argumentów wiersza polecenia. Dane wyjściowe wymienione w drugiej, trzeciej i czwartej kolumnie pochodzą z ARGUMENTÓW. Program C, który znajduje się na liście.

|Command-Line dane wejściowe|argv [1]|argv [2]|argv [3]|
|-------------------------|---------------|---------------|---------------|
|`"a b c" d e`|`a b c`|`d`|`e`|
|`"ab\"c" "\\" d`|`ab"c`|`\`|`d`|
|`a\\\b d"e f"g h`|`a\\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|
|`a"b"" c d`|`ab" c d`|||

## <a name="example"></a>Przykład

### <a name="code"></a>Kod

```c
// ARGS.C illustrates the following variables used for accessing
// command-line arguments and environment variables:
// argc  argv  envp
//

#include <stdio.h>

int main( int argc, // Number of strings in array argv
char *argv[],      // Array of command-line argument strings
char **envp )      // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    printf_s( "\nCommand-line arguments:\n" );
    for( count = 0; count < argc; count++ )
        printf_s( "  argv[%d]   %s\n", count, argv[count] );

    // Display each environment variable.
    printf_s( "\nEnvironment variables:\n" );
    while( *envp != NULL )
        printf_s( "  %s\n", *(envp++) );

    return;
}
```

## <a name="comments"></a>Komentarze

Przykładem danych wyjściowych z tego programu jest:

```
Command-line arguments:
  argv[0]   C:\MSC\TEST.EXE

Environment variables:
  COMSPEC=C:\NT\SYSTEM32\CMD.EXE

  PATH=c:\nt;c:\binb;c:\binr;c:\nt\system32;c:\word;c:\help;c:\msc;c:\;
  PROMPT=[$p]
  TEMP=c:\tmp
  TMP=c:\tmp
  EDITORS=c:\binr
  WINDIR=c:\nt
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Funkcja Main i wykonywanie programu](../c-language/main-function-and-program-execution.md)

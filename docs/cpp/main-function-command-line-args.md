---
title: '`main` argumenty funkcji i wiersza polecenia (C++)'
description: '`main`Funkcja jest punktem wejścia dla programu C++.'
ms.date: 11/19/2020
no-loc:
- main
- wmain
- inline
- static
- _tmain
- void
- exit
- argc
- argv
- envp
- CreateProcess
- GetModuleFileName
- char
- wchar_t
- extern
ms.openlocfilehash: 8a5ed43bdacf5d9d6dd2cbc5d1c56783c82b8e9a
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483220"
---
# <a name="no-locmain-function-and-command-line-arguments"></a>`main` argumenty funkcji i wiersza polecenia

Wszystkie programy C++ muszą mieć `main` funkcję. W przypadku próby skompilowania programu C++ bez `main` funkcji kompilator zgłasza błąd. (Biblioteki i biblioteki dołączane dynamicznie static nie mają `main` funkcji). `main` Funkcja jest, gdzie kod źródłowy rozpoczyna wykonywanie, ale zanim program przejdzie do `main` funkcji, wszystkie static elementy członkowskie klasy bez jawnych inicjatorów mają ustawioną wartość zero. W programie Microsoft C++ static obiekty globalne są również inicjowane przed wpisem do `main` . Kilka ograniczeń ma zastosowanie do `main` funkcji, która nie ma zastosowania do innych funkcji języka C++. `main`Funkcja:

- Nie może być przeciążony (zobacz [przeciążanie funkcji](./function-overloading.md)).
- Nie można zadeklarować jako **`inline`** .
- Nie można zadeklarować jako **`static`** .
- Nie można pobrać adresu.
- Nie można wywołać z programu.

## <a name="the-no-locmain-function-signature"></a>`main`Sygnatura funkcji

`main`Funkcja nie ma deklaracji, ponieważ jest wbudowana w język. Jeśli tak, Składnia deklaracji dla `main` będzie wyglądać następująco:

```cpp
int main();
int main(int argc, char *argv[]);
```

Jeśli nie określono wartości zwracanej w `main` , kompilator dostarcza wartość zwracaną zero.

## <a name="standard-command-line-arguments"></a>Standardowe argumenty wiersza polecenia

Argumenty dla `main` umożliwiają wygodne analizowanie argumentów wiersza polecenia. Typy dla `argc` i `argv` są zdefiniowane przez język. Nazwy `argc` i `argv` są tradycyjnie, ale możesz je nazwać w dowolny sposób.

Definicje argumentów są następujące:

*`argc`*\
Liczba całkowita, która zawiera liczbę argumentów, które są następujące po elemencie *argv* . *argc* Parametr jest zawsze większy lub równy 1.

*`argv`*\
Tablica ciągów zakończonych znakiem null, która reprezentuje argumenty wiersza polecenia wprowadzone przez użytkownika programu. Według Konwencji `argv[0]` jest poleceniem, z którym wywoływany jest program. `argv[1]` jest pierwszym argumentem wiersza polecenia. Ostatni argument z wiersza polecenia to `argv[argc - 1]` i `argv[argc]` ma zawsze wartość null.

Aby uzyskać informacje na temat pomijania przetwarzania w wierszu polecenia, zobacz [Dostosowywanie przetwarzania w wierszu polecenia języka C++](#customize).

> [!NOTE]
> Zgodnie z Konwencją, `argv[0]` jest nazwą pliku programu. Jednak w systemie Windows istnieje możliwość duplikowania procesu za pomocą [`CreateProcess`](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) . Jeśli używasz zarówno pierwszego, jak i drugiego argumentu ( *`lpApplicationName`* i *`lpCommandLine`* ), `argv[0]` nie może być nazwą pliku wykonywalnego. Możesz użyć [`GetModuleFileName`](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) , aby pobrać nazwę pliku wykonywalnego i jego w pełni kwalifikowaną ścieżkę.

## <a name="microsoft-specific-extensions"></a>Rozszerzenia specyficzne dla firmy Microsoft

W poniższych sekcjach opisano zachowanie specyficzne dla firmy Microsoft.

## <a name="the-no-locwmain-function-and-no-loc_tmain-macro"></a>`wmain`Funkcja i `_tmain` makro

Jeśli zaprojektujesz kod źródłowy w celu używania char Acters Unicode, możesz użyć punktu wejścia specyficznego dla firmy Microsoft `wmain` , który jest w wersji szerokiej char acter `main` . Oto efektywna Składnia deklaracji dla `wmain` :

```cpp
int wmain();
int wmain(int argc, wchar_t *argv[]);
```

Można również użyć określonego przez firmę Microsoft `_tmain` , który jest makrem preprocesora zdefiniowanym w *`tchar.h`* . `_tmain` jest rozpoznawana jako, `main` chyba że `_UNICODE` jest zdefiniowany. W takim przypadku jest `_tmain` rozpoznawany jako `wmain` . `_tmain`Makro i inne makra, które zaczynają się od `_t` są przydatne dla kodu, który musi kompilować oddzielne wersje dla wąskich i szerokich char zestawów acter. Aby uzyskać więcej informacji, zobacz [Using Generic-Text Mappings](../c-runtime-library/using-generic-text-mappings.md).

## <a name="returning-no-locvoid-from-no-locmain"></a>Powrót `void` z main

Jako rozszerzenie firmy Microsoft `main` `wmain` funkcje i mogą być deklarowane jako Return **`void`** (bez wartości zwracanej). To rozszerzenie jest również dostępne w innych kompilatorach, ale nie jest to zalecane. Jest dostępny dla symetrii, gdy `main` nie zwraca wartości.

Jeśli deklarujesz `main` lub `wmain` jako Return **`void`** , nie można zwrócić exit kodu do procesu nadrzędnego lub systemu operacyjnego przy użyciu [`return`](./program-termination.md) instrukcji. Aby zwrócić exit kod, gdy `main` lub `wmain` jest zadeklarowany jako **`void`** , należy użyć [`exit`](./program-termination.md) funkcji.

## <a name="the-no-locenvp-command-line-argument"></a>`envp`Argument wiersza polecenia

`main` `wmain` Podpisy lub zezwalają na opcjonalne rozszerzenie specyficzne dla firmy Microsoft w celu uzyskania dostępu do zmiennych środowiskowych. To rozszerzenie jest również wspólne w przypadku innych kompilatorów systemów Windows i UNIX. Nazwa *`envp`* jest tradycyjna, ale można nazwać parametr środowiska. Poniżej przedstawiono obowiązujące deklaracje dla list argumentów, które zawierają parametr Environment:

```cpp
int main(int argc, char* argv[], char* envp[]);
int wmain(int argc, wchar_t* argv[], wchar_t* envp[]);
```

*`envp`*\
Opcjonalny *`envp`* parametr jest tablicą ciągów reprezentujących zmienne ustawione w środowisku użytkownika. Ta tablica została zakończona przez wpis o wartości NULL. Może być zadeklarowany jako tablica wskaźników do **`char`** ( `char *envp[]` ) lub jako wskaźnik do wskaźników **`char`** ( `char **envp` ). Jeśli program używa `wmain` zamiast tego `main` , użyj **`wchar_t`** typu danych zamiast **`char`** .

Blok środowiska przeszedł do `main` i `wmain` jest "zamrożoną" kopią bieżącego środowiska. W przypadku późniejszej zmiany środowiska przez wywołanie z `putenv` lub `_wputenv` , bieżące środowisko (zwracane przez `getenv` lub `_wgetenv` i `_environ` lub  `_wenviron` zmienna) zostanie zmienione, ale blok wskazywany przez *`envp`* nie ulegnie zmianie. Aby uzyskać więcej informacji na temat pomijania przetwarzania środowiska, zobacz [Dostosowywanie przetwarzania w wierszu polecenia języka C++](#customize). *`envp`* Argument jest zgodny ze standardem C89, ale nie ze standardami języka C++.

### <a name="example-arguments-to-no-locmain"></a>Przykładowe argumenty do `main`

Poniższy przykład pokazuje, jak używać *`argc`* *`argv`* argumentów, i *`envp`* do `main` :

```cpp
// argument_definitions.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;
int main( int argc, char *argv[], char *envp[] ) {
    int iNumberLines = 0;    // Default is no line numbers.

    // If /n is passed to the .exe, display numbered listing
    // of environment variables.

    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )
         iNumberLines = 1;

    // Walk through list of strings until a NULL is encountered.
    for( int i = 0; envp[i] != NULL; ++i ) {
        if( iNumberLines )
            cout << i << ": " << envp[i] << "\n";
    }
}
```

## <a name="parsing-c-command-line-arguments"></a>Analizowanie argumentów wiersza polecenia języka C++

Reguły analizy wiersza polecenia używane przez kod Microsoft C/C++ są specyficzne dla firmy Microsoft. Kod uruchomienia środowiska uruchomieniowego używa tych reguł podczas interpretacji argumentów podanym w wierszu polecenia systemu operacyjnego:

- Argumenty są rozdzielane znakami odstępu, który jest spacją lub tabulatorem.

- Pierwszy argument ( `argv[0]` ) jest traktowany specjalnie. Reprezentuje nazwę programu. Ponieważ musi być prawidłową nazwą ścieżki, części ujęte w podwójne cudzysłowy ( **`"`** ) są dozwolone. Znaki podwójnego cudzysłowu nie są uwzględniane w `argv[0]` danych wyjściowych. Części ujęte w podwójne cudzysłowy uniemożliwiają interpretację spacji lub karty char acter jako koniec argumentu. Późniejsze reguły na tej liście nie mają zastosowania.

- Ciąg ujęty w podwójne znaki cudzysłowu jest interpretowany jako pojedynczy argument, który może zawierać białe miejsce char acters. Ciąg w cudzysłowie może być osadzony w argumencie. Karetka ( **`^`** ) nie jest rozpoznawana jako char acter ucieczki lub ogranicznika. W ciągu ujętym w cudzysłów para podwójnych cudzysłowów jest interpretowana jako pojedynczy znak cudzysłowu podwójnego ucieczki. Jeśli wiersz polecenia zostanie zakończony przed znalezieniem cudzysłowu zamykającego cudzysłowu, wszystkie char acters odczytane do tej pory są wyprowadzane jako ostatni argument.

- Podwójny znak cudzysłowu poprzedzony ukośnikiem odwrotnym ( **`\"`** ) jest interpretowany jako znak podwójnego cudzysłowu ( **`"`** ).

- Ukośniki odwrotne są interpretowane dosłownie, chyba że od razu poprzedzają podwójny cudzysłów.

- Jeśli parzysta liczba kresek ułamkowych jest poprzedzona znakiem podwójnego cudzysłowu, to jeden ukośnik odwrotny ( **`\`** ) jest umieszczany w `argv` tablicy dla każdej pary ukośników odwrotnych ( **`\\`** ), a znak cudzysłowu ( **`"`** ) jest interpretowany jako ogranicznik ciągu.

- Jeśli po parzystej liczbie ukośników odwrotnych następuje znak podwójnego cudzysłowu, to jeden ukośnik odwrotny ( **`\`** ) zostanie umieszczony w `argv` tablicy dla każdej pary ukośników odwrotnych ( **`\\`** ). Znak podwójnego cudzysłowu jest interpretowany jako sekwencja ucieczki przez przekroczenie main ukośnika odwrotnego, powodującego umieszczenie podwójnego znaku cudzysłowu ( **`"`** ) `argv` .

### <a name="example-of-command-line-argument-parsing"></a>Przykład analizy argumentów wiersza polecenia

Następujący program ilustruje sposób przekazywania argumentów wiersza polecenia:

```cpp
// command_line_arguments.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
int main( int argc,      // Number of strings in array argv
          char *argv[],   // Array of command-line argument strings
          char *envp[] )  // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    cout << "\nCommand-line arguments:\n";
    for( count = 0; count < argc; count++ )
         cout << "  argv[" << count << "]   "
                << argv[count] << "\n";
}
```

### <a name="results-of-parsing-command-lines"></a>Wyniki analizy wierszy poleceń

W poniższej tabeli przedstawiono przykładowe dane wejściowe i oczekiwane dane wyjściowe, ukazując reguły z powyższej listy.

| Wprowadzanie w wierszu polecenia | argvjedno | argvdwóch | argvr.3 |
|--|--|--|--|
| `"abc" d e` | `abc` | `d` | `e` |
| `a\\b d"e f"g h` | `a\\b` | `de fg` | `h` |
| `a\\\"b c d` | `a\"b` | `c` | `d` |
| `a\\\\"b c" d e` | `a\\b c` | `d` | `e` |
| `a"b"" c d` | `ab" c d` |  |  |

## <a name="wildcard-expansion"></a>Rozwijanie symbolu wieloznacznego

Kompilator firmy Microsoft opcjonalnie umożliwia użycie *symboli wieloznacznych* char acters, znaku zapytania ( **`?`** ) i gwiazdki ( **`*`** ), aby określić argumenty filename i Path w wierszu polecenia.

Argumenty wiersza polecenia są obsługiwane przez wewnętrzną procedurę w kodzie uruchomienia środowiska uruchomieniowego, które domyślnie nie rozszerza symboli wieloznacznych na oddzielne ciągi w `argv` tablicy ciągów. Można włączyć rozszerzanie symboli wieloznacznych, dołączając *`setargv.obj`* plik ( *`wsetargv.obj`* plik dla `wmain` ) w **`/link`** opcjach kompilatora lub w **`LINK`** wierszu polecenia.

Aby uzyskać więcej informacji na temat uruchamiania opcji konsolidatora środowiska uruchomieniowego, zobacz [Opcje łącza](../c-runtime-library/link-options.md).

## <a name="customize-c-command-line-processing"></a><a name="customize"/> Dostosowywanie przetwarzania w wierszu polecenia języka C++

Jeśli program nie przyjmuje argumentów wiersza polecenia, można pominąć procedurę przetwarzania wiersza polecenia, aby zaoszczędzić niewielką ilość miejsca. Aby pominąć użycie, Dołącz *`noarg.obj`* plik (dla obu `main` i `wmain` ) w **`/link`** opcjach kompilatora lub w **`LINK`** wierszu polecenia.

Podobnie, jeśli nie masz dostępu do tabeli środowiska za pomocą *`envp`* argumentu, możesz pominąć procedurę wewnętrznego przetwarzania środowiska. Aby pominąć użycie, Dołącz *`noenv.obj`* plik (dla obu `main` i `wmain` ) w **`/link`** opcjach kompilatora lub w **`LINK`** wierszu polecenia.

Program może wykonywać wywołania do `spawn` lub `exec` z rodziny procedur w bibliotece środowiska uruchomieniowego języka C. W takim przypadku nie należy pomijać procedury przetwarzania środowiska, ponieważ jest ona używana do przekazywania środowiska z procesu nadrzędnego do procesu podrzędnego.

## <a name="see-also"></a>Zobacz także

[Podstawowe pojęcia](../cpp/basic-concepts-cpp.md)

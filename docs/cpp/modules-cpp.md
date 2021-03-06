---
title: Omówienie modułów w języku C++
ms.date: 12/13/2019
helpviewer_keywords:
- modules [C++]
- modules [C++], overview
description: Moduły w języku C++ 20 zapewniają nowoczesne alternatywy dla plików nagłówkowych.
ms.openlocfilehash: fe5beee92ed257cca8143fa95f8f59bc9308fd5d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233681"
---
# <a name="overview-of-modules-in-c"></a>Omówienie modułów w języku C++

C++ 20 wprowadza *moduły*, nowoczesne rozwiązanie do componentization bibliotek i programów C++. Moduł jest zestawem plików kodu źródłowego, które są kompilowane niezależnie od [jednostek translacji](https://wikipedia.org/wiki/Translation_unit_(programming)) , które je zaimportują. Moduły eliminują lub znacznie zmniejszają wiele problemów związanych z użyciem plików nagłówkowych, a także mogą skrócić czas kompilacji. Makra, dyrektywy preprocesora i nieeksportowane nazwy zadeklarowane w module nie są widoczne i nie mają wpływu na kompilację jednostki tłumaczenia, która importuje moduł. Moduły można importować w dowolnej kolejności bez obaw o ponowne zdefiniowanie makr. Deklaracje w importującej jednostce translacji nie uczestniczą w rozpoznaniu przeciążenia lub wyszukiwaniu nazw w importowanym module. Po skompilowaniu modułu raz, wyniki są przechowywane w pliku binarnym, który opisuje wszystkie eksportowane typy, funkcje i szablony. Ten plik może być przetwarzany znacznie szybciej niż plik nagłówka i może być ponownie używany przez kompilator w każdym miejscu, w którym zaimportowano moduł do projektu.

Moduły mogą być używane obok plików nagłówkowych. Plik źródłowy języka C++ umożliwia importowanie modułów, a także #include plików nagłówkowych. W niektórych przypadkach plik nagłówka może zostać zaimportowany jako moduł, a nie #includedny przez preprocesor. Zalecamy, aby nowe projekty używały modułów zamiast plików nagłówkowych, jak to możliwe. W przypadku większych istniejących projektów w ramach aktywnego programowania zalecamy przeprowadzenie eksperymentu z konwertowaniem starszych nagłówków na moduły, aby zobaczyć, czy uzyskano znaczącą redukcję w czasie kompilacji.

## <a name="enable-modules-in-the-microsoft-c-compiler"></a>Włączanie modułów w kompilatorze języka Microsoft C++

W przypadku programu Visual Studio 2019 w wersji 16,2 moduły nie są w pełni zaimplementowane w kompilatorze języka Microsoft C++. Za pomocą funkcji modułów można tworzyć moduły z jedną partycją i importować moduły biblioteki standardowej udostępniane przez firmę Microsoft. Aby włączyć obsługę modułów, skompiluj z [/Experimental: module](../build/reference/experimental-module.md) i [/std: c + + Najnowsza](../build/reference/std-specify-language-standard-version.md). W projekcie programu Visual Studio kliknij prawym przyciskiem myszy węzeł projektu w **Eksplorator rozwiązań** i wybierz polecenie **Właściwości**. Ustaw listę rozwijaną **Konfiguracja** na **wszystkie konfiguracje**, a następnie wybierz pozycję **Właściwości konfiguracji**  >  **Język C/c++**  >  **Language**  >  **Włącz moduły języka C++ (eksperymentalne)**.

Moduł i kod, który go zużywa, muszą być kompilowane z tymi samymi opcjami kompilatora.

## <a name="consume-the-c-standard-library-as-modules"></a>Korzystanie z biblioteki standardowej języka C++ jako modułów

Mimo że nie jest to określone przez standard C++ 20, firma Microsoft umożliwia importowanie standardowej biblioteki języka C++ jako modułów. Przez zaimportowanie standardowej biblioteki C++ jako modułów zamiast #including za pomocą plików nagłówkowych można przyspieszyć czas kompilacji w zależności od wielkości projektu. Biblioteka jest podzielona na następujące moduły:

- STD. wyrażenie regularne zapewnia zawartość nagłówka\<regex>
- STD. FileSystem zawiera zawartość nagłówka\<filesystem>
- wartość std. Memory zapewnia zawartość nagłówka\<memory>
- STD. Threading zapewnia zawartość nagłówków \<atomic> ,,, \<condition_variable> , \<future> \<mutex> \<shared_mutex> i\<thread>
- STD. Core zapewnia wszystkie inne elementy w standardowej bibliotece języka C++

Aby korzystać z tych modułów, po prostu Dodaj deklarację importu na początku pliku kodu źródłowego. Na przykład:

```cpp
import std.core;
import std.regex;
```

Aby korzystać z modułu standardowej biblioteki firmy Microsoft, skompiluj program przy użyciu opcji [/EHsc](../build/reference/eh-exception-handling-model.md) i [/MD](../build/reference/md-mt-ld-use-run-time-library.md) .

## <a name="basic-example"></a>Przykład podstawowy

Poniższy przykład pokazuje prostą definicję modułu w pliku źródłowym o nazwie **foo. IXX**. Rozszerzenie **. IXX** jest wymagane dla plików interfejsu modułu w programie Visual Studio. W tym przykładzie plik interfejsu zawiera definicję funkcji oraz deklarację. Jednakże definicje można także umieścić w jednym lub kilku oddzielnych plikach (jak pokazano w późniejszym przykładzie). Instrukcja **Export module foo** wskazuje, że ten plik jest interfejsem podstawowym dla modułu o nazwie `Foo` . **`export`** Modyfikator on `f()` wskazuje, że ta funkcja będzie widoczna, gdy `Foo` zostanie zaimportowana przez inny program lub moduł. Należy zauważyć, że moduł odwołuje się do przestrzeni nazw `Bar` .

```cpp
export module Foo;

#define ANSWER 42

namespace Bar
{
   int f_internal() {
        return ANSWER;
      }

   export int f() {
      return f_internal();
   }
}
```

Plik **. cpp** używa deklaracji **Import** w celu uzyskania dostępu do nazwy, która została wyeksportowana przez `Foo` . Należy zauważyć, że nazwa `Bar` jest widoczna w tym miejscu, ale nie dla wszystkich jej elementów członkowskich. Należy również zauważyć, że makro `ANSWER` nie jest widoczne.

```cpp

import Foo;
import std.core;

using namespace std;

int main()
{
   cout << "The result of f() is " << Bar::f() << endl; // 42
   // int i = Bar::f_internal(); // C2039
   // int j = ANSWER; //C2065
}

```

Deklaracja importu może wystąpić tylko w zakresie globalnym.

## <a name="implementing-modules"></a>Implementowanie modułów

Można utworzyć moduł z pojedynczym plikiem interfejsu (. IXX), który eksportuje nazwy i zawiera implementacje wszystkich funkcji i typów. Możesz również wprowadzić implementacje w co najmniej jednym osobnym pliku implementacji, podobnie jak pliki. h i. cpp. **`export`** Słowo kluczowe jest używane tylko w pliku interfejsu. Plik implementacji może **importować** inny moduł, ale nie może mieć **`export`** żadnych nazw. Pliki implementacji mogą być nazwane z dowolnym rozszerzeniem. Plik interfejsu i zestaw plików implementacji, które z niego odnoszą, są traktowane jako specjalny rodzaj jednostki tłumaczenia zwanej *jednostką modułu*. Nazwa zadeklarowana w dowolnym pliku implementacji jest automatycznie widoczna we wszystkich innych plikach w tej samej jednostce modułu.

W przypadku większych modułów można podzielić moduł na wiele jednostek modułu o nazwie *Partitions*. Każda partycja składa się z pliku interfejsu obsługiwanego przez jeden lub więcej plików implementacji. (W przypadku programu Visual Studio 2019 w wersji 16,2 partycje nie są jeszcze w pełni zaimplementowane).

## <a name="modules-namespaces-and-argument-dependent-lookup"></a>Moduły, przestrzenie nazw i wyszukiwanie zależne od argumentów

Reguły dla przestrzeni nazw w modułach są takie same jak w przypadku innych kodów. Jeśli zostanie wyeksportowana deklaracja w przestrzeni nazw, zostanie ona również niejawnie wyeksportowana. Jeśli obszar nazw jest jawnie eksportowany, wszystkie deklaracje w tej definicji przestrzeni nazw są eksportowane.

Podczas wyszukiwania zależnego od argumentów dla rozdzielczości przeciążeń w jednostce translacji importowania, kompilator traktuje funkcje, które są zadeklarowane w tej samej jednostce translacji (w tym interfejsy modułów), jak gdzie jest zdefiniowany typ argumentów funkcji.

### <a name="module-partitions"></a>Partycje modułu

> [!NOTE]
> Ta sekcja jest zapewniana kompletność. Partycje nie są jeszcze zaimplementowane w kompilatorze języka Microsoft C++.

Moduł może być składowany w *partycjach*, z których każdy składa się z pliku interfejsu i nie może zawierać plików implementacji. Partycja modułu jest podobna do modułu, z tą różnicą, że udostępnia własność wszystkich deklaracji w całym module. Wszystkie nazwy, które są eksportowane przez pliki interfejsu partycji, są importowane i ponownie eksportowane przez podstawowy plik interfejsu. Nazwa partycji musi rozpoczynać się od nazwy modułu, po którym następuje dwukropek. Deklaracje w dowolnej z partycji są widoczne w całym module. Nie są konieczne żadne specjalne środki ostrożności, aby uniknąć błędów ODR (Rule-Definition). Można zadeklarować nazwę (funkcję, klasę itp.) w jednej partycji i zdefiniować ją w innej. Plik implementacji partycji zaczyna wyglądać następująco:

```cpp
module Foo:part1
```

plik interfejsu partycji zaczyna wyglądać następująco:

```cpp
export module Foo:part1
```

Aby można było uzyskać dostęp do deklaracji w innej partycji, partycja musi ją zaimportować, ale może używać tylko nazwy partycji, a nie nazwy modułu:

```cpp
module Foo:part2;
import :part1;
```

Podstawowa jednostka interfejsu musi importować i ponownie eksportować wszystkie pliki partycji interfejsu modułu w następujący sposób:

```cpp
export import :part1
export import :part2
...
```

Podstawowa jednostka interfejsu może importować pliki implementacji partycji, ale nie może ich eksportować, ponieważ te pliki nie mogą eksportować żadnych nazw. Umożliwia to modułowi zachowanie szczegółów implementacji wewnętrznych dla modułu.

## <a name="modules-and-header-files"></a>Moduły i pliki nagłówkowe

Pliki nagłówkowe można dołączać do pliku źródłowego modułu przez umieszczenie `#include` dyrektywy przed deklaracją modułu. Te pliki są uważane za znajdujące się w *fragmencie modułu globalnego*. W module można zobaczyć tylko nazwy w *fragmencie modułu globalnego* , które znajdują się w nagłówkach, które jawnie zawiera. Fragment modułu globalnego zawiera tylko symbole, które są rzeczywiście używane.

```cpp
// MyModuleA.cpp

#include "customlib.h"
#include "anotherlib.h"

import std.core;
import MyModuleB;

//... rest of file
```

Możesz użyć tradycyjnego pliku nagłówkowego, aby kontrolować, które moduły są importowane:

```cpp
// MyProgram.h
import std.core;
#ifdef DEBUG_LOGGING
import std.filesystem;
#endif
```

### <a name="imported-header-files"></a>Zaimportowane pliki nagłówkowe

> [!NOTE]
> Ta sekcja ma tylko informacje informacyjne. Starsze Importy nie zostały jeszcze zaimplementowane w kompilatorze języka Microsoft C++.

Niektóre nagłówki są wystarczająco samodzielne, ponieważ mogą być wprowadzane przy użyciu słowa kluczowego **Import** . Główna różnica między zaimportowanym nagłówkiem a zaimportowanym modułem polega na tym, że wszystkie Definicje preprocesora w nagłówku są widoczne w programie importującym bezpośrednio po instrukcji import. (Definicje preprocesora w dowolnych plikach zawartych w tym nagłówku *nie* są widoczne).

```cpp
import <vector>
import "myheader.h"
```

## <a name="see-also"></a>Zobacz także

[moduł, import, eksport](import-export-module.md)

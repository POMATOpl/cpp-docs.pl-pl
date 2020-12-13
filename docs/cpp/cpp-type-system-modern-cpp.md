---
description: Dowiedz się więcej o systemie typów C++
title: System typów języka C++
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
ms.openlocfilehash: 1be39124e51fc2e812ce5a2779ce701d727c81e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339582"
---
# <a name="c-type-system"></a>System typów języka C++

Koncepcja *typu* jest bardzo ważna w języku C++. Zwracana wartość każdej zmiennej, argumentu funkcji oraz funkcji musi mieć typ, aby mogła zostać skompilowana. Ponadto, kompilator niejawnie nadaje typ każdemu wyrażeniu (w tym wartości literału), zanim zostanie on oceniony. Niektóre przykłady typów obejmują **`int`** przechowywanie wartości całkowitych, **`double`** przechowywanie wartości zmiennoprzecinkowych (znanych także jako *skalarne* typy danych) lub klasy standardowej biblioteki [std:: basic_string](../standard-library/basic-string-class.md) do przechowywania tekstu. Możesz utworzyć własny typ, definiując a **`class`** lub **`struct`** . Typ określa wielkość pamięci, która zostanie zaalokowana dla zmiennej (lub wyniku wyrażenia), rodzaje wartości, które mogą być przechowywane w tej zmiennej, sposób interpretacji tych wartości (jako wzorców bajtów) oraz operacje, jakie mogą zostać na nich wykonane. Ten artykuł zawiera nieformalny przegląd głównych funkcji systemu typów C++.

## <a name="terminology"></a>Terminologia

**Zmienna**: Nazwa symboliczna ilości danych, tak aby nazwa mogła być używana do uzyskiwania dostępu do danych, do których odwołuje się cały zakres kodu, w którym jest zdefiniowany. W języku C++ *zmienna* jest zwykle używana do odwoływania się do wystąpień typów danych skalarnych, natomiast wystąpienia innych typów są zwykle nazywane *obiektami*.

**Obiekt**: dla uproszczenia i spójności, w tym artykule użyto *obiektu* Term do odwoływania się do dowolnego wystąpienia klasy lub struktury, a gdy jest on używany w ogólnym sensie, obejmuje wszystkie typy, nawet zmienne skalarne.

**Typ pod** (zwykłe stare dane): Ta nieformalna Kategoria typów danych w języku C++ odwołuje się do typów, które są skalarne (patrz sekcja podstawowe typy) lub znajdują się w *klasach*. Klasa POD nie ma żadnych statycznych składowych danych, które nie są również POD, i nie ma zdefiniowanych przez użytkownika konstruktorów, zdefiniowanych przez użytkownika destruktorów ani zdefiniowanych przez użytkownika operatorów przypisania. Klasa POD nie ma też żadnych funkcji wirtualnych, nie ma klasy podstawowej ani żadnych prywatnych lub chronionych niestatycznych składowych danych. Typy POD są często używane do wymiany danych zewnętrznych, na przykład przy użyciu modułu napisanego w języku C (który ma tylko typy POD).

## <a name="specifying-variable-and-function-types"></a>Określanie typów zmiennych i funkcji

C++ jest *jednoznacznie określonym* językiem i jest również *statycznie wpisana*; Każdy obiekt ma typ i ten typ nigdy nie ulega zmianie (nie należy mylić z obiektami danych statycznych). W przypadku deklarowania zmiennej w kodzie należy określić jawnie jej typ lub użyć **`auto`** słowa kluczowego, aby nakazać kompilatorowi wywnioskowanie typu z inicjatora. Kiedy deklarujesz funkcję w kodzie, musisz określić typ każdego argumentu i jego wartość zwracaną, lub **`void`** Jeśli żadna wartość nie zostanie zwrócona przez funkcję. Wyjątek występuje podczas korzystania z szablonów funkcji, które pozwalają na argumenty dowolnego typu.

Po pierwszym zdeklarowaniu zmiennej nie można później zmienić jej typu. Możesz jednak skopiować wartość zmiennej lub wartość zwracaną przez funkcję do innej zmiennej innego typu. Operacje te są nazywane *konwersjemi typu*, które są czasami niezbędne, ale również są potencjalnymi źródłami utraty lub nieprawidłowego działania danych.

Kiedy deklarujesz zmienną typu POD, stanowczo zalecamy jej inicjalizację, co oznacza nadanie jej początkowej wartości. Dopóki zmienna nie zostanie zainicjalizowana, ma ona wartość „śmieciową”, składającą się z bitów, które poprzednio znajdowały się w tej lokalizacji pamięci. Jest to ważny aspekt C++ warty zapamiętania, szczególnie jeżeli praca odbywała się wcześniej w innym języku, który automatycznie obsługuje inicjalizację. Gdy deklarujesz zmienną typu innego niż klasa POD, konstruktor obsługuje inicjalizację.

Poniższy przykład pokazuje kilka prostych deklaracji zmiennych z opisami każdej z nich. W przykładzie pokazano również, jak kompilator używa informacji o typie, aby umożliwiać lub uniemożliwiać pewne kolejne operacje na zmiennej.

```cpp
int result = 0;              // Declare and initialize an integer.
double coefficient = 10.8;   // Declare and initialize a floating
                             // point value.
auto name = "Lady G.";       // Declare a variable and let compiler
                             // deduce the type.
auto address;                // error. Compiler cannot deduce a type
                             // without an intializing value.
age = 12;                    // error. Variable declaration must
                             // specify a type or use auto!
result = "Kenny G.";         // error. Can’t assign text to an int.
string result = "zero";      // error. Can’t redefine a variable with
                             // new type.
int maxValue;                // Not recommended! maxValue contains
                             // garbage bits until it is initialized.
```

## <a name="fundamental-built-in-types"></a>Podstawowe (wbudowane) typy

W odróżnieniu do innych języków, C++ nie ma uniwersalnego typu bazowego, z którego wywodzą się wszystkie inne typy. Język zawiera wiele *typów podstawowych*, znanych również jako *typy wbudowane*. Obejmuje to typy liczbowe, takie jak,,,, **`int`** **`double`** **`long`** **`bool`** **`char`** oraz **`wchar_t`** typy i dla znaków ASCII i Unicode. Wszystkie typy podstawowe (z wyjątkiem **`bool`** , **`double`** , **`wchar_t`** , i powiązane typy) mają wszystkie **`unsigned`** wersje, które modyfikują zakres wartości, które mogą być przechowywane w zmiennej. Na przykład, **`int`** który przechowuje 32-bitową liczbę całkowitą ze znakiem, może reprezentować wartość z-2 147 483 648 do 2 147 483 647. **`unsigned int`** A, który jest również przechowywany jako 32-bitowy, może przechowywać wartość z przeniesień od 0 do 4 294 967 295. Całkowita liczba możliwych wartości w każdym przypadku jest taka sama, zmienia się tylko zakres.

Podstawowe typy są rozpoznawane przez kompilator, który posiada wbudowane reguły rządzące tym, jakie operacje można na nich wykonywać i jak mogą być konwertowane na inne typy podstawowe. Aby uzyskać pełną listę typów wbudowanych oraz ich rozmiar i limity liczbowe, zobacz [typy wbudowane](../cpp/fundamental-types-cpp.md).

Na poniższej ilustracji przedstawiono względne rozmiary wbudowanych typów w implementacji języka Microsoft C++:

![Rozmiar w bajtach skompilowanego&#45;w typach](../cpp/media/built-intypesizes.png "Rozmiar w bajtach skompilowanego&#45;w typach")

W poniższej tabeli wymieniono najczęściej używane podstawowe typy i ich rozmiary w implementacji języka Microsoft C++:

| Typ | Rozmiar | Komentarz |
|--|--|--|
| **`int`** | 4 bajty | Wybór domyślny dla wartości całkowitych. |
| **`double`** | 8 bajtów | Wybór domyślny dla wartości zmiennopozycyjnych. |
| **`bool`** | 1 bajt | Przedstawia wartości, które mogą być prawdziwe lub fałszywe. |
| **`char`** | 1 bajt | Używaj dla znaków ASCII w starszych ciągach typu C lub obiektach std::string, które nigdy nie będą musiały zostać skonwertowane na UNICODE. |
| **`wchar_t`** | 2 bajty | Przedstawia wartości znaku „szerokiego”, które mogą być zakodowane w formacie UNICODE (UTF-16 w systemie Windows, inne systemy operacyjne mogą się różnić). Jest to typ znaku, który jest używany w ciągach typu `std::wstring` . |
| **`unsigned char`** | 1 bajt | Język C++ nie ma wbudowanego typu bajtów.  Służy **`unsigned char`** do reprezentowania wartości bajtowej. |
| **`unsigned int`** | 4 bajty | Wybór domyślny dla flag bitowych. |
| **`long long`** | 8 bajtów | Przedstawia bardzo duże wartości całkowitoliczbowe. |

Inne implementacje języka C++ mogą używać różnych rozmiarów dla niektórych typów liczbowych. Aby uzyskać więcej informacji na temat rozmiarów i wielkości relacji, których wymaga standard C++, zobacz [typy wbudowane](fundamental-types-cpp.md).

## <a name="the-void-type"></a>Typ void (pusty).

**`void`** Typ jest typem specjalnym; nie można zadeklarować zmiennej typu **`void`** , ale można zadeklarować zmienną typu `void *` (wskaźnik do **`void`** ), która jest czasami konieczna podczas alokowania pierwotnej (niewpisanej) pamięci. Jednak wskaźniki do **`void`** nie są bezpieczne dla typów i ogólnie ich użycie jest zdecydowanie odradzane w nowoczesnej C++. W deklaracji funkcji **`void`** zwracana wartość oznacza, że funkcja nie zwraca wartości; jest to typowe i akceptowalne użycie **`void`** . Chociaż język C wymaga funkcji, które mają zerowe parametry do zadeklarowania **`void`** na liście parametrów, na przykład, `fou(void)` Ta metoda jest niezalecana w nowoczesnej C++ i powinna być zadeklarowana `fou()` . Aby uzyskać więcej informacji, zobacz [konwersje typów i bezpieczeństwo typów](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="const-type-qualifier"></a>kwalifikator typu const

Dowolny wbudowany lub zdefiniowany przez użytkownika typ może być zakwalifikowany według słowa kluczowego const. Ponadto funkcje składowe mogą być **`const`** kwalifikowane i nawet **`const`** przeciążone. Wartość **`const`** typu nie może być modyfikowana po zainicjowaniu.

```cpp

const double PI = 3.1415;
PI = .75 //Error. Cannot modify const variable.
```

**`const`** Kwalifikator jest szeroko używany w deklaracjach funkcji i zmiennych i "poprawność const" jest ważnym pojęciem w języku C++; zasadniczo oznacza to **`const`** , że w czasie kompilacji nie są one modyfikowane przypadkowo. Aby uzyskać więcej informacji, zobacz [`const`](../cpp/const-cpp.md).

**`const`** Typ różni się od wersji niestałej, na przykład, **`const int`** jest typem odrębnym od **`int`** . Operatora C++ można użyć **`const_cast`** w rzadkich przypadkach, gdy należy usunąć *const-stałość* ze zmiennej. Aby uzyskać więcej informacji, zobacz [konwersje typów i bezpieczeństwo typów](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="string-types"></a>Typy ciągu

Dokładnie mówiąc, język C++ nie ma wbudowanego typu ciągu; **`char`** i **`wchar_t`** przechowywanie pojedynczych znaków — należy zadeklarować tablicę tych typów do przybliżonego ciągu, dodając kończącą wartość null (na przykład ASCII) do elementu tablicy, który znajduje się za `'\0'` ostatnim prawidłowym znakiem (nazywanym również *ciągiem w stylu C*). Ciągi stylu C wymagały znacznie więcej kodu lub korzystania z funkcji zewnętrznej biblioteki obsługującej ciągi. Ale w nowoczesnych językach C++ mamy standardowe typy biblioteki `std::string` (dla ciągów znaków 8-bitowych **`char`** ) lub `std::wstring` (dla ciągów znaków 16-bitowych **`wchar_t`** ). Te kontenery standardowej biblioteki C++ można traktować jako natywne typy ciągów, ponieważ są częścią standardowych bibliotek, które są zawarte w dowolnym zgodnym środowisku kompilacji C++. Po prostu Użyj `#include <string>` dyrektywy, aby udostępnić te typy w programie. (Jeśli używasz biblioteki MFC lub ATL, `CString` Klasa jest również dostępna, ale nie jest częścią standardu C++). Użycie tablic znaków zakończonych znakiem null (wcześniej wspomniane ciągi stylu C) jest zdecydowanie odradzane w nowoczesnej C++.

## <a name="user-defined-types"></a>Typy definiowane przez użytkownika

Podczas definiowania **`class`** , **`struct`** , **`union`** , lub **`enum`** , Ta konstrukcja jest używana w pozostałej części kodu, tak jakby był to typ podstawowy. Zajmuje znany obszar w pamięci, a niektóre zasady sposobu, w jaki można go używać, dotyczą sprawdzania w czasie kompilacji i w trakcie uruchomienia, przez cały okres istnienia programu. Główne różnice między głównymi wbudowanymi typami a typami definiowanymi przez użytkownika są następujące:

- Kompilator nie ma wbudowanej wiedzy o typie zdefiniowanym przez użytkownika. Informacje o typie pojawiają się po pierwszym napotkaniu definicji podczas procesu kompilacji.

- Ty określasz, jakie operacje mogą zostać przeprowadzone na typie i jak może on zostać przekonwertowany do innych typów, definiując (przez przeciążenie) odpowiednie operatory, albo jako funkcje składowych, albo jako funkcje, które nie są składowymi. Aby uzyskać więcej informacji, zobacz [przeciążanie funkcji](function-overloading.md)

## <a name="pointer-types"></a>Typy wskaźnika

Datowanie z powrotem do najstarszych wersji języka C, C++ w dalszym ciągu można zadeklarować zmienną typu wskaźnika przy użyciu specjalnych deklarator **`*`** (gwiazdka). Typ wskaźnika przechowuje adres lokalizacji w pamięci, gdzie jest przechowywana rzeczywista wartość danych. W nowoczesnych językach C++ są one określane jako *surowe wskaźniki* i są dostępne w kodzie za pomocą specjalnych operatorów **`*`** (gwiazdka) lub **`->`** (kreska z większą liczbą). Jest to nazywane *wyłuskaniem*, który jest używany przez użytkownika, zależy od tego, czy odwołujesz wskaźnik do wartości skalarnej, czy wskaźnika do elementu członkowskiego w obiekcie. Praca z typami wskaźników od dawna jest jednym z najtrudniejszych i najbardziej dezorientujących aspektów tworzenia programów w C i C++. Ta sekcja zawiera opis niektórych faktów i praktyk, które ułatwiają korzystanie z nieprzetworzonych wskaźników, ale w nowoczesnych C++ nie jest już wymagane (lub zalecane) do używania surowych wskaźników dla własności obiektu, ze względu na ewolucję [inteligentnego wskaźnika](../cpp/smart-pointers-modern-cpp.md) (omówiona więcej na końcu tej sekcji). Nadal jest użyteczne i bezpieczne używanie surowych wskaźników do obserwacji obiektów, ale jeśli musisz użyć ich do własności obiektu, należy to zrobić z ostrożnością i po bardzo starannym rozważeniu sposobu, w jaki obiekty przez nie posiadane są tworzone i niszczone.

Pierwszą rzeczą, którą należy wiedzieć przy deklarowaniu zmiennej surowego wskaźnika, jest to, że zmienna przydzieli tylko pamięć, która jest niezbędna do przechowania adresu lokalizacji pamięci, do którego odwoła się wskaźnik po wyłuskaniu. Alokacja pamięci dla samej wartości danych (nazywanej również *magazynem zapasowym*) nie jest jeszcze przypisana. Innymi słowy, przez zadeklarowanie zmiennej surowego wskaźnika tworzysz zmienną adresu pamięci, a nie zmienną rzeczywistych danych. \Wyłuskanie zmiennej wskaźnika przed upewnieniem się, że zawiera ona prawidłowy adres magazynu zapasowego, spowoduje niezdefiniowane zachowanie (zwykle błąd krytyczny) w programie. Poniższy przykład przedstawia ten rodzaj błędu:

```cpp
int* pNumber;       // Declare a pointer-to-int variable.
*pNumber = 10;      // error. Although this may compile, it is
                    // a serious error. We are dereferencing an
                    // uninitialized pointer variable with no
                    // allocated memory to point to.
```

Przykład wyłuskuje typ wskaźnika, bez przydzielania pamięci na przechowywanie rzeczywistych danych całkowitoliczbowych lub prawidłowego przypisanego adresu pamięci. Poniższy kod poprawia te błędy:

```cpp
    int number = 10;          // Declare and initialize a local integer
                              // variable for data backing store.
    int* pNumber = &number;   // Declare and initialize a local integer
                              // pointer variable to a valid memory
                              // address to that backing store.
...
    *pNumber = 41;            // Dereference and store a new value in
                              // the memory pointed to by
                              // pNumber, the integer variable called
                              // "number". Note "number" was changed, not
                              // "pNumber".
```

Poprawiony przykład kodu używa lokalnej pamięci stosu do utworzenia magazynu zapasowego, który `pNumber` wskazuje na. Dla uproszczenia używamy podstawowego typu. W rzeczywistości magazyn zapasowy dla wskaźników jest najczęściej zdefiniowanym przez użytkownika typami, które są przydzielane dynamicznie w obszarze pamięci o nazwie *sterta* (lub *bezpłatna wersja magazynu*) za pomocą **`new`** wyrażenia słowa kluczowego (w programowaniu w stylu języka c, użyto starszej `malloc()` funkcji biblioteki środowiska uruchomieniowego języka c). Po przydzieleniu te zmienne są zwykle określane jako obiekty, zwłaszcza jeśli są one oparte na definicji klasy. Pamięć przydzielona za pomocą **`new`** musi zostać usunięta przez odpowiednią **`delete`** instrukcję (lub, jeśli użyto `malloc()` funkcji do jej przydzielenia, funkcja środowiska uruchomieniowego języka C `free()` ).

Można jednak łatwo zapomnieć o usunięciu dynamicznie przydzielanego obiektu, szczególnie w złożonym kodzie, co powoduje błąd zasobu o nazwie *wyciek pamięci*. Z tego powodu zdecydowanie odradza się stosowanie surowych wskaźników w nowoczesnym języku C++. Niemal zawsze lepiej jest otoczyć surowy wskaźnik w [inteligentnym wskaźniku](../cpp/smart-pointers-modern-cpp.md), który automatycznie zwolni pamięć, gdy jego destruktor jest wywoływany (gdy kod wykracza poza zakres dla inteligentnego wskaźnika); Korzystając z inteligentnych wskaźników, możesz praktycznie wyeliminować całą klasę usterek w programach języka C++. W poniższym przykładzie Załóżmy, `MyClass` że jest typem zdefiniowanym przez użytkownika, który ma metodę publiczną `DoSomeWork();`

```cpp
void someFunction() {
    unique_ptr<MyClass> pMc(new MyClass);
    pMc->DoSomeWork();
}
  // No memory leak. Out-of-scope automatically calls the destructor
  // for the unique_ptr, freeing the resource.
```

Aby uzyskać więcej informacji o inteligentnych wskaźnikach, zobacz [inteligentne wskaźniki](../cpp/smart-pointers-modern-cpp.md).

Aby uzyskać więcej informacji na temat konwersji wskaźników, zobacz [konwersje typów i bezpieczeństwo typów](../cpp/type-conversions-and-type-safety-modern-cpp.md).

Aby uzyskać więcej informacji na temat ogólnych wskaźników, zobacz [wskaźniki](../cpp/pointers-cpp.md).

## <a name="windows-data-types"></a>Typy danych Windows

W klasycznym programowaniu Win32 dla języków C i C++, większość funkcji korzysta z określonych w systemie Windows elementów typedef i `#define` makr (zdefiniowanych w `windef.h` ), aby określić typy parametrów i zwracanych wartości. Te typy danych systemu Windows są głównie tylko specjalnymi nazwami (aliasami) nadanymi wbudowanym typom C/C++. Aby zapoznać się z pełną listą tych elementów typedef i definicji preprocesora, zobacz [typy danych systemu Windows](/windows/win32/WinProg/windows-data-types). Niektóre z tych typów, takich jak `HRESULT` i `LCID` , są przydatne i opisowe. Inne, takie jak `INT` , nie mają specjalnego znaczenia i są po prostu aliasami dla podstawowych typów języka C++. Inne typy danych systemu Windows mają nazwy pochodzące z czasów programowania w C i procesorów 16-bitowych. Nie mają one żadnego celu ani znaczenia w przypadku nowoczesnego sprzętu lub systemu operacyjnego. Istnieją również specjalne typy danych powiązane z biblioteką środowisko wykonawcze systemu Windows, wymienione jako [środowisko wykonawcze systemu Windows podstawowe typy danych](/windows/win32/WinRT/base-data-types). W nowoczesnym C++, ogólną wytyczną jest preferowanie typów podstawowych języka C++, chyba że typ Windows komunikuje jakieś dodatkowe znaczenie o sposobie interpretowania wartości.

## <a name="more-information"></a>Więcej informacji

Aby uzyskać więcej informacji dotyczących typu systemu C++, zobacz następujące tematy.

[Typy wartości](../cpp/value-types-modern-cpp.md)\
Opisuje *typy wartości* wraz z problemami związanymi z ich użyciem.

[Konwersje typów i bezpieczeństwo typów](../cpp/type-conversions-and-type-safety-modern-cpp.md)\
Opisuje typowe problemy przy konwersji typu i pokazuje, jak ich unikać.

## <a name="see-also"></a>Zobacz też

[Witamy ponownie w języku C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[Dokumentacja języka C++](../cpp/cpp-language-reference.md)<br/>
[Standardowa biblioteka języka C++](../standard-library/cpp-standard-library-reference.md)

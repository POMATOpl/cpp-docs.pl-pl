---
title: Ulepszenia zgodności języka C++
ms.date: 08/04/2020
description: Program Microsoft C++ w programie Visual Studio postępuje w kierunku pełnej zgodności ze standardem języka C++ 20.
ms.technology: cpp-language
ms.openlocfilehash: fc88406a3d2e291d06e01c3e92261b8dfc624ced
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921428"
---
# <a name="c-conformance-improvements-in-visual-studio"></a>Ulepszenia zgodności języka C++ w programie Visual Studio

Program Microsoft C++ zapewnia zgodność z poprawkami i poprawek błędów w każdej wersji. W tym artykule przedstawiono ulepszenia w wersji głównej, a następnie według wersji. Zawiera również listę najważniejszych poprawek błędów według wersji. Aby przejść bezpośrednio do zmian w określonej wersji, użyj na liście **w tym artykule** .

::: moniker range="msvc-160"

## <a name="conformance-improvements-in-visual-studio-2019-rtw-version-160"></a><a name="improvements_160"></a> Udoskonalenia zgodności w programie Visual Studio 2019 RTW (wersja 16,0)

Program Visual Studio 2019 RTW zawiera następujące ulepszenia zgodności, poprawki błędów i zmiany zachowań w kompilatorze języka Microsoft C++ (MSVC)

**Uwaga:** Funkcje języka c++ 20 zostaną udostępnione w **`/std:c++latest`** trybie do momentu ukończenia implementacji języka c++ 20 dla kompilatora i IntelliSense. W tym czasie **`/std:c++20`** zostanie wprowadzony tryb kompilatora.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Ulepszono obsługę modułów dla szablonów i wykrywania błędów

Moduły są teraz oficjalnie w standardzie C++ 20. Ulepszona obsługa została dodana w programie Visual Studio 2017 w wersji 15,9. Aby uzyskać więcej informacji, zobacz [lepsza obsługa szablonów i wykrywanie błędów w modułach języka C++ z MSVC 2017 w wersji 15,9](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Zmodyfikowano specyfikację typu agregacji

Specyfikacja typu agregacji została zmieniona w języku C++ 20 (zobacz [Zabroń agregowania w konstruktorach zadeklarowanych przez użytkownika](https://wg21.link/p1008r1)). W programie Visual Studio 2019, w obszarze **`/std:c++latest`** , Klasa z dowolnym konstruktorem zadeklarowanym przez użytkownika (na przykład, łącznie z konstruktorem zadeklarowanym `= default` lub `= delete` ) nie jest agregacją. Wcześniej tylko konstruktory dostarczone przez użytkownika nie kwalifikują klasy jako agregacji. Ta zmiana powoduje dodatkowe ograniczenia dotyczące sposobu inicjowania takich typów.

Poniższy kod kompiluje się bez błędów w programie Visual Studio 2017, ale zgłasza błędy C2280 i C2440 w programie Visual Studio 2019 w obszarze **`/std:c++latest`** :

```cpp
struct A
{
    A() = delete; // user-declared ctor
};

struct B
{
    B() = default; // user-declared ctor
    int i = 0;
};

A a{}; // ill-formed in C++20, previously well-formed
B b = { 1 }; // ill-formed in C++20, previously well-formed
```

### <a name="partial-support-for-operator-"></a>Częściowa pomoc techniczna dla `operator <=>`

[P0515R3](https://wg21.link/p0515r3) W języku c++ 20 wprowadzono `<=>` trójwymiarowy operator porównania, znany również jako "operator Spaceship". Program Visual Studio 2019 w **`/std:c++latest`** trybie zawiera częściową obsługę operatora przez podnoszenie błędów dla składni, która jest obecnie niedozwolona. Na przykład poniższy kod kompiluje się bez błędów w programie Visual Studio 2017, ale wywołuje wiele błędów w programie Visual Studio 2019 w **`/std:c++latest`** :

```cpp
struct S
{
    bool operator<=(const S&) const { return true; }
};

template <bool (S::*)(const S&) const>
struct U { };

int main(int argc, char** argv)
{
    U<&S::operator<=> u; // In Visual Studio 2019 raises C2039, 2065, 2146.
}
```

Aby uniknąć błędów, Wstaw spację w wierszu powodującym problemy przed końcowym nawiasem ostrym: `U<&S::operator<= > u;` .

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>Odwołania do typów z niezgodnymi kwalifikatorami CV

Wcześniej MSVC dozwolone bezpośrednie powiązanie odwołania z typu z niezgodnymi kwalifikatorami CV poniżej najwyższego poziomu. To powiązanie może umożliwić modyfikację danych supposedly const, do których odwołuje się odwołanie. Kompilator tworzy teraz tymczasowy, zgodnie z wymaganiami Standard. W programie Visual Studio 2017 następujący kod kompiluje się bez ostrzeżeń. W programie Visual Studio 2019 kompilator zgłasza ostrzeżenie C4172: `<func:#1 "?PData@X@@QBEABQBXXZ"> returning address of local variable or temporary.` :

```cpp
struct X
{
    const void* const& PData() const
    {
        return _pv;
    }

    void* _pv;
};

int main()
{
    X x;
    auto p = x.PData(); // C4172
}
```

### <a name="reinterpret_cast-from-an-overloaded-function"></a>`reinterpret_cast` ze przeciążonej funkcji

Argument, który **`reinterpret_cast`** nie jest jednym z kontekstów, w których dozwolony jest adres przeciążonej funkcji. Poniższy kod kompiluje się bez błędów w programie Visual Studio 2017, ale w programie Visual Studio 2019 zgłasza błąd C2440: `cannot convert from 'overloaded-function' to 'fp'` :

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f);
}
```

Aby uniknąć tego błędu, użyj dozwolonego rzutowania w tym scenariuszu:

```cpp
int f(int);
int f(float);
using fp = int(*)(int);

int main()
{
    fp r = static_cast<fp>(&f); // or just &f;
}
```

### <a name="lambda-closures"></a>Zamknięcia lambda

W języku C++ 14 typy zamknięć lambda nie są literałami. Podstawową konsekwencją tej reguły jest to, że wyrażenie lambda nie może być przypisane do **`constexpr`** zmiennej. Poniższy kod kompiluje się bez błędów w programie Visual Studio 2017, ale w programie Visual Studio 2019 zgłasza błąd C2127: `'l': illegal initialization of 'constexpr' entity with a non-constant expression` :

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Aby uniknąć tego błędu, Usuń **`constexpr`** kwalifikator lub zmień tryb zgodności na **`/std:c++17`** .

### <a name="stdcreate_directory-failure-codes"></a>`std::create_directory` Kody błędów

Implementacja [P1164](https://wg21.link/p1164r1) z c++ 20 bezwarunkowo. Ta zmiana polega `std::create_directory` na sprawdzeniu, czy element docelowy był już katalogiem w przypadku niepowodzenia. Poprzednio wszystkie błędy typu ERROR_ALREADY_EXISTS były przełączane do kodów, które nie zostały utworzone.

### `operator<<(std::ostream, nullptr_t)`

Na [LWG 2221](https://cplusplus.github.io/LWG/issue2221)dodano `operator<<(std::ostream, nullptr_t)` do zapisu nullptrs do strumieni.

### <a name="additional-parallel-algorithms"></a>Dodatkowe algorytmy równoległe

Nowe równoległe wersje systemów `is_sorted` ,,,, `is_sorted_until` `is_partitioned` `set_difference` `set_intersection` `is_heap` i `is_heap_until` .

### <a name="atomic-initialization"></a>Inicjalizacja niepodzielna

[P0883 "naprawianie niepodzielnych inicjacji"](https://wg21.link/p0883r1) zmiany `std::atomic` wartości — inicjowanie zawartej w nim funkcji T zamiast default-inicjowanie. Poprawka jest włączona w przypadku używania Clang/LLVM z biblioteką standard firmy Microsoft. Jest on obecnie wyłączony dla kompilatora języka Microsoft C++, jako obejście błędu w **`constexpr`** przetwarzaniu.

### <a name="remove_cvref-and-remove_cvref_t"></a>`remove_cvref` i `remove_cvref_t`

Zaimplementowano `remove_cvref` `remove_cvref_t` cechy typu i z [P0550](https://wg21.link/p0550r2). Te Remove Reference-stałość i CV-kwalifikacje z typu bez obsłużenia funkcji i tablic do wskaźników (w przeciwieństwie do `std::decay` i `std::decay_t` ).

### <a name="feature-test-macros"></a>Testowanie funkcji — makra

[Makra P0941R2-Feature-test](https://wg21.link/p0941r2) zostały wykonane z obsługą programu `__has_cpp_attribute` . Makra funkcji-test są obsługiwane we wszystkich trybach standardowych.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Zabroń agregowania dla konstruktorów zadeklarowanych przez użytkownika

[C++ 20 P1008R1 — Zabroń agregacji z konstruktorami zadeklarowanymi przez użytkownika](https://wg21.link/p1008r1) .

## <a name="conformance-improvements-in-161"></a><a name="improvements_161"></a> Ulepszenia zgodności w 16,1

### <a name="char8_t"></a>char8_t

[P0482r6](https://wg21.link/p0482r6). C++ 20 dodaje nowy typ znaku, który jest używany do reprezentowania jednostek kodu UTF-8. `u8` Literały ciągu w języku C++ 20 mają typ `const char8_t[N]` zamiast `const char[N]` , który był wcześniej w przypadku. Podobne zmiany zostały zaproponowane dla standardu C w [N2231](https://wg14.link/n2231). Sugestie dotyczące **`char8_t`** korygowania zgodności z poprzednimi wersjami są podano w [P1423r3](https://wg21.link/p1423r3). Kompilator języka Microsoft C++ dodaje obsługę programu **`char8_t`** w programie Visual Studio 2019 w wersji 16,1 podczas określania **`/Zc:char8_t`** opcji kompilatora. W przyszłości będzie ona obsługiwana przez [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) program, który można przywrócić do zachowania języka c++ 17 za pośrednictwem programu **`/Zc:char8_t-`** . Kompilator EDG, który nie obsługuje jeszcze technologii IntelliSense. Mogą być widoczne fałszywe błędy tylko IntelliSense, które nie mają wpływu na rzeczywistą kompilację.

#### <a name="example"></a>Przykład

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtype_identity-metafunction-and-stdidentity-function-object"></a>std:: type_identitybinding i obiekt funkcji std:: Identity

[P0887R1 type_identity](https://wg21.link/p0887r1). Przestarzałe `std::identity` rozszerzenie szablonu klasy zostało usunięte i zastąpione przez obiekt funkcyjny języka c++ 20 `std::type_identity` `std::identity` . Oba są dostępne tylko w [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) .

Poniższy przykład generuje ostrzeżenie o zaniechaniu C4996 dla `std::identity` (zdefiniowane w \<type_traits> ) w programie Visual Studio 2017:

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

Poniższy przykład pokazuje, jak używać nowego `std::identity` (zdefiniowanego w programie \<functional> ) razem z nowym `std::type_identity` :

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>Sprawdzanie składni dla rodzajowych wyrażeń lambda

Nowy procesor lambda umożliwia pewną składnię w trybie zgodności, która sprawdza w ogólnym wyrażeniu lambda, w obszarze [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) lub w dowolnym innym trybie języka z **`/experimental:newLambdaProcessor`** .

W programie Visual Studio 2017 ten kod kompiluje się bez ostrzeżeń, ale w programie Visual Studio 2019 generuje błąd C2760 `syntax error: unexpected token '\<id-expr>', expected 'id-expression'` :

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t;
    };
}
```

Poniższy przykład pokazuje poprawną składnię, która jest teraz wymuszana przez kompilator:

```cpp
void f() {
    auto a = [](auto arg) {
        typename decltype(arg)::Type t;
    };
}
```

### <a name="argument-dependent-lookup-for-function-calls"></a>Wyszukiwanie wywołań funkcji zależnych od argumentów

[P0846R0](https://wg21.link/p0846r0) (c++ 20) zwiększona możliwość znajdowania szablonów funkcji przez wyszukiwanie zależne od argumentów dla wyrażeń wywołania funkcji z jawnymi argumentami szablonu. Wymaga **`/std:c++latest`** .

### <a name="designated-initialization"></a>Wyznaczono inicjalizację

[P0329R4](https://wg21.link/p0329r4) (c++ 20) *wyznaczoną inicjalizację* umożliwia wybranie określonych elementów członkowskich w ramach inicjalizacji agregacji przy użyciu `Type t { .member = expr }` składni. Wymaga **`/std:c++latest`** .

### <a name="new-and-updated-standard-library-functions-c20"></a>Nowe i zaktualizowane funkcje biblioteki standardowej (C++ 20)

- `starts_with()` i `ends_with()` dla `basic_string` i `basic_string_view` .
- `contains()` dla kontenerów asocjacyjnych.
- `remove()`, `remove_if()` i `unique()` dla obiektów `list` i `forward_list` zwracają teraz obiekt `size_type`.
- `shift_left()` i `shift_right()` dodane do obiektu \<algorithm>.

## <a name="conformance-improvements-in-162"></a><a name="improvements_162"></a> Ulepszenia zgodności w 16,2

### <a name="noexcept-constexpr-functions"></a>`noexcept``constexpr`funkcje

**`constexpr`** funkcje nie są już traktowane **`noexcept`** Domyślnie, gdy są używane w wyrażeniu stałym. Ta zmiana zachowania pochodzi z rozwiązania [CWG 1351](https://wg21.link/cwg1351) i jest włączona w programie [`/permissive-`](../build/reference/permissive-standards-conformance.md) . Poniższy przykład kompiluje w programie Visual Studio 2019 w wersji 16,1 i starszej, ale tworzy C2338 w programie Visual Studio 2019 w wersji 16,2:

```cpp
constexpr int f() { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept"); // C2338 in 16.2
}
```

Aby naprawić ten błąd, Dodaj **`noexcept`** wyrażenie do deklaracji funkcji:

```cpp
constexpr int f() noexcept { return 0; }

int main() {
    static_assert(noexcept(f()), "f should be noexcept");
}
```

### <a name="binary-expressions-with-different-enum-types"></a>Wyrażenia binarne z różnymi typami wyliczeniowymi

Język c++ 20 zakończył normalne konwersje arytmetyczne dla operandów, gdzie:

- Jeden operand jest typu wyliczeniowego i

- druga jest innego typu wyliczeniowego lub typu zmiennoprzecinkowego.

Aby uzyskać więcej informacji, zobacz [P1120R0](https://wg21.link/p1120r0).

W programie Visual Studio 2019 w wersji 16,2 lub nowszej Poniższy kod generuje ostrzeżenie poziomu 4, gdy [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) Opcja kompilatora jest włączona:

```cpp
enum E1 { a };
enum E2 { b };
int main() {
    int i = a | b; // warning C5054: operator '|': deprecated between enumerations of different types
}
```

Aby uniknąć tego ostrzeżenia, należy użyć [static_cast](../cpp/static-cast-operator.md) do przekonwertowania drugiego operandu:

```cpp
enum E1 { a };
enum E2 { b };
int main() {
  int i = a | static_cast<int>(b);
}
```

Przy użyciu operacji binarnej między wyliczeniem a typem zmiennoprzecinkowym jest teraz ostrzeżenie, gdy [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) Opcja kompilatora jest włączona:

```cpp
enum E1 { a };
int main() {
  double i = a * 1.1;
}
```

Aby uniknąć tego ostrzeżenia, należy użyć [static_cast](../cpp/static-cast-operator.md) do przekonwertowania drugiego operandu:

```cpp
enum E1 { a };
int main() {
   double i = static_cast<int>(a) * 1.1;
}
```

### <a name="equality-and-relational-comparisons-of-arrays"></a>Porównanie równości i relacyjnych tablic

Porównania równości i relacyjnych między dwoma operandami typu Array są przestarzałe w języku C++ 20 ([P1120R0](https://wg21.link/p1120r0)). Innymi słowy, operacja porównania między dwiema tablicami (Pomimo rangi i zakresu podobieństwa) jest teraz ostrzeżeniem. Począwszy od programu Visual Studio 2019 w wersji 16,2, poniższy kod generuje C5056: `operator '==': deprecated for array types` po [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) włączeniu opcji kompilatora:

```cpp
int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 1, 2, 3 };
    if (a == b) { return 1; }
}
```

Aby uniknąć ostrzeżenia, można porównać adresy pierwszego elementu:

```cpp
int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 1, 2, 3 };
    if (&a[0] == &b[0]) { return 1; }
}
```

Aby określić, czy zawartość dwóch tablic jest równa, użyj funkcji [std:: EQUAL](../standard-library/algorithm-functions.md#equal) :

```cpp
std::equal(std::begin(a), std::end(a), std::begin(b), std::end(b));
```

### <a name="effect-of-defining-spaceship-operator-on--and-"></a>Wpływ definiowania operatora Spaceship na `==` i `!=`

Definicja samego operatora Spaceship ( **`<=>`** ) nie będzie już ponownie pisać wyrażeń obejmujących **`==`** lub **`!=`** , chyba że operator Spaceship jest oznaczony jako **`= default`** ( [P1185R2](https://wg21.link/p1185r2)). Poniższy przykład kompiluje się w programie Visual Studio 2019 RTW i w wersji 16,1, ale produkuje C2678 w programie Visual Studio 2019 w wersji 16,2:

```cpp
#include <compare>

struct S {
  int a;
  auto operator<=>(const S& rhs) const {
    return a <=> rhs.a;
  }
};
bool eq(const S& lhs, const S& rhs) {
  return lhs == rhs;
}
bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

Aby uniknąć tego błędu, zdefiniuj operator = = lub Zadeklaruj go jako domyślny:

```cpp
#include <compare>

struct S {
  int a;
  auto operator<=>(const S& rhs) const {
    return a <=> rhs.a;
  }
  bool operator==(const S&) const = default;
};
bool eq(const S& lhs, const S& rhs) {
  return lhs == rhs;
}
bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

### <a name="standard-library-improvements"></a>Ulepszenia biblioteki standardowej

- \<charconv>`to_chars()`z dokładnością stałą/naukową. (Ogólna precyzja jest obecnie planowana dla 16,4).
- [P0020R6](https://wg21.link/p0020r6): niepodzielna, niepodzielna \<float> \<double> , niepodzielna\<long double>
- [P0463R1](https://wg21.link/p0463r1): endian
- [P0482R6](https://wg21.link/p0482r6): obsługa biblioteki dla char8_t
- [P0600R1](https://wg21.link/p0600r1): [ \[ nodiscard]] dla STL, część 1
- [P0653R2](https://wg21.link/p0653r2): to_address ()
- [P0754R2](https://wg21.link/p0754r2): \<version>
- [P0771R1](https://wg21.link/p0771r1): noexcept for std:: Function — Konstruktor

## <a name="conformance-improvements-in-visual-studio-2019-version-163"></a><a name="improvements_163"></a> Ulepszenia zgodności w programie Visual Studio 2019 w wersji 16,3

### <a name="stream-extraction-operators-for-char-removed"></a>Operatory wyodrębniania strumienia dla char * usunięte

Operatory wyodrębniania strumienia dla wskaźników do znaków zostały usunięte i zastąpione przez operatory wyodrębniania tablic-znaków (na [P0487R1](https://wg21.link/p0487r1)). WG21 traktuje usunięte przeciążenia jako niebezpieczne. W [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) trybie w poniższym przykładzie jest teraz tworzony C2679: `binary '>>': no operator found which takes a right-hand operand of type 'char*' (or there is no acceptable conversion)` :

```cpp
   char x[42];
   char* p = x;
   std::cin >> std::setw(42);
   std::cin >> p;
```

Aby uniknąć tego błędu, należy użyć operatora wyodrębniania z zmienną Char []:

```cpp
char x[42];
std::cin >> x;
```

### <a name="new-keywords-requires-and-concept"></a>Nowe słowa kluczowe `requires` i `concept`

Nowe słowa kluczowe **`requires`** i zostały **`concept`** dodane do kompilatora języka Microsoft C++. Jeśli spróbujesz użyć jednego z nich jako identyfikatora w [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) trybie, kompilator zgłosi C2059: `syntax error` .

### <a name="constructors-as-type-names-disallowed"></a>Konstruktory jako nazwy typów są niedozwolone

Kompilator nie traktuje już nazw konstruktorów jako wstrzykiwanych nazw klas w tym przypadku: Kiedy pojawiają się w kwalifikowanej nazwie po aliasie specjalizacji szablonu klasy. Wcześniej konstruktory były użyteczny jako nazwa typu w celu zadeklarować innych jednostek. Poniższy przykład tworzy teraz C3646: `'TotalDuration': unknown override specifier` :

```cpp
#include <chrono>

class Foo {
   std::chrono::milliseconds::duration TotalDuration{};
};

```

Aby uniknąć tego błędu, zadeklaruj `TotalDuration` jak pokazano poniżej:

```cpp
#include <chrono>

class Foo {
  std::chrono::milliseconds TotalDuration {};
};
```

### <a name="stricter-checking-of-extern-c-functions"></a>Dokładniejsze sprawdzanie `extern "C"` funkcji

Jeśli **`extern "C"`** funkcja została zadeklarowana w różnych obszarach nazw, poprzednie wersje kompilatora języka Microsoft C++ nie sprawdzają, czy deklaracje były zgodne. Począwszy od programu Visual Studio 2019 w wersji 16,3, kompilator sprawdza zgodność. W [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybie w programie Poniższy kod generuje błędy C2371 `redefinition; different basic types` i C2733 `you cannot overload a function with C linkage` :

```cpp
using BOOL = int;

namespace N
{
   extern "C" void f(int, int, int, bool);
}

void g()
{
   N::f(0, 1, 2, false);
}

extern "C" void f(int, int, int, BOOL){}
```

Aby uniknąć błędów w poprzednim przykładzie, Użyj zamiast tego **`bool`** `BOOL` spójnego w obu deklaracjach `f` .

### <a name="standard-library-improvements"></a>Ulepszenia biblioteki standardowej

Niestandardowe nagłówki \<stdexcpt.h> i zostały \<typeinfo.h> usunięte. Kod, który zawiera te elementy, powinien zamiast nich zawierać standardowe nagłówki \<exception> i \<typeinfo> , odpowiednio.

## <a name="conformance-improvements-in-visual-studio-2019-version-164"></a><a name="improvements_164"></a> Ulepszenia zgodności w programie Visual Studio 2019 w wersji 16,4

### <a name="better-enforcement-of-two-phase-name-lookup-for-qualified-ids-in-permissive-"></a>Lepsze wymuszanie dwufazowego wyszukiwania nazw dla kwalifikujących się identyfikatorów w `/permissive-`

Dwufazowe wyszukiwanie nazw wymaga, aby nazwy niezależne używane w treści szablonu musiały być widoczne dla szablonu w czasie definicji. Wcześniej takie nazwy mogły zostać znalezione podczas tworzenia wystąpienia szablonu. Ta zmiana ułatwia pisanie przenośnego i zgodnego kodu w MSVC pod [`/permissive-`](../build/reference/permissive-standards-conformance.md) flagą.

W programie Visual Studio 2019 w wersji 16,4 z **`/permissive-`**  ustawioną flagą Poniższy przykład generuje błąd, ponieważ `N::f` nie jest widoczny podczas `f<T>` definiowania szablonu:

```cpp
template <class T>
int f() {
    return N::f() + T{}; // error C2039: 'f': is not a member of 'N'
}

namespace N {
    int f() { return 42; }
}
```

Zazwyczaj ten błąd można naprawić, dołączając brakujące nagłówki lub funkcje lub zmienne deklarujące przekazywanie dalej, jak pokazano w następującym przykładzie:

```cpp
namespace N {
    int f();
}

template <class T>
int f() {
    return N::f() + T{};
}

namespace N {
    int f() { return 42; }
}
```

### <a name="implicit-conversion-of-integral-constant-expressions-to-null-pointer"></a>Niejawna konwersja wyrażeń stałych całkowitej na wskaźnik o wartości null

Kompilator MSVC implementuje teraz [CWG problem 903](https://wg21.link/cwg903) w trybie zgodności ( **`/permissive-`** ). Ta reguła nie zezwala na niejawną konwersję wyrażeń stałych całkowitych (z wyjątkiem literału liczby całkowitej "0") na stałe wskaźnika o wartości null. Poniższy przykład generuje C2440 w trybie zgodności:

```cpp
int* f(bool* p) {
    p = false; // error C2440: '=': cannot convert from 'bool' to 'bool *'
    p = 0; // OK
    return false; // error C2440: 'return': cannot convert from 'bool' to 'int *'
}
```

Aby naprawić ten błąd, użyj **`nullptr`** zamiast **`false`** . Literał 0 jest nadal dozwolony:

```cpp
int* f(bool* p) {
    p = nullptr; // OK
    p = 0; // OK
    return nullptr; // OK
}
```

### <a name="standard-rules-for-types-of-integer-literals"></a>Standardowe reguły dla typów literałów liczb całkowitych

W trybie zgodności (włączony przez [`/permissive-`](../build/reference/permissive-standards-conformance.md) ) MSVC korzysta z standardowych reguł dla typów literałów liczb całkowitych. Literały dziesiętne są zbyt duże, aby mieściły się w **`signed int`** poprzednio danym typie **`unsigned int`** . Teraz takie literały otrzymują następny największy **`signed`** typ Integer, **`long long`** . Ponadto literały z sufiksem "" są zbyt duże, aby mieściły się w **`signed`** typie **`unsigned long long`** .

Ta zmiana może prowadzić do wygenerowania różnych diagnostyki ostrzeżeń i różnic w działaniu operacji arytmetycznych na literałach.

W poniższym przykładzie przedstawiono nowe zachowanie programu Visual Studio 2019 w wersji 16,4. `i`Zmienna jest teraz typu **`unsigned int`** . Dlatego to ostrzeżenie jest zgłaszane. W przypadku bitów o wysokim stopniu zmienna `j` jest ustawiana na 0.

```cpp
void f(int r) {
    int i = 2964557531; // warning C4309: truncation of constant value
    long long j = 0x8000000000000000ll >> r; // literal is now unsigned, shift will fill high-order bits with 0
}
```

W poniższym przykładzie pokazano, jak zachować stare zachowanie i uniknąć ostrzeżeń oraz zmiany zachowania w czasie wykonywania:

```cpp
void f(int r) {
int i = 2964557531u; // OK
long long j = (long long)0x8000000000000000ll >> r; // shift will keep high-order bits
}
```

### <a name="function-parameters-that-shadow-template-parameters"></a>Parametry funkcji, które są parametrami szablonu w tle

Kompilator MSVC teraz zgłasza błąd, gdy parametr funkcji zasłania parametr szablonu:

```cpp
template<typename T>
void f(T* buffer, int size, int& size_read);

template<typename T, int Size>
void f(T(&buffer)[Size], int& Size) // error C7576: declaration of 'Size' shadows a template parameter
{
    return f(buffer, Size, Size);
}
```

Aby naprawić ten błąd, Zmień nazwę jednego z parametrów:

```cpp
template<typename T>
void f(T* buffer, int size, int& size_read);

template<typename T, int Size>
void f(T (&buffer)[Size], int& size_read)
{
    return f(buffer, Size, size_read);
}
```

### <a name="user-provided-specializations-of-type-traits"></a>Specjalizacje podane przez użytkownika dla cech typu

Zgodnie z podklauzulą *meta. rqmts* w standardzie, kompilator MSVC wywołuje teraz błąd podczas znajdowania zdefiniowanej przez użytkownika specjalizacji jednego z określonych `type_traits` szablonów w `std` przestrzeni nazw. O ile nie określono inaczej, takie specjalizacje powodują niezdefiniowane zachowanie. Poniższy przykład ma niezdefiniowane zachowanie, ponieważ narusza regułę i **`static_assert`** kończy się niepowodzeniem z błędem C2338.

```cpp
#include <type_traits>
struct S;

template<>
struct std::is_fundamental<S> : std::true_type {};

static_assert(std::is_fundamental<S>::value, "fail");
```

Aby uniknąć tego błędu, Zdefiniuj strukturę, która dziedziczy z preferowanych `type_trait` i specialize:

```cpp
#include <type_traits>

struct S;

template<typename T>
struct my_is_fundamental : std::is_fundamental<T> {};

template<>
struct my_is_fundamental<S> : std::true_type { };

static_assert(my_is_fundamental<S>::value, "fail");
```

### <a name="changes-to-compiler-provided-comparison-operators"></a>Zmiany w operatorach porównania dostarczonych przez kompilator

Kompilator MSVC implementuje teraz następujące zmiany w operatorach porównania na [P1630R1](https://wg21.link/p1630r1) , gdy [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) opcja jest włączona:

Kompilator nie zapisuje już wyrażeń przy użyciu `operator==` , jeśli zawierają one zwracany typ, który nie jest **`bool`** . Poniższy kod generuje teraz błąd C2088: `'!=': illegal for struct` :

```cpp
struct U {
    operator bool() const;
};

struct S {
    U operator==(const S&) const;
};

bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

Aby uniknąć tego błędu, należy jawnie zdefiniować wymaganego operatora:

```cpp
struct U {
    operator bool() const;
};

struct S {
    U operator==(const S&) const;
    U operator!=(const S&) const;
};

bool neq(const S& lhs, const S& rhs) {
    return lhs != rhs;
}
```

Kompilator nie definiuje już domyślnego operatora porównania, jeśli jest elementem członkowskim klasy podobnej do Union. Poniższy przykład tworzy teraz błąd C2120: `'void' illegal with all types` :

```cpp
#include <compare>

union S {
    int a;
    char b;
    auto operator<=>(const S&) const = default;
};

bool lt(const S& lhs, const S& rhs) {
    return lhs < rhs;
}
```

Aby uniknąć tego błędu, zdefiniuj treść dla operatora:

```cpp
#include <compare>

union S {
    int a;
    char b;
    auto operator<=>(const S&) const { ... }
};

bool lt(const S& lhs, const S& rhs) {
    return lhs < rhs;
}
```

Kompilator nie będzie już definiować domyślnego operatora porównywania, jeśli Klasa zawiera element członkowski odwołania. Poniższy kod generuje teraz błąd C2120: `'void' illegal with all types` :

```cpp
#include <compare>

struct U {
    int& a;
    auto operator<=>(const U&) const = default;
};

bool lt(const U& lhs, const U& rhs) {
    return lhs < rhs;
}
```

Aby uniknąć tego błędu, zdefiniuj treść dla operatora:

```cpp
#include <compare>

struct U {
    int& a;
    auto operator<=>(const U&) const { ... };
};

bool lt(const U& lhs, const U& rhs) {
    return lhs < rhs;
}
```

## <a name="conformance-improvements-in-visual-studio-2019-version-165"></a><a name="improvements_165"></a> Ulepszenia zgodności w programie Visual Studio 2019 w wersji 16,5

### <a name="explicit-specialization-declaration-without-an-initializer-isnt-a-definition"></a>Jawna deklaracja specjalizacji bez inicjatora nie jest definicją

W programie `/permissive-` MSVC teraz wymusza standardową regułę, która jawne deklaracje specjalizacji bez inicjatorów nie są definicjami. Wcześniej deklaracja powinna być traktowana jako definicja z inicjatorem domyślnym. Efekt jest zauważalny w czasie łączenia, ponieważ program w zależności od tego zachowania może teraz mieć nierozpoznane symbole. Ten przykład teraz powoduje błąd:

```cpp
template <typename> struct S {
    static int a;
};

// In permissive-, this declaration isn't a definition, and the program won't link.
template <> int S<char>::a;

int main() {
    return S<char>::a;
}
```

```Output
error LNK2019: unresolved external symbol "public: static int S<char>::a" (?a@?$S@D@@2HA) referenced in function _main
at link time.
```

Aby rozwiązać ten problem, Dodaj inicjatora:

```cpp
template <typename> struct S {
    static int a;
};

// Add an initializer for the declaration to be a definition.
template <> int S<char>::a{};

int main() {
    return S<char>::a;
}
```

### <a name="preprocessor-output-preserves-newlines"></a>Dane wyjściowe preprocesora zachowują nowy wiersz

Eksperymentalny preprocesor umożliwia teraz zachowywanie nowego wiersza i odstępów podczas używania **`/P`** lub **`/E`** z **`/experimental:preprocessor`** .

Podaną przykładowe źródło,

```cpp
#define m()
line m(
) line
```

Poprzednie dane wyjściowe **`/E`** :

```Output
line line
#line 2
```

Nowe dane wyjściowe **`/E`** są teraz:

```Output
line
 line
```

### <a name="import-and-module-keywords-are-context-dependent"></a>Słowa kluczowe "Import" i "module" są zależne od kontekstu

Na P1857R1 dyrektywy preprocesora importu i modułu mają dodatkowe ograniczenia dotyczące ich składni. Ten przykład nie jest już kompilowany:

```cpp
import // Invalid
m;
```

Generuje następujący komunikat o błędzie:

```Output
error C2146: syntax error: missing ';' before identifier 'm'
```

Aby rozwiązać ten problem, należy zachować import w tym samym wierszu:

```cpp
import m; // OK
```

### <a name="removal-of-stdweak_equality-and-stdstrong_equality"></a>Usuwanie std:: weak_equality i std:: strong_equality

Scalanie P1959R0 wymaga, aby kompilator usunął zachowanie i odwołania do `std::weak_equality` `std::strong_equality` typów i.

Kod w tym przykładzie nie jest już kompilowany:

```cpp
#include <compare>

struct S {
    std::strong_equality operator<=>(const S&) const = default;
};

void f() {
    nullptr<=>nullptr;
    &f <=> &f;
    &S::operator<=> <=> &S::operator<=>;
}
```

Przykład teraz prowadzi do następujących błędów:

```Output
error C2039: 'strong_equality': is not a member of 'std'
error C2143: syntax error: missing ';' before '<=>'
error C4430: missing type specifier - int assumed. Note: C++ does not support default-int
error C4430: missing type specifier - int assumed. Note: C++ does not support default-int
error C7546: binary operator '<=>': unsupported operand types 'nullptr' and 'nullptr'
error C7546: binary operator '<=>': unsupported operand types 'void (__cdecl *)(void)' and 'void (__cdecl *)(void)'
error C7546: binary operator '<=>': unsupported operand types 'int (__thiscall S::* )(const S &) const' and 'int (__thiscall S::* )(const S &) const'
```

Aby rozwiązać ten problem, zaktualizuj, aby preferować wbudowane operatory relacyjne i zamienić usunięte typy:

```cpp
#include <compare>

struct S {
    std::strong_ordering operator<=>(const S&) const = default; // prefer 'std::strong_ordering'
};

void f() {
    nullptr != nullptr; // use pre-existing builtin operator != or ==.
    &f != &f;
    &S::operator<=> != &S::operator<=>;
}
```

### <a name="tls-guard-changes"></a>Zmiany ochrony TLS

Wcześniej zmienne lokalne wątku w bibliotekach DLL nie zostały poprawnie zainicjowane. Inne niż w wątku, który załadował bibliotekę DLL, nie zostały zainicjowane przed pierwszym użyciem w wątkach, które istniały przed załadowaniem biblioteki DLL. Ta wada została teraz poprawiona. Zmienne lokalne wątku w takiej bibliotece DLL są inicjowane natychmiast przed ich pierwszym użyciem na takich wątkach.

To nowe zachowanie testowania na potrzeby inicjowania użycia zmiennych lokalnych wątku może być wyłączone przy użyciu **`/Zc:tlsGuards-`** przełącznika kompilatora. Lub, dodając `[[msvc:no_tls_guard]]` atrybut do określonych zmiennych lokalnych wątku.

### <a name="better-diagnosis-of-call-to-deleted-functions"></a>Lepsza diagnostyka wywołania usuniętych funkcji

Naszym kompilatorem było korzystniejsze wywołania wcześniej usuniętych funkcji. Na przykład, jeśli wywołania wystąpią w kontekście treści szablonu, nie będziemy zdiagnozować wywołania. Ponadto, jeśli wystąpiły wiele wystąpień wywołań do usuniętych funkcji, firma Microsoft wystawia tylko jedną diagnostykę. Teraz wystawią diagnostykę dla każdego z nich.

Jedna z konsekwencji nowego zachowania może generować małą istotną zmianę: kod, który wywołał usuniętą funkcję, nie zostanie zdiagnozowany, jeśli nigdy nie był konieczny do generowania kodu. Teraz możemy zdiagnozować wszystko.

Ten przykład pokazuje kod, który generuje błąd:

```cpp
struct S {
  S() = delete;
  S(int) { }
};

struct U {
  U() = delete;
  U(int i): s{ i } { }

  S s{};
};

U u{ 0 };
```

```Output
error C2280: 'S::S(void)': attempting to reference a deleted function
note: see declaration of 'S::S'
note: 'S::S(void)': function was explicitly deleted
```

Aby rozwiązać ten problem, Usuń wywołania funkcji usuniętych:

```cpp
struct S {
  S() = delete;
  S(int) { }
};

struct U {
  U() = delete;
  U(int i): s{ i } { }

  S s;  // Do not call the deleted ctor of 'S'.
};

U u{ 0 };
```

## <a name="conformance-improvements-in-visual-studio-2019-version-166"></a><a name="improvements_166"></a> Ulepszenia zgodności w programie Visual Studio 2019 w wersji 16,6

### <a name="standard-library-streams-reject-insertions-of-mis-encoded-character-types"></a>Strumienie biblioteki standardowej odrzucają wstawienia niezakodowanych typów znaków

Tradycyjnie, wstawianie **`wchar_t`** do `std::ostream` i wstawianie **`char16_t`** lub **`char32_t`** do `std::ostream` lub `std::wostream` , wyprowadza jego wartość całkowitą. Wstawianie wskaźników do tych typów znaków wyprowadza wartość wskaźnika. Programiści nie znajdują żadnego przypadku intuicyjnego. Często oczekuje się, że standardowa biblioteka transkodowanie znak lub ciąg znaku zakończony wartością null, a następnie wyprowadza wynik.

Propozycja C++ 20 [P1423R3](https://wg21.link/p1423r3) dodaje usunięte przeciążenia operatora wstawiania strumienia dla tych kombinacji typów strumienia i znaku lub znaku. W obszarze **`/std:c++latest`** przeciążenia przeciążenia sprawiają, że te wstawienia zostały nieprawidłowo sformułowane, a nie zachowujeją się w sposób nieoczekiwany. Kompilator zgłasza błąd C2280, gdy zostanie znaleziony. W `_HAS_STREAM_INSERTION_OPERATORS_DELETED_IN_CXX20` `1` celu przywrócenia starego zachowania można zdefiniować makro "do kreski ucieczki". (Propozycja usuwa również operatory wstawiania strumienia dla **`char8_t`** . Nasza biblioteka standardowa zaimplementował podobne przeciążenia, gdy dodaliśmy **`char8_t`** obsługę, więc zachowanie "niewłaściwe" nigdy nie było dostępne dla programu **`char8_t`** .)

Ten przykład pokazuje zachowanie z tą zmianą:

```cpp
#include <iostream>
int main() {
    const wchar_t cw = L'x', *pw = L"meow";
    const char16_t c16 = u'x', *p16 = u"meow";
    const char32_t c32 = U'x', *p32 = U"meow";
    std::cout << cw << ' ' << pw << '\n';
    std::cout << c16 << ' ' << p16 << '\n';
    std::cout << c32 << ' ' << p32 << '\n';
    std::wcout << c16 << ' ' << p16 << '\n';
    std::wcout << c32 << ' ' << p32 << '\n';
}
```

Kod tworzy teraz te komunikaty diagnostyczne:

```Output
error C2280: 'std::basic_ostream<char,std::char_traits<char>> &std::<<<std::char_traits<char>>(std::basic_ostream<char,std::char_traits<char>> &,wchar_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<char,std::char_traits<char>> &std::<<<std::char_traits<char>>(std::basic_ostream<char,std::char_traits<char>> &,char16_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<char,std::char_traits<char>> &std::<<<std::char_traits<char>>(std::basic_ostream<char,std::char_traits<char>> &,char32_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::<<<std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,char16_t)': attempting to reference a deleted function
error C2280: 'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::<<<std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,char32_t)': attempting to reference a deleted function
```

Efekt starego zachowania można osiągnąć we wszystkich trybach języka, konwertując typy znaków na **`unsigned int`** lub typy wskaźnika do znaków na `const void*` :

```c++
#include <iostream>
int main() {
    const wchar_t cw = L'x', *pw = L"meow";
    const char16_t c16 = u'x', *p16 = u"meow";
    const char32_t c32 = U'x', *p32 = U"meow";
    std::cout << (unsigned)cw << ' ' << (const void*)pw << '\n'; // Outputs "120 0052B1C0"
    std::cout << (unsigned)c16 << ' ' << (const void*)p16 << '\n'; // Outputs "120 0052B1CC"
    std::cout << (unsigned)c32 << ' ' << (const void*)p32 << '\n'; // Outputs "120 0052B1D8"
    std::wcout << (unsigned)c16 << ' ' << (const void*)p16 << '\n'; // Outputs "120 0052B1CC"
    std::wcout << (unsigned)c32 << ' ' << (const void*)p32 << '\n'; // Outputs "120 0052B1D8"
}
```

### <a name="changed-return-type-of-stdpow-for-stdcomplex"></a>Zmieniony typ zwracany `std::pow()` dla elementu `std::complex`

Wcześniej implementacja MSVC reguł podwyższania poziomu dla zwracanego typu szablonu funkcji `std::pow()` była nieprawidłowa. Na przykład poprzednio `pow(complex<float>, int)` zwrócone `complex<float>` . Teraz poprawnie zwraca `complex<double>` . Poprawka została wdrożona bezwarunkowo dla wszystkich trybów standardów w programie Visual Studio 2019 w wersji 16,6.

Ta zmiana może spowodować błędy kompilatora. Na przykład wcześniej można było pomnożyć `pow(complex<float>, int)` przez **`float`** . Ponieważ `complex<T> operator*` oczekuje argumentów tego samego typu, Poniższy przykład teraz emituje błąd kompilatora C2676: `binary '*': 'std::complex<double>' does not define this operator or a conversion to a type acceptable to the predefined operator` :

```cpp
// pow_error.cpp
// compile by using: cl /EHsc /nologo /W4 pow_error.cpp
#include <complex>

int main() {
    std::complex<float> cf(2.0f, 0.0f);
    (void) (std::pow(cf, -1) * 3.0f);
}
```

Istnieje wiele możliwych poprawek:

- Zmień typ **`float`** multiplicand na **`double`** . Ten argument może być konwertowany bezpośrednio do `complex<double>` typu, który jest zgodny z typem zwracanym przez `pow` .

- Zawężaj wynik `pow` do `complex<float>` , mówiąc `complex<float>{pow(ARG, ARG)}` . Następnie można kontynuować mnożenie według **`float`** wartości.

- Przekazanie **`float`** zamiast **`int`** do `pow` . Ta operacja może potrwać wolniej.

- W niektórych przypadkach można `pow` całkowicie uniknąć. Na przykład `pow(cf, -1)` mogą zostać zastąpione przez dzielenie.

### <a name="switch-related-warnings-for-c"></a>Ostrzeżenia dotyczące przełącznika dla języka C

Począwszy od programu Visual Studio 2019 w wersji 16,6, kompilator implementuje pewne istniejące ostrzeżenia języka C++ dla kodu skompilowanego jako C. Następujące ostrzeżenia są teraz włączone na różnych poziomach: C4060, C4061, C4062, C4063, C4064, C4065, C4808 i C4809. Ostrzeżenia C4065 i C4060 są domyślnie wyłączone w języku C.

Wyzwalacz ostrzeżeń w przypadku brakujących **`case`** instrukcji, niezdefiniowanych **`enum`** i nieprawidłowych **`bool`** przełączników (czyli tych, które zawierają zbyt wiele przypadków). Na przykład:

```c
#include <stdbool.h>

int main() {
    bool b = true;
    switch (b) {
        case true: break;
        case false: break;
        default: break; // C4809: switch statement has redundant 'default' label;
                        // all possible 'case' labels are given
    }
}
```

Aby naprawić ten kod, Usuń nadmiarowy **`default`** przypadek:

```c
#include <stdbool.h>

int main() {
    bool b = true;
    switch (b) {
        case true: break;
        case false: break;
    }
}
```

### <a name="unnamed-classes-in-typedef-declarations"></a>Nienazwane klasy w `typedef` deklaracjach

Począwszy od programu Visual Studio 2019 w wersji 16,6, zachowanie **`typedef`** deklaracji zostało ograniczone do zgodności z [P1766R1](https://wg21.link/P1766R1). W przypadku tej aktualizacji nienazwane klasy w **`typedef`** deklaracji nie mogą mieć żadnych składowych innych niż:

- niestatyczne składowe danych,
- klasy Członkowskie,
- wyliczenia elementów członkowskich,
- i domyślne inicjatory członków.

Te same ograniczenia są stosowane cyklicznie dla każdej klasy zagnieżdżonej. Ograniczenie jest przeznaczone do zapewnienia prostoty struktur, które mają **`typedef`** nazwy dla celów powiązania. Muszą one być proste, aby nie trzeba było wykonywać obliczeń powiązania, zanim kompilator uzyska **`typedef`** nazwę dla powiązania.

Ta zmiana ma wpływ na wszystkie tryby standardu kompilatora. W domyślnych ( **`/std:c++14`** ) i  **`/std:c++17`** trybach kompilator emituje ostrzeżenie C5208 o niezgodnym kodzie. Jeśli **`/permissive-`** jest określony, kompilator emituje ostrzeżenie C5208 jako błąd w obszarze **`/std:c++14`** i emituje błąd C7626 w obszarze **`/std:c++17`** . Kompilator emituje C7626 błędów dla kodu niezgodnego, gdy **`/std:c++latest`** jest określony.

Poniższy przykład pokazuje konstrukcje, które nie są już dozwolone w strukturach nienazwanych. W zależności od określonego trybu standardów C5208 lub C7626 błędy lub ostrzeżenia są emitowane:

```cpp
struct B { };
typedef struct : B { // inheriting from 'B'; ill-formed
    void f(); // ill-formed
    static int i; // ill-formed
    struct U {
        void f(); // nested class has non-data member; ill-formed
    };
    int j = 10; // default member initializer; ill-formed
} S;
```

Powyższy kod można naprawić, podając nazwę klasy bez nazwy:

```cpp
struct B { };
typedef struct S_ : B {
    void f();
    static int i;
    struct U {
        void f();
    };
    int j = 10;
} S;
```

### <a name="default-argument-import-in-ccli"></a>Domyślny import argumentu w języku C++/CLI

Rosnąca liczba interfejsów API ma argumenty domyślne w programie .NET Core. Dlatego teraz obsługujemy domyślne Importowanie argumentów w języku C++/CLI. Ta zmiana może spowodować uszkodzenie istniejącego kodu, w którym zadeklarowane jest wiele przeciążeń, jak w poniższym przykładzie:

```cpp
public class R {
    public void Func(string s) {}   // overload 1
    public void Func(string s, string s2 = "") {} // overload 2;
}
```

Gdy ta klasa jest importowana do/CLI języka C++, wywołanie jednego z przeciążeń powoduje błąd:

```cpp
    (gcnew R)->Func("abc"); // error C2668: 'R::Func' ambiguous call to overloaded function
```

Kompilator emituje błąd C2668, ponieważ oba przeciążenia są zgodne z tą listą argumentów. W drugim przeciążeniu drugi argument jest wypełniany przez argument domyślny. Aby obejść ten problem, można usunąć nadmiarowe Przeciążenie (1). Można też użyć listy pełny argument i jawnie podać argumenty domyślne.

## <a name="conformance-improvements-in-visual-studio-2019-version-167"></a><a name="improvements_167"></a> Ulepszenia zgodności w programie Visual Studio 2019 w wersji 16,7

### <a name="definition-of-is-trivially-copyable"></a>Definicja *jest w prosty sposób kopiowany*

W języku c++ 20 zmieniono definicję elementu, który *jest w prosty sposób kopiowany* . Gdy Klasa ma niestatyczną składową danych z **`volatile`** typem kwalifikowanym, nie oznacza już, że żaden Konstruktor kopiowania lub przenoszenia wygenerowanego przez kompilator lub operator przypisania kopiowania lub przenoszenia nie jest prosty. Standardowy Komitet języka C++ stosował tę zmianę wstecz jako raport wad. W MSVC zachowanie kompilatora nie zmienia się w różnych trybach języka, takich jak **`/std:c++14`** lub **`/std:c++latest`** .

Oto przykład nowego zachowania:

```cpp
#include <type_traits>

struct S
{
    volatile int m;
};

static_assert(std::is_trivially_copyable_v<S>, "Meow!");
```

Ten kod nie kompiluje się w wersjach programu MSVC przed Visual Studio 2019 w wersji 16,7. Jest to domyślne Ostrzeżenie kompilatora, za pomocą którego można wykryć tę zmianę. Jeśli kompilujesz kod powyżej przy użyciu, zobaczysz **`cl /W4 /w45220`** następujące ostrzeżenie:

Ostrzeżenie C5220: `'S::m': a non-static data member with a volatile qualified type no longer implies that compiler generated copy/move constructors and copy/move assignment operators are non trivial`

### <a name="pointer-to-member-and-string-literal-conversions-to-bool-are-narrowing"></a>Konwersje wskaźnika do składowej i literału ciągu na `bool` zawężają

Komitet standardu C++ przyjął ostatnio [P1957R2](https://wg21.link/p1957r2)raportu wad, który jest uważany za `T*`  ->  **`bool`** konwersję zawężaną. MSVC naprawił błąd w swojej implementacji, który był wcześniej zdiagnozowany `T*`  ->  **`bool`** jako zawężający, ale nie zdiagnozowano konwersji literału ciągu na **`bool`** lub wskaźnika do elementu członkowskiego **`bool`** .

Następujący program został niepoprawnie sformułowany w programie Visual Studio 2019 w wersji 16,7:

```cpp
struct X { bool b; };
void f(X);

int main() {
    f(X { "whoops?" }); // error: conversion from 'const char [8]' to 'bool' requires a narrowing conversion

    int (X::* p) = nullptr;
    f(X { p }); // error: conversion from 'int X::*' to 'bool' requires a narrowing conversion
}
```

Aby poprawić ten kod, należy dodać jawne porównania do **`nullptr`** lub uniknąć kontekstów, w których konwersje wąskie są źle sformułowane:

```cpp
struct X { bool b; };
void f(X);

int main() {
    f(X { "whoops?" != nullptr }); // Absurd, but OK

    int (X::* p) = nullptr;
    f(X { p != nullptr }); // OK
}
```

### <a name="nullptr_t-is-only-convertible-to-bool-as-a-direct-initialization"></a>`nullptr_t` jest konwertowany tylko `bool` jako Inicjalizacja bezpośrednia

W języku C++ 11, **`nullptr`** można przekonwertować tylko na **`bool`** jako *konwersję bezpośrednią* ; na przykład po zainicjowaniu **`bool`** za pomocą listy inicjalizatora w nawiasach klamrowych. To ograniczenie nigdy nie jest wymuszane przez MSVC. MSVC teraz implementuje regułę w obszarze [`/permissive-`](../build/reference/permissive-standards-conformance.md) . Konwersje niejawne są teraz diagnozowane jako źle sformułowane. Konwersja kontekstowa **`bool`** jest nadal dozwolona, ponieważ bezpośrednie inicjowanie `bool b(nullptr)` jest prawidłowe.

W większości przypadków błąd można naprawić, zastępując **`nullptr`** przy użyciu **`false`** , jak pokazano w poniższym przykładzie:

```cpp
struct S { bool b; };
void g(bool);
bool h() { return nullptr; } // error, should be 'return false;'

int main() {
    bool b1 = nullptr; // error: cannot convert from 'nullptr' to 'bool'
    S s { nullptr }; // error: cannot convert from 'nullptr' to 'bool'
    g(nullptr); // error: cannot convert argument 1 from 'nullptr' to 'bool'

    bool b2 { nullptr }; // OK: Direct-initialization
    if (!nullptr) {} // OK: Contextual conversion to bool
}
```

### <a name="conforming-initialization-behavior-for-array-initializations-with-missing-initializers"></a>Zgodność z zachowaniem inicjalizacji dla inicjalizacji tablicy z brakującymi inicjatorami

Wcześniej MSVC miało niezgodne zachowanie w przypadku inicjalizacji tablicy z brakującymi inicjatorami. MSVC zawsze nazywany konstruktorem domyślnym dla każdego elementu tablicy, który nie ma inicjatora. Standardowe zachowanie polega na zainicjowaniu każdego elementu za pomocą pustej listy inicjatora ( **`{}`** ). Kontekst inicjalizacji pustej listy inicjalizatora w nawiasach klamrowych jest inicjalizacją kopiowania, która nie zezwala na wywołania jawnych konstruktorów. Mogą istnieć także różnice w czasie wykonywania, ponieważ użycie `{}` do inicjowania może wywołać konstruktora, który przyjmuje `std::initializer_list` zamiast domyślnego konstruktora. Zachowanie zgodności jest włączone w programie [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

Oto przykład zmienionego zachowania:

```cpp
struct B {
    explicit B() {}
};

void f() {
    B b1[1]{}; // Error in /permissive-, because aggregate init calls explicit ctor
    B b2[1]; // OK: calls default ctor for each array element
}
```

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019"></a><a name="update_160"></a> Poprawki błędów i zmiany zachowań w programie Visual Studio 2019

### <a name="reinterpret_cast-in-a-constexpr-function"></a>`reinterpret_cast` w `constexpr` funkcji

Element **`reinterpret_cast`** jest niedozwolony w **`constexpr`** funkcji. Kompilator języka Microsoft C++ zostałby wcześniej odrzucony **`reinterpret_cast`** tylko wtedy, gdy został użyty w **`constexpr`** kontekście. W programie Visual Studio 2019 we wszystkich trybach standardów języka kompilator prawidłowo diagnozuje **`reinterpret_cast`** w definicji **`constexpr`** funkcji. Poniższy kod generuje teraz C3615: `constexpr function 'f' cannot result in a constant expression` .

```cpp
long long i = 0;
constexpr void f() {
    int* a = reinterpret_cast<int*>(i);
}
```

Aby uniknąć tego błędu, Usuń **`constexpr`** modyfikator z deklaracji funkcji.

### <a name="correct-diagnostics-for-basic_string-range-constructor"></a>Poprawna Diagnostyka dla konstruktora zakresu basic_string

W programie Visual Studio 2019 `basic_string` Konstruktor zakresu nie pomija już diagnostyki kompilatora z **`static_cast`** . Poniższy kod kompiluje bez ostrzeżeń w programie Visual Studio 2017, pomimo możliwej utraty danych z programu **`wchar_t`** do **`char`** momentu jego inicjalizacji `out` :

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Program Visual Studio 2019 poprawnie zgłasza C4244 ostrzeżeń: `'argument': conversion from 'wchar_t' to 'const _Elem', possible loss of data` . Aby uniknąć ostrzeżenia, można zainicjować std:: String, jak pokazano w poniższym przykładzie:

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>Nieprawidłowe wywołania do `+=` i `-=` pod `/clr` lub `/ZW` są teraz prawidłowo wykryte

W programie Visual Studio 2017 wprowadzono usterkę, która spowodowała, że kompilator ignoruje błędy i nie generuje kodu dla nieprawidłowych wywołań do **`+=`** i **`-=`** pod **`/clr`** lub **`/ZW`** . Poniższy kod kompiluje się bez błędów w programie Visual Studio 2017, ale w programie Visual Studio 2019 poprawnie zgłasza błąd C2845: `'System::String ^': pointer arithmetic not allowed on this type` :

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

Aby uniknąć błędu w tym przykładzie, użyj **`+=`** operatora z `ToString()` metodą: `s += E::e.ToString();` .

### <a name="initializers-for-inline-static-data-members"></a>Inicjatory dla wbudowanych statycznych elementów członkowskich danych

Nieprawidłowe dostępy do elementów członkowskich wewnątrz **`inline`** i **`static constexpr`** inicjatory są teraz prawidłowo wykrywane. Poniższy przykład kompiluje się bez błędu w programie Visual Studio 2017, ale w programie Visual Studio 2019 w **`/std:c++17`** trybie Wystąpił błąd C2248: `cannot access private member declared in class 'X'` .

```cpp
struct X
{
    private:
        static inline const int c = 1000;
};

struct Y : X
{
    static inline int d = c; // C2248 in Visual Studio 2019
};
```

Aby uniknąć tego błędu, zadeklaruj element członkowski `X::c` jako chroniony:

```cpp
struct X
{
    protected:
        static inline const int c = 1000;
};
```

### <a name="c4800-reinstated"></a>C4800 przywrócono

MSVC używany do wypróbowania wydajności C4800 na temat niejawnej konwersji na **`bool`** . Był zbyt dużo szumu i nie można go pominąć, co prowadzi do usunięcia go w programie Visual Studio 2017. Jednak przed cyklem życia programu Visual Studio 2017 mamy wiele opinii na temat przydatnych przypadków, w których rozwiązanie było rozwiązywane. Wracamy do programu Visual Studio 2019 a dokładnie dopasowane C4800 oraz wyjaśniając C4165. Oba te ostrzeżenia można łatwo pominąć: przy użyciu jawnego rzutowania lub przez porównanie z wartością 0 odpowiedniego typu. C4800 jest ostrzeżeniem na poziomie niestandardowym 4, a C4165 jest ostrzeżeniem o poziomie niestandardowym 3. Obie są wykrywalne przy użyciu **`/Wall`** opcji kompilatora.

Poniższy przykład podnosi C4800 i C4165 w **`/Wall`** :

```cpp
bool test(IUnknown* p)
{
    bool valid = p; // warning C4800: Implicit conversion from 'IUnknown*' to bool. Possible information loss
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return hr; // warning C4165: 'HRESULT' is being converted to 'bool'; are you sure this is what you want?
}
```

Aby uniknąć ostrzeżeń w poprzednim przykładzie, można napisać kod podobny do tego:

```cpp
bool test(IUnknown* p)
{
    bool valid = p != nullptr; // OK
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return SUCCEEDED(hr);  // OK
}
```

### <a name="local-class-member-function-doesnt-have-a-body"></a>Funkcja składowa klasy lokalnej nie ma treści

W programie Visual Studio 2017 C4822 ostrzegawczy: `Local class member function doesn't have a body` jest uruchamiany tylko wtedy, gdy opcja kompilatora **`/w14822`** jest jawnie ustawiona. Nie jest on wyświetlany w **`/Wall`** . W programie Visual Studio 2019 C4822 jest ostrzeżeniem niezależnym od domyślnego, co sprawia, że jest wykrywalny **`/Wall`** bez konieczności **`/w14822`** jawnego ustawiania.

```cpp
void example()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-if-constexpr-statements"></a>Treści szablonu funkcji zawierające `if constexpr` instrukcje

Jednostki funkcji szablonu zawierające **`if constexpr`** instrukcje mają [`/permissive-`](../build/reference/permissive-standards-conformance.md) włączone sprawdzanie związane z analizą. Na przykład w programie Visual Studio 2017 Poniższy kod generuje C7510: `'Type': use of dependent type name must be prefixed with 'typename'` tylko wtedy, gdy **`/permissive-`** opcja nie jest ustawiona. W programie Visual Studio 2019 ten sam kod zgłasza błędy nawet wtedy, gdy **`/permissive-`** opcja jest ustawiona:

```cpp
template <typename T>

int f()
{
    T::Type a; // error C7510

    if constexpr (T::val)
    {
        return 1;
    }
    else
    {
        return 2;
    }
}

struct X
{
    using Type = X;
    constexpr static int val = 1;
};

int main()
{
    return f<X>();
}
```

Aby uniknąć tego błędu, Dodaj **`typename`** słowo kluczowe do deklaracji `a` : `typename T::Type a;` .

### <a name="inline-assembly-code-isnt-supported-in-a-lambda-expression"></a>Kod asemblera wbudowanego nie jest obsługiwany w wyrażeniu lambda

Zespół Microsoft C++ był niedawno świadomy problemu zabezpieczeń, w którym użycie wbudowanego asemblera w ramach wyrażenia lambda może prowadzić do uszkodzenia `ebp` (rejestr adresów zwrotnych) w czasie wykonywania. Złośliwy atakujący może wykorzystać ten scenariusz. Wbudowany asembler jest obsługiwany tylko na architekturze x86, a interakcja między wbudowanym asemblerem a resztą kompilatora jest niska. Uwzględniając te fakty i istotę problemu, Najbezpieczniejsze rozwiązanie tego problemu było niedozwolone w wyrażeniu lambda.

Jedynym zastosowaniem asemblera wbudowanego w wyrażeniu lambda, którego znaleziono "w symbolu wieloznacznego, było przechwycenie adresu zwrotnego. W tym scenariuszu można przechwycić adres zwrotny na wszystkich platformach po prostu przy użyciu wewnętrznego kompilatora `_ReturnAddress()` .

Poniższy kod generuje C7552: `inline assembler is not supported in a lambda` zarówno w programie Visual studio 2017 15,9, jak i w programie Visual studio 2019:

```cpp
#include <cstdio>

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;

    auto lambda = [&]
    {
        __asm {

            mov eax, x
            mov y, eax
        }
    };

    lambda();
    return y;
}
```

Aby uniknąć tego błędu, Przenieś kod zestawu do funkcji nazwanej, jak pokazano w następującym przykładzie:

```cpp
#include <cstdio>

void g(int& x, int& y)
{
    __asm {
        mov eax, x
        mov y, eax
    }
}

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;
    auto lambda = [&]
    {
        g(x, y);
    };
    lambda();
    return y;
}

int main()
{
    std::printf("%d\n", f());
}
```

### <a name="iterator-debugging-and-stdmove_iterator"></a>Debugowanie iteratora i `std::move_iterator`

Funkcja debugowania iteratora została poprawna do prawidłowego odwinięcia `std::move_iterator` . Na przykład program `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` może teraz włączać `memcpy` szybką ścieżkę.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>Poprawki dotyczące \<xkeycheck.h> wymuszania słowa kluczowego

Wymuszanie biblioteki standardowej w programie \<xkeycheck.h> dla makr zastępujące słowo kluczowe zostało naprawione. Biblioteka teraz emituje faktycznie wykryte słowo kluczowe problemu, a nie komunikat ogólny. Obsługuje ona również słowa kluczowe języka C++ 20 i pozwala uniknąć używania funkcji IntelliSense do wymawiających losowo słów kluczowych.

### <a name="allocator-types-no-longer-deprecated"></a>Typy alokatorów nie są już przestarzałe

`std::allocator<void>`, `std::allocator::size_type` i `std::allocator::difference_type` nie są już przestarzałe.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Poprawne ostrzeżenie dotyczące zawężania konwersji ciągów

Usunięto element fałszywe **`static_cast`** z `std::string` , który nie został wywołany przez standard, i przypadkowo pominięto C4244 Zawężanie ostrzeżeń. Próby wywołania `std::string::string(const wchar_t*, const wchar_t*)` teraz prawidłowo emitują C4244 `narrowing a wchar_t into a char` .

### <a name="various-fixes-for-filesystem-correctness"></a>Różne poprawki dotyczące \<filesystem> poprawności

- Rozwiązano `std::filesystem::last_write_time` błąd podczas próby zmiany czasu ostatniego zapisu katalogu.
- `std::filesystem::directory_entry`Konstruktor zapisuje teraz wynik niepowodzenia, zamiast zgłaszać wyjątek, gdy podano nieistniejącą ścieżkę docelową.
- `std::filesystem::create_directory`Wersja 2-parametru została zmieniona w taki sposób, aby wywołała wersję z 1-parametrową, ponieważ jest `CreateDirectoryExW` ona używana `copy_symlink` podczas `existing_p` link symboliczny.
- `std::filesystem::directory_iterator` nie kończy się już w przypadku znalezienia uszkodzonego link symbolicznyu.
- `std::filesystem::space` teraz akceptowane są ścieżki względne.
- `std::filesystem::path::lexically_relative` nie jest już pomylony przez końcowe ukośniki, zgłoszone jako [LWG 3096](https://cplusplus.github.io/LWG/issue3096).
- Działały wokół `CreateSymbolicLinkW` odrzucania ścieżek z ukośnikami w `std::filesystem::create_symlink` .
- Praca między funkcją trybu usuwania POSIX, `delete` która istniała w systemie Windows 10 LTSB 1609, ale nie mogła faktycznie usunąć plików.
- `std::boyer_moore_searcher``std::boyer_moore_horspool_searcher`konstruktory kopiujące i kopiujące operatory przypisania teraz rzeczywiście kopiują elementy.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Algorytmy równoległe w systemie Windows 8 i nowszych

Biblioteka algorytmów równoległych teraz prawidłowo używa rzeczywistej `WaitOnAddress` rodziny w systemie Windows 8 i nowszych wersjach, a nie zawsze z systemami Windows 7 i wcześniejszymi wersjami.

### <a name="stdsystem_categorymessage-whitespace"></a>`std::system_category::message()` odstępu

`std::system_category::message()` teraz przycina końcowe odstępy od zwróconej wiadomości.

### <a name="stdlinear_congruential_engine-divide-by-zero"></a>`std::linear_congruential_engine` dzielenie przez zero

Niektóre warunki, które mogłyby spowodować, że `std::linear_congruential_engine` wyzwalacz dzielenia przez 0 zostały naprawione.

### <a name="fixes-for-iterator-unwrapping"></a>Poprawki dotyczące rozpakowywania iteratora

Niektóre maszyny do odpakowania, zostały najpierw ujawnione w celu integracji użytkownika programisty w programie Visual Studio 2017 15,8. Został on opisany w artykule Blog zespołu języka C++ [funkcje i poprawki w programie VS 2017 15,8](https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/). Te maszyny nie są już odlewane Iteratory pochodzące z iteratorów biblioteki standardowej. Na przykład użytkownik, który pochodzi z `std::vector<int>::iterator` i próbuje dostosować zachowanie, otrzymuje teraz dostosowane zachowanie podczas wywoływania standardowych algorytmów biblioteki zamiast zachowania wskaźnika.

Funkcja kontenera nieuporządkowanego `reserve` teraz rzeczywiście rezerwuje dla N elementów, zgodnie z opisem w [LWG 2156](https://cplusplus.github.io/LWG/issue2156).

### <a name="time-handling"></a>Obsługa czasu

- Wcześniej niektóre wartości czasu, które zostały przesłane do biblioteki współbieżności, zostałyby przepełnione, na przykład `condition_variable::wait_for(seconds::max())` . Naprawiono napływy zmieniono zachowanie na pozornie losowych cyklach 29-dniowych (w przypadku uint32_t milisekund zaakceptowanych przez bazowe interfejsy API Win32).

- \<ctime>Nagłówek teraz prawidłowo deklaruje `timespec` i `timespec_get` w przestrzeni nazw `std` , a także deklaruje je w globalnej przestrzeni nazw.

### <a name="various-fixes-for-containers"></a>Różne poprawki dla kontenerów

- Wiele wewnętrznych funkcji kontenera biblioteki standardowej została udostępniona jako prywatna dla udoskonalonego środowiska IntelliSense. Dodatkowe poprawki do oznaczania elementów członkowskich jako prywatne są oczekiwane w nowszych wersjach MSVC.

- Problemy z korekcją bezpieczeństwa wyjątków, w przypadku których kontenery oparte na węzłach, takie jak `list` , `map` i `unordered_map` zostałyby uszkodzone, zostały naprawione. W trakcie `propagate_on_container_copy_assignment` `propagate_on_container_move_assignment` operacji lub ponownego przypisywania można zwolnić węzeł wskaźnikowy kontenera ze starym alokatorem, wykonać przypisanie POCCA/POCMA przed starym alokatorem, a następnie spróbować uzyskać węzeł wskaźnikowy z nowego alokatora. Jeśli ta alokacja nie powiodła się, kontener został uszkodzony. Nie można nawet zniszczyć, ponieważ właściciel węzła wskaźnikowego jest niezmienną strukturą danych. Ten kod został naprawiony w celu utworzenia nowego węzła wskaźnikowego przy użyciu programu przydzielania kontenera źródłowego przed zniszczeniem istniejącego węzła wskaźnikowego.

- Kontenery zostały naprawione tak, aby zawsze były kopiowane/przenoszone/zamieniane, w zależności od tego, `propagate_on_container_copy_assignment` `propagate_on_container_move_assignment` , i `propagate_on_container_swap` , nawet w przypadku przyłożonych `is_always_equal` .

- Dodano przeciążenia kontenerów scalania i Wyodrębnij funkcje członkowskie, które akceptują kontenery rvalue. Aby uzyskać więcej informacji, zobacz [P0083 "łączenie map i zestawów"](https://wg21.link/p0083r3)

### <a name="stdbasic_istreamread-processing-of-rn-n"></a>`std::basic_istream::read` przetwarzanie elementu `\r\n`` =>` \n "

`std::basic_istream::read`Naprawiono, aby nie zapisywać do części podanego buforu tymczasowo w ramach `\r\n`  =>  `\n` przetwarzania. Ta zmiana stanowi część zalet wydajności, która została uzyskana w programie Visual Studio 2017 15,8 dla odczytów o rozmiarze większym niż 4 KB. Jednak w dalszym ciągu istnieją ulepszenia wydajności przed uniknięciem trzech wywołań wirtualnych na znak.

### <a name="stdbitset-constructor"></a>`std::bitset` konstruktora

`std::bitset`Konstruktor nie odczytuje już tych elementów i zero w kolejności odwrotnej dla dużych bitsets.

### <a name="stdpairoperator-regression"></a>`std::pair::operator=` ubytk

Naprawiono operator przypisania regresji w `std::pair` trakcie implementowania [LWG 2729 "Brak SFINAE w std::p powietrze:: operator =";](https://cplusplus.github.io/LWG/issue2729). Teraz prawidłowo akceptowane są konwersję typów na `std::pair` ponownie.

### <a name="non-deduced-contexts-for-add_const_t"></a>Konteksty niewnioskowane dla `add_const_t`

Naprawiono usterkę typu pomocniczego, gdzie `add_const_t` i powiązane funkcje powinny być kontekstem nieokreślonym. Innymi słowy, `add_const_t` należy do aliasu `typename add_const<T>::type` , nie `const T` .

## <a name="bug-fixes-and-behavior-changes-in-162"></a><a name="update_162"></a> Poprawki błędów i zmiany zachowań w 16,2

### <a name="const-comparators-for-associative-containers"></a>Const komparatorów dla kontenerów asocjacyjnych

Kod dla wyszukiwania i wstawiania w [zestawie](../standard-library/set-class.md), [mapie](../standard-library/map-class.md), wielu [zestawów](../standard-library/multiset-class.md)i [multimap](../standard-library/multimap-class.md) został scalony pod kątem zmniejszonego rozmiaru kodu. Operacje wstawiania teraz wywołują mniej niż porównanie porównania **`const`** Funktor w taki sam sposób, w jaki operacje wyszukiwania zostały wykonane wcześniej. Poniższy kod kompiluje się w programie Visual Studio 2019 w wersji 16,1 i starszej, ale wywołuje C3848 w programie Visual Studio 2019 w wersji 16,2:

```cpp
#include <iostream>
#include <map>

using namespace std;

struct K
{
   int a;
   string b = "label";
};

struct Comparer  {
   bool operator() (K a, K b) {
      return a.a < b.a;
   }
};

map<K, double, Comparer> m;

K const s1{1};
K const s2{2};
K const s3{3};

int main() {

   m.emplace(s1, 1.08);
   m.emplace(s2, 3.14);
   m.emplace(s3, 5.21);

}
```

Aby uniknąć tego błędu, ustaw operator porównania **`const`** :

```cpp
struct Comparer  {
   bool operator() (K a, K b) const {
      return a.a < b.a;
   }
};

```

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019-version-167"></a><a name="updates_167"></a> Poprawki błędów i zmiany zachowań w programie Visual Studio 2019 w wersji 16,7

### <a name="initialization-of-class-members-with-overloaded-names-is-correctly-sequenced"></a>Inicjalizacja elementów członkowskich klasy z przeciążonymi nazwami jest prawidłowo sekwencjonowana

Zidentyfikowano usterkę w wewnętrznej reprezentacji członków danych klasy, gdy nazwa typu jest również przeciążona jako nazwa elementu członkowskiego danych. Ta usterka spowodowała niespójności w ramach inicjalizacji agregującej i kolejności inicjowania składowej. Wygenerowany kod inicjujący jest teraz poprawny. Jednak ta zmiana może prowadzić do błędów lub ostrzeżeń w źródle, które w sposób nieumyślnie opierają się na nieprawidłowo uporządkowanych elementach członkowskich, jak w poniższym przykładzie:

```cpp
// Compiling with /w15038 now gives:
// warning C5038: data member 'Outer::Inner' will be initialized after data member 'Outer::v'
struct Outer {
    Outer(int i, int j) : Inner{ i }, v{ j } {}

    struct Inner { int x; };
    int v;
    Inner Inner; // 'Inner' is both a type name and data member name in the same scope
};
```

W poprzednich wersjach Konstruktor niepoprawnie zainicjował element członkowski danych `Inner` przed elementem członkowskim danych `v` . (Standard C++ wymaga, aby kolejność inicjalizacji była taka sama jak kolejność deklaracji elementów członkowskich). Teraz, gdy wygenerowany kod jest zgodny ze standardem, element członkowski-init-list jest nieuporządkowany. Kompilator generuje ostrzeżenie dla tego przykładu. Aby rozwiązać ten problem, Zmień kolejność listy inicjatorów elementów członkowskich, aby odzwierciedlała kolejność deklaracji.

### <a name="overload-resolution-involving-integral-overloads-and-long-arguments"></a>Rozpoznawanie przeciążenia obejmujące całkowite przeciążenia i `long` argumenty

Standard C++ wymaga, aby klasyfikacja była konwersja **`long`** **`int`** jako konwersja standardowa. Poprzednie kompilatory MSVC niepoprawnie klasyfikują je jako promocję integralną, która określa rangę większą dla rozdzielczości przeciążenia. Ta klasyfikacja może spowodować pomyślne rozwiązanie rozpoznania przeciążenia, gdy powinien być uważany za niejednoznaczny.

Kompilator teraz traktuje rangę poprawnie w [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybie. Nieprawidłowy kod został prawidłowo zdiagnozowany, jak w poniższym przykładzie:

```cpp
void f(long long);
void f(int);

int main() {
    long x {};
    f(x); // error: 'f': ambiguous call to overloaded function
    f(static_cast<int>(x)); // OK
}
```

Ten problem można rozwiązać na kilka sposobów:

- W miejscu wywołania Zmień typ przenoszonego argumentu na **`int`** . Można zmienić typ zmiennej lub rzutować ją.

- Jeśli istnieje wiele witryn wywołań, można dodać kolejne Przeciążenie, które przyjmuje **`long`** argument. W tej funkcji rzutowanie i przekazywanie argumentu do **`int`** przeciążenia.

### <a name="use-of-undefined-variable-with-internal-linkage"></a>Użycie niezdefiniowanej zmiennej z połączeniem wewnętrznym

Wersje programu MSVC zanim program Visual Studio 2019 w wersji 16,7 zatwierdził użycie zmiennej zadeklarowanej **`extern`** , która ma wewnętrzny związek i nie została zdefiniowana. Takie zmienne nie mogą być zdefiniowane w żadnej innej jednostce translacji i nie mogą tworzyć prawidłowych programów. Kompilator teraz diagnozuje ten przypadek w czasie kompilacji. Błąd jest podobny do błędu dla niezdefiniowanych funkcji statycznych.

```cpp
namespace {
    extern int x; // Not a definition, but has internal linkage because of the anonymous namespace
}

int main()
{
    return x; // Use of 'x' that no other translation unit can possibly define.
}
```

Ten program został wcześniej niepoprawnie skompilowany i połączony, ale teraz emituje:

C7631 błędu: `'anonymous-namespace'::x': variable with internal linkage declared but not defined`

Takie zmienne muszą być zdefiniowane w tej samej jednostce tłumaczenia, w której są używane. Na przykład można podać jawny inicjator lub oddzielną definicję.

### <a name="type-completeness-and-derived-to-base-pointer-conversions"></a>Konwersje typu kompletności i wskaźnika pochodnego na podstawowe

W standardach języka C++ przed C++ 20 konwersja z klasy pochodnej na klasę bazową nie wymagała, aby Klasa pochodna była kompletnym typem klasy. W standardowym Komitecie języka C++ zatwierdzono zmianę raportu wad wstecz, która ma zastosowanie do wszystkich wersji języka C++. Ta zmiana dopasowuje proces konwersji do cech typu, takich jak `std::is_base_of` , które wymagają, aby Klasa pochodna była kompletnym typem klasy.

Oto przykład:

```cpp
template<typename A, typename B>
struct check_derived_from
{
    static A a;
    static constexpr B* p = &a;
};

struct W { };
struct X { };
struct Y { };

// With this change this code will fail as Z1 is not a complete class type
struct Z1 : X, check_derived_from<Z1, X>
{
};

// This code failed before and it will still fail after this change
struct Z2 : check_derived_from<Z2, Y>, Y
{
};

// With this change this code will fail as Z3 is not a complete class type
struct Z3 : W
{
    check_derived_from<Z3, W> cdf;
};
```

Ta zmiana zachowania dotyczy wszystkich trybów języka C++ MSVC, a nie tylko **`/std:c++latest`** .

### <a name="narrowing-conversions-are-more-consistently-diagnosed"></a>Konwersje wąskie są bardziej spójnie diagnozowane

MSVC emituje Ostrzeżenie dla konwersji zawężających w przypadku inicjatora listy z nawiasami klamrowymi. Wcześniej kompilator nie wykrywa wąskich konwersji z większych **`enum`** typów podstawowych do węższych typów całkowitych. (Kompilator nieprawidłowo uznawany za integralną promocję zamiast konwersji). Jeśli zamierzone jest przekształcenie zawężania, można uniknąć ostrzeżenia przy użyciu **`static_cast`** argumentu w argumencie inicjatora. Możesz też wybrać większy docelowy typ całkowity.

Oto przykład użycia jawnego **`static_cast`** w celu rozwiązania ostrzeżenia:

```cpp
enum E : long long { e1 };
struct S { int i; };

void f(E e) {
    S s = { e }; // warning: conversion from 'E' to 'int' requires a narrowing conversion
    S s1 = { static_cast<int>(e) }; // Suppress warning with explicit conversion
}
```

::: moniker-end

::: moniker range="msvc-150"

## <a name="conformance-improvements-in-visual-studio-2017-rtw-version-150"></a><a name="improvements_150"></a> Udoskonalenia zgodności w programie Visual Studio 2017 RTW (wersja 15,0)

Dzięki obsłudze uogólnionej **`constexpr`** i niestatycznej inicjalizacji składowych danych (NSDMI) dla agregacji, kompilator języka Microsoft C++ w programie Visual Studio 2017 jest teraz gotowy do obsługi funkcji dodanych w standardzie c++ 14. Jednak kompilator nadal nie ma kilku funkcji ze standardów C++ 11 i C++ 98. Zobacz [tabelę zgodności języka Microsoft C++](./visual-cpp-language-conformance.md) dla tabeli, która pokazuje bieżący stan kompilatora.

### <a name="c11-expression-sfinae-support-in-more-libraries"></a>C++ 11: obsługa wyrażenia SFINAE w większej liczbie bibliotek

Kompilator kontynuuje ulepszanie obsługi wyrażenia SFINAE. Jest to wymagane w przypadku odejmowania argumentu szablonu i podstawienia, gdzie **`decltype`** i **`constexpr`** wyrażenia mogą być wyświetlane jako parametry szablonu. Aby uzyskać więcej informacji, zobacz temat [Expression SFINAE ulepszeń w programie Visual Studio 2017 RC](https://devblogs.microsoft.com/cppblog/expression-sfinae-improvements-in-vs-2015-update-3/).

### <a name="c14-nsdmi-for-aggregates"></a>C++ 14: NSDMI dla agregacji

Agregacja jest tablicą lub klasą, która ma: Brak konstruktora dostarczonego przez użytkownika, bez niestatycznych składowych danych, które są prywatne lub chronione, brak klas bazowych i nie ma żadnych funkcji wirtualnych. Począwszy od języka C++ 14, agregacje mogą zawierać inicjatory elementów członkowskich. Aby uzyskać więcej informacji, zobacz [inicjatory i agregacje członków](https://wg21.link/n3605).

### <a name="c14-extended-constexpr"></a>C++ 14: rozszerzony `constexpr`

Wyrażenia zadeklarowane jako **`constexpr`** są teraz dozwolone do przechowywania niektórych rodzajów deklaracji, instrukcji if i Switch, instrukcji pętli i mutacji obiektów, których okres istnienia został rozpoczęty w wyniku **`constexpr`** obliczania wyrażenia. Nie istnieje już wymóg, że **`constexpr`** niestatyczna funkcja członkowska musi być niejawnie **`const`** . Aby uzyskać więcej informacji, zobacz [złagodzeniu wymagań dotyczących ograniczenia dotyczące `constexpr` funkcji](https://wg21.link/n3652).

### <a name="c17-terse-static_assert"></a>C++ 17: zwięzła `static_assert`

parametr komunikatu dla **`static_assert`** jest opcjonalny. Aby uzyskać więcej informacji, zobacz [rozszerzanie static_assert, v2](https://wg21.link/n3928).

### <a name="c17-fallthrough-attribute"></a>C++ 17: `[[fallthrough]]` atrybut

W **`/std:c++17`** trybie w tym `[[fallthrough]]` atrybut może być używany w kontekście instrukcji switch jako wskazówkę dla kompilatora, że zachowanie "spadek liczby" jest zamierzone. Ten atrybut uniemożliwia kompilatorowi wygenerowanie ostrzeżeń w takich przypadkach. Aby uzyskać więcej informacji, zobacz [Wording for `[[fallthrough]]` Attribute](https://wg21.link/p0188r0).

### <a name="generalized-range-based-for-loops"></a>Uogólniony zakres na podstawie pętli

Pętle oparte na zakresie dla pętli nie wymagają już `begin()` i `end()` zwracają obiekty tego samego typu. Ta zmiana umożliwia `end()` zwrócenie wskaźnikiem kontrolnym używanym przez zakresy z [zakresu od 3](https://github.com/ericniebler/range-v3) do i gotowe, ale niecałkowicie opublikowane zakresy Specyfikacja techniczna. Aby uzyskać więcej informacji, zobacz [uogólnianie Range-Based `for` pętli](https://wg21.link/p0184r0).

## <a name="conformance-improvements-in-153"></a><a name="improvements_153"></a> Ulepszenia zgodności w 15,3

### <a name="constexpr-lambdas"></a>`constexpr` wyrażeń lambda

Wyrażenia lambda mogą być teraz używane w wyrażeniach stałych. Aby uzyskać więcej informacji, zobacz [ `constexpr` wyrażenia lambda w języku C++](../cpp/lambda-expressions-constexpr.md).

### <a name="if-constexpr-in-function-templates"></a>`if constexpr` w szablonach funkcji

Szablon funkcji może zawierać **`if constexpr`** instrukcje umożliwiające rozgałęzianie w czasie kompilacji. Aby uzyskać więcej informacji, zobacz [ `if constexpr` instrukcje](../cpp/if-else-statement-cpp.md#if_constexpr).

### <a name="selection-statements-with-initializers"></a>Instrukcje wyboru z inicjatorami

**`if`** Instrukcja może zawierać inicjator wprowadzający zmienną w zakresie bloku w samej instrukcji. Aby uzyskać więcej informacji, zobacz [ `if` instrukcje z inicjatorem](../cpp/if-else-statement-cpp.md#if_with_init).

### <a name="maybe_unused-and-nodiscard-attributes"></a>`[[maybe_unused]]` i `[[nodiscard]]` atrybuty

Nowy atrybut `[[maybe_unused]]` powoduje wyciszenie ostrzeżeń, gdy jednostka nie jest używana. Ten `[[nodiscard]]` atrybut tworzy ostrzeżenie, jeśli wartość zwracana wywołania funkcji jest odrzucana. Aby uzyskać więcej informacji, zobacz [atrybuty w języku C++](../cpp/attributes.md).

### <a name="using-attribute-namespaces-without-repetition"></a>Używanie przestrzeni nazw atrybutów bez powtarzania

Nowa składnia umożliwiająca włączenie tylko jednego identyfikatora przestrzeni nazw na liście atrybutów. Aby uzyskać więcej informacji, zobacz [atrybuty w języku C++](../cpp/attributes.md).

### <a name="structured-bindings"></a>Powiązania strukturalne

Teraz można w jednej deklaracji przechowywać wartość przy użyciu pojedynczych nazw składników, gdy wartość jest tablicą, a `std::tuple` lub `std::pair` lub ma wszystkie publiczne niestatyczne elementy członkowskie danych. Aby uzyskać więcej informacji, zobacz [strukturalne powiązania](https://wg21.link/p0144r0) i [zwracają wiele wartości z funkcji](../cpp/functions-cpp.md#multi_val).

### <a name="construction-rules-for-enum-class-values"></a>Reguły konstrukcji dla `enum class` wartości

Teraz istnieje niejawna konwersja dla wyliczeń objętych zakresem, które nie są zawężane. Konwertuje typ podstawowy wyliczenia z zakresem na sam Wyliczenie. Konwersja jest dostępna, gdy jej definicja nie wprowadza modułu wyliczającego, a kiedy źródło używa składni inicjowania listy. Aby uzyskać więcej informacji, zobacz [reguły tworzenia dla wartości klasy enum](https://wg21.link/p0138r2) i [wyliczeń](../cpp/enumerations-cpp.md#no_enumerators).

### <a name="capturing-this-by-value"></a>Przechwytywanie `*this` przez wartość

**`*this`** Obiekt w wyrażeniu lambda może teraz być przechwytywany przez wartość. Ta zmiana umożliwia scenariusze, w których wyrażenie lambda jest wywoływane w operacjach równoległych i asynchronicznych, szczególnie w przypadku nowszych architektur maszyn. Aby uzyskać więcej informacji, zobacz [przechwytywanie lambda \* tego elementu przez wartość AS \[ =, \* this \] ](https://wg21.link/p0018r3).

### <a name="removing-operator-for-bool"></a>Usuwanie `operator++` dla `bool`

`operator++` nie jest już obsługiwane w **`bool`** typach. Aby uzyskać więcej informacji, zobacz [usuwanie przestarzałego operatora + + (bool)](https://wg21.link/p0002r1).

### <a name="removing-deprecated-register-keyword"></a>Usuwanie przestarzałego `register` słowa kluczowego

**`register`** Słowo kluczowe, wcześniej przestarzałe (i zignorowane przez kompilator), jest teraz usuwane z języka. Aby uzyskać więcej informacji, zobacz [Usuń przestarzałe użycie `register` słowa kluczowego](https://wg21.link/p0001r1).

## <a name="conformance-improvements-in-155"></a><a name="improvements_155"></a> Ulepszenia zgodności w 15,5

Funkcje oznaczone jako \[ 14] są dostępne bezwarunkowo nawet w **`/std:c++14`** trybie.

### <a name="new-compiler-switch-for-extern-constexpr"></a>Nowy przełącznik kompilatora dla `extern constexpr`

We wcześniejszych wersjach programu Visual Studio kompilator zawsze udzielił **`constexpr`** zmiennej wewnętrznej powiązania, nawet gdy zmienna została oznaczona **`extern`** . W programie Visual Studio 2017 w wersji 15,5, nowy przełącznik kompilatora, [`/Zc:externConstexpr`](../build/reference/zc-externconstexpr.md) umożliwia poprawne i zgodne ze standardami zachowanie zgodności. Aby uzyskać więcej informacji, zobacz [zewnętrzny związek constexpr](#extern_linkage).

### <a name="removing-dynamic-exception-specifications"></a>Usuwanie specyfikacji wyjątków dynamicznych

[P0003R5](https://wg21.link/p0003r5) Specyfikacje wyjątków dynamicznych są przestarzałe w języku C++ 11. Funkcja jest usuwana z C++ 17, ale (nadal) przestarzała `throw()` Specyfikacja jest przechowywana wyłącznie jako alias dla `noexcept(true)` . Aby uzyskać więcej informacji, zobacz sekcję [usuwanie specyfikacji wyjątków dynamicznych i noexcept](#noexcept_removal).

### `not_fn()`

[P0005R4](https://wg21.link/p0005r4) `not_fn` jest zamiennikiem `not1` i `not2` .

### <a name="rewording-enable_shared_from_this"></a>Resformułowanie `enable_shared_from_this`

[P0033R1](https://wg21.link/p0033r1) `enable_shared_from_this` dodano do języka C++ 11. Standard C++ 17 aktualizuje specyfikację, aby lepiej obsługiwać niektóre przypadki narożne. \[14,5

### <a name="splicing-maps-and-sets"></a>Łączenie map i zestawów

[P0083R3](https://wg21.link/p0083r3) Ta funkcja umożliwia wyodrębnienie węzłów z kontenerów asocjacyjnych (takich jak,,,, `map` `set` `unordered_map` `unordered_set` ), które można następnie zmodyfikować i wstawić z powrotem do tego samego kontenera lub innego kontenera, który używa tego samego typu węzła. (Typowym przypadkiem użycia jest wyodrębnienie węzła z `std::map` , zmiana klucza i wstawienie ponownie).

### <a name="deprecating-vestigial-library-parts"></a>Przestarzałe części biblioteki szczątkowe

[P0174R2](https://wg21.link/p0174r2) Niektóre funkcje standardowej biblioteki języka C++ zostały zastąpione przez nowsze funkcje w ciągu lat, a inne nie są użyteczne ani problematyczne. Te funkcje są oficjalnie przestarzałe w języku C++ 17.

### <a name="removing-allocator-support-in-stdfunction"></a>Usuwanie obsługi alokatora w programie `std::function`

[P0302R1](https://wg21.link/p0302r1) Wcześniej niż C++ 17, szablon klasy `std::function` miał kilka konstruktorów, które miały argument alokatora. Jednak użycie przystawek w tym kontekście było problematyczne, a semantyka była niejasne. Problem dla rodziny został usunięty.

### <a name="fixes-for-not_fn"></a>Poprawki dla `not_fn()`

[P0358R1](https://wg21.link/p0358r1) Nowe słownictwo dla programu `std::not_fn` zapewnia obsługę propagacji kategorii wartości w przypadku użycia w wywołaniu otoki.

### <a name="shared_ptrt-shared_ptrtn"></a>`shared_ptr<T[]>`, `shared_ptr<T[N]>`

[P0414R2](https://wg21.link/p0414r2) Scalanie `shared_ptr` zmian z bibliotek podstawowych do c++ 17. \[14,5

### <a name="fixing-shared_ptr-for-arrays"></a>Naprawianie `shared_ptr` dla tablic

[P0497R0](https://wg21.link/p0497r0) Poprawki do shared_ptr obsługi tablic. \[14,5

### <a name="clarifying-insert_return_type"></a>Wyjaśniające `insert_return_type`

[P0508R0](https://wg21.link/p0508r0) Kontenery asocjacyjne z unikatowymi kluczami i kontenery nieuporządkowane z unikatowymi kluczami mają funkcję członkowską `insert` zwracającą typ zagnieżdżony `insert_return_type` . Ten typ zwracany jest teraz zdefiniowany jako specjalizacja typu, który jest sparametryzowane dla iteratora i NodeType kontenera.

### <a name="inline-variables-for-the-standard-library"></a>Wbudowane zmienne biblioteki standardowej

[P0607R0](https://wg21.link/p0607r0)

### <a name="annex-d-features-deprecated"></a>Załączniki D funkcji przestarzałe

Załącznik D standardu C++ zawiera wszystkie funkcje, które zostały wycofane, w tym `shared_ptr::unique()` , `<codecvt>` i `namespace std::tr1` . Gdy **`/std:c++17`** przełącznik kompilatora jest ustawiony, prawie wszystkie standardowe funkcje biblioteki w załączniku D są oznaczone jako przestarzałe. Aby uzyskać więcej informacji, zobacz [standardowe funkcje biblioteki w załączniku D są oznaczone jako przestarzałe](#annex_d).

`std::tr2::sys`Przestrzeń nazw w programie `<experimental/filesystem>` teraz domyślnie emituje ostrzeżenie o zaniechaniu **`/std:c++14`** i jest teraz domyślnie usuwana **`/std:c++17`** .

Ulepszona zgodność `<iostream>` poprzez uniknięcie niestandardowym rozszerzeniem (jawne specjalizacje w klasie).

Biblioteka standardowa używa teraz szablonów zmiennych wewnętrznie.

Standardowa biblioteka została zaktualizowana w odpowiedzi na zmiany kompilatora C++ 17. Aktualizacje obejmują dodanie **`noexcept`** w systemie typów i usunięcie specyfikacji Dynamic-Exception-Specification.

## <a name="conformance-improvements-in-156"></a><a name="improvements_156"></a> Ulepszenia zgodności w 15,6

### <a name="c17-library-fundamentals-v1"></a>Biblioteka c++ 17 — podstawowe informacje o wersji 1

Biblioteka [P0220R1](https://wg21.link/p0220r1) zawiera podstawowe specyfikacje techniczne dla języka c++ 17 w standardzie. Obejmuje aktualizacje,,,,,, \<experimental/tuple> \<experimental/optional> \<experimental/functional> \<experimental/any> \<experimental/string_view> \<experimental/memory> \<experimental/memory_resource> i \<experimental/algorithm> .

### <a name="c17-improving-class-template-argument-deduction-for-the-standard-library"></a>C++ 17: ulepszanie odejmowania argumentów szablonu klasy dla standardowej biblioteki

[P0739R0](https://wg21.link/p0739r0) Przejdź `adopt_lock_t` na wierzch listy parametrów `scoped_lock` , aby włączyć spójne korzystanie z programu `scoped_lock` . Zezwól `std::variant` konstruktorowi na uczestnictwo w rozpoznawaniu przeciążenia w większej liczbie przypadków, aby włączyć przypisanie kopiowania.

## <a name="conformance-improvements-in-157"></a><a name="improvements_157"></a> Ulepszenia zgodności w 15,7

### <a name="c17-rewording-inheriting-constructors"></a>C++ 17: odsformułowanie konstruktorów dziedziczenia

[P0136R1](https://wg21.link/p0136r1) określa, że **`using`** Deklaracja, która nazywa konstruktora, teraz sprawia, że odpowiadające konstruktory klasy bazowej widoczne dla inicjalizacji klasy pochodnej, zamiast deklarowania dodatkowych konstruktorów klasy pochodnej. Jest to zmiana w języku C++ 14. W programie Visual Studio 2017 w wersji 15,7 lub nowszej, w **`/std:c++17`** trybie, kod, który jest prawidłowy w języku c++ 14 i używa konstruktorów dziedziczenia, może być nieprawidłowy lub mieć inną semantykę.

W poniższym przykładzie przedstawiono zachowanie języka C++ 14:

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n) = delete; // Error C2280
};

B b(42L); // Calls B<long>(long), which calls A(int)
          //  due to substitution failure in A<long>(long).
```

W poniższym przykładzie przedstawiono **`/std:c++17`** zachowanie w programie Visual Studio 15,7:

```cpp
struct A {
    template<typename T>
    A(T, typename T::type = 0);
    A(int);
};

struct B : A {
    using A::A;
    B(int n)
    {
        //do something
    }
};

B b(42L); // now calls B(int)
```

Aby uzyskać więcej informacji, zobacz [konstruktory](../cpp/constructors-cpp.md#inheriting_constructors).

### <a name="c17-extended-aggregate-initialization"></a>C++ 17: rozszerzona Inicjalizacja agregacji

[P0017R1](https://wg21.link/p0017r1)

Jeśli Konstruktor klasy bazowej jest niepubliczny, ale dostęp do klasy pochodnej, w obszarze **`/std:c++17`** tryb w programie Visual Studio 2017 w wersji 15,7 nie można już używać pustych nawiasów klamrowych w celu zainicjowania obiektu typu pochodnego.
W poniższym przykładzie przedstawiono zachowanie zgodne z językiem C++ 14:

```cpp
struct Derived;
struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {};
Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // OK in C++14: Calls Derived::Derived()
               // which can call Base ctor.
```

W języku C++ 17 `Derived` jest teraz uznawany za typ zagregowany. Oznacza to, że inicjalizacja `Base` za pośrednictwem prywatnego konstruktora domyślnego odbywa się bezpośrednio w ramach rozszerzonej reguły inicjowania agregacji. Wcześniej `Base` Konstruktor prywatny został wywołany za pośrednictwem `Derived` konstruktora i powiódł się z powodu deklaracji zaprzyjaźnionej.
W poniższym przykładzie przedstawiono zachowanie języka C++ 17 w programie Visual Studio w wersji 15,7 w **`/std:c++17`** trybie:

```cpp
struct Derived;
struct Base {
    friend struct Derived;
private:
    Base() {}
};
struct Derived : Base {
    Derived() {} // add user-defined constructor
                 // to call with {} initialization
};
Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // error C2248: 'Base::Base': cannot access
               // private member declared in class 'Base'
```

### <a name="c17-declaring-non-type-template-parameters-with-auto"></a>C++ 17: deklarowanie parametrów szablonu bez typu za pomocą

[P0127R2](https://wg21.link/p0127r2)

W **`/std:c++17`** trybie, kompilator może teraz ustalić typ argumentu szablonu bez typu, który jest zadeklarowany za pomocą **`auto`** :

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

Jednym wpływem tej nowej funkcji jest to, że prawidłowy kod języka C++ 14 może być nieprawidłowy lub może mieć inną semantykę. Na przykład niektóre przeciążenia, które były wcześniej nieprawidłowe, są teraz prawidłowe. Poniższy przykład przedstawia kod języka C++ 14, który kompiluje, ponieważ wywołanie `example(p)` jest powiązane z `example(void*);` . W programie Visual Studio 2017 w wersji 15,7 w **`/std:c++17`** trybie, `example` szablon funkcji jest najlepszym dopasowaniem.

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*) = delete;

void example(void *);

void sample(A<0> *p)
{
    example(p); // OK in C++14
}
```

W poniższym przykładzie przedstawiono kod C++ 17 w programie Visual Studio 15,7 w **`/std:c++17`** trybie:

```cpp
template <int N> struct A;
template <typename T, T N> int example(A<N>*);

void example(void *);

void sample(A<0> *p)
{
    example(p); // C2280: 'int example<int,0>(A<0>*)': attempting to reference a deleted function
}
```

### <a name="c17-elementary-string-conversions-partial"></a>C++ 17: podstawowe konwersje ciągów (częściowa)

[P0067R5](https://wg21.link/p0067r5) Funkcje niezależne od ustawień regionalnych dotyczące konwersji między liczbami całkowitymi i ciągami oraz między liczbami zmiennoprzecinkowymi i ciągami.

### <a name="c20-avoiding-unnecessary-decay-partial"></a>C++ 20: uniknięcie niepotrzebnego uszkodzenia (częściowa)

[P0777R1](https://wg21.link/p0777r1) Dodaje rozróżnienie między pojęciem "zanikania" i po prostu usuwa kwalifikatory const lub Reference.  Nowa cecha typu `remove_reference_t` zastępuje `decay_t` w niektórych kontekstach. Obsługa programu `remove_cvref_t` jest zaimplementowana w programie Visual Studio 2019.

### <a name="c17-parallel-algorithms"></a>C++ 17: algorytmy równoległe

[P0024R2](https://wg21.link/p0024r2) Równoległość TS jest wbudowana w standard przy użyciu drobnych modyfikacji.

### <a name="c17-hypotx-y-z"></a>C++ 17: `hypot(x, y, z)`

[P0030R1](https://wg21.link/p0030r1) Dodaje trzy nowe przeciążenia do `std::hypot` , dla typów **`float`** , **`double`** i **`long double`** , z których każdy ma trzy parametry wejściowe.

### <a name="c17-filesystem"></a>C++ 17: \<filesystem>

[P0218R1](https://wg21.link/p0218r1) Przyjmuje system plików TS w standardzie z kilkoma modyfikacjami wyrazów.

### <a name="c17-mathematical-special-functions"></a>C++ 17: specjalne funkcje matematyczne

[P0226R1](https://wg21.link/p0220r1) Przyjmuje poprzednie specyfikacje techniczne dla matematycznych funkcji specjalnych do nagłówka standardowego \<cmath> .

### <a name="c17-deduction-guides-for-the-standard-library"></a>C++ 17: przewodniki odejmowania dla standardowej biblioteki

[P0433R2](https://wg21.link/p0433r2) Aktualizacje biblioteki STL, aby skorzystać z wdrażania [P0091R3](https://wg21.link/p0091r3)w języku c++ 17, które dodaje obsługę odliczania argumentów szablonu klasy.

### <a name="c17-repairing-elementary-string-conversions"></a>C++ 17: Naprawa podstawowych konwersji ciągów

[P0682R1](https://wg21.link/p0682r1) Przenieś nowe funkcje konwersji ciągów podstawowych z P0067R5 do nowego nagłówka \<charconv> i wprowadź inne udoskonalenia, w tym zmianę obsługi błędów `std::errc` zamiast `std::error_code` .

### <a name="c17-constexpr-for-char_traits-partial"></a>C++ 17: `constexpr` for `char_traits` (częściowa)

[P0426R1](https://wg21.link/p0426r1) Zmiany w `std::traits_type` funkcjach składowych `length` , `compare` i `find` Aby można było `std::string_view` używać ich w wyrażeniach stałych. (W programie Visual Studio 2017 w wersji 15,6 obsługiwane tylko dla Clang/LLVM. W wersji 15,7 Preview 2 Pomoc techniczna została również niemal zakończona dla ClXX.)

## <a name="conformance-improvements-in-159"></a><a name="improvements_159"></a> Ulepszenia zgodności w 15,9

### <a name="left-to-right-evaluation-order-for-operators-----and-"></a>Kolejność oceny od lewej do prawej dla operatorów `->*` , `[]` , `>>` i `<<`

Począwszy od języka c++ 17, operandy operatorów,, `->*` `[]` `>>` i `<<` muszą być oceniane w kolejności od lewej do prawej. Istnieją dwa przypadki, w których kompilator nie może zagwarantowania tej kolejności:

- gdy jedno z wyrażeń operandów jest obiektem przesłanym przez wartość lub zawiera obiekt przekazaną przez wartość lub

- po skompilowaniu przy użyciu **`/clr`** , a jeden z operandów jest polem obiektu lub tablicy.

Kompilator emituje ostrzeżenie [C4866](../error-messages/compiler-warnings/c4866.md) , gdy nie może zagwarantować oceny od lewej do prawej. Kompilator generuje to ostrzeżenie tylko wtedy **`/std:c++17`** , gdy jest określona lub późniejsza, zgodnie z wymogami zamówienia od lewej do prawej tego operatora w języku c++ 17.

Aby rozwiązać ten problem, należy najpierw rozważyć, czy konieczne jest obliczanie operandów od lewej do prawej. Na przykład może być konieczne, gdy Ocena operandów może generować efekty uboczne zależne od kolejności. Kolejność, w której są oceniane operandy, nie ma zauważalnego efektu w wielu przypadkach. Jeśli kolejność obliczeń musi być od lewej do prawej, należy rozważyć, czy można przekazać operandy przez odwołanie const. Ta zmiana eliminuje ostrzeżenie w następującym przykładzie kodu:

```cpp
// C4866.cpp
// compile with: /w14866 /std:c++17

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x) : x(x) {}
    HasCopyConstructor(const HasCopyConstructor& h) : x(h.x) { }
};

int operator>>(HasCopyConstructor a, HasCopyConstructor b) { return a.x >> b.x; }

// This version of operator>> does not trigger the warning:
// int operator>>(const HasCopyConstructor& a, const HasCopyConstructor& b) { return a.x >> b.x; }

int main()
{
    HasCopyConstructor a{ 1 };
    HasCopyConstructor b{ 2 };

    a>>b;        // C4866 for call to operator>>
};
```

## <a name="bug-fixes-in-visual-studio-2017-rtw-version-150"></a><a name="update_150"></a> Poprawki błędów w programie Visual Studio 2017 RTW (wersja 15,0)

### <a name="copy-list-initialization"></a>Inicjalizacja kopiowania listy

Program Visual Studio 2017 poprawnie wywołuje błędy kompilatora związane z tworzeniem obiektów przy użyciu list inicjatorów. Te błędy nie zostały przechwycone w programie Visual Studio 2015 i mogą prowadzić do awarii lub niezdefiniowanego zachowania środowiska uruchomieniowego. Zgodnie z N4594 13.3.1.7 P1, w ramach inicjalizacji listy kopii, kompilator jest wymagany do rozważania jawnego konstruktora do rozpoznawania przeciążenia. Jednak musi zgłosić błąd, jeśli wybrane zostanie określone Przeciążenie.

Poniższe dwa przykłady kompilują w programie Visual Studio 2015, ale nie w programie Visual Studio 2017.

```cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```

Aby poprawić błąd, użyj bezpośredniej inicjalizacji:

```cpp
A a1{ 1 };
const A& a2{ 1 };
```

W programie Visual Studio 2015 kompilator błędnie traktowany jako proces inicjalizacji kopiowania listy w taki sam sposób jak regularne inicjowanie kopiowania: uważa się tylko na konwersję konstruktorów w celu rozpoznania przeciążenia. W poniższym przykładzie program Visual Studio 2015 wybiera `MyInt(23)` . Program Visual Studio 2017 poprawnie zgłasza błąd.

```cpp
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyStore {
    explicit MyStore(int initialCapacity);
};

struct MyInt {
    MyInt(int i);
};

struct Printer {
    void operator()(MyStore const& s);
    void operator()(MyInt const& i);
};

void f() {
    Printer p;
    p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

Ten przykład jest podobny do poprzedniego, ale zgłasza inny błąd. To się powiedzie w programie Visual Studio 2015 i kończy się niepowodzeniem w programie Visual Studio 2017 z C2668.

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>Przestarzałe definicje typów

Program Visual Studio 2017 teraz wydaje poprawne Ostrzeżenie dla przestarzałych typów typedef zadeklarowanych w klasie lub strukturze. Poniższy przykład kompiluje bez ostrzeżeń w programie Visual Studio 2015. Produkuje C4996 w programie Visual Studio 2017.

```cpp
struct A
{
    // also for __declspec(deprecated)
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### `constexpr`

Program Visual Studio 2017 poprawnie zgłasza błąd, gdy operand po lewej stronie operacji oceniania warunkowo nie jest prawidłowy w kontekście constexpr. Poniższy kod kompiluje się w programie Visual Studio 2015, ale nie w programie Visual Studio 2017, gdzie wywołuje C3615 `constexpr function 'f' cannot result in a constant expression` :

```cpp
template<int N>
struct array
{
    int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615
}
```

Aby poprawić błąd, należy zadeklarować `array::size()` funkcję jako **`constexpr`** lub usunąć **`constexpr`** kwalifikator z elementu `f` .

### <a name="class-types-passed-to-variadic-functions"></a>Typy klas przenoszone do funkcji wariadyczne

W programie Visual Studio 2017 klasy lub struktury, które są przenoszone do funkcji wariadyczne, takie jak, muszą być składowane do `printf` kopiowania. Podczas przekazywania takich obiektów kompilator po prostu wykonuje kopię bitową i nie wywołuje konstruktora ani destruktora.

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function.
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

Aby poprawić błąd, można wywołać funkcję członkowską, która zwraca typ z możliwością kopiowania,

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

lub można użyć rzutowania statycznego, aby przekonwertować obiekt przed jego przekazaniem:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

W przypadku ciągów skompilowanych i zarządzanych przy użyciu `CString` , dostarczone, `operator LPCTSTR()` powinno być używane do rzutowania `CString` obiektu na wskaźnik C oczekiwany przez ciąg formatu.

```cpp
CString str1;
CString str2 = _T("hello!");
str1.Format(_T("%s"), static_cast<LPCTSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>Kwalifikatory CV w konstrukcji klasy

W programie Visual Studio 2015 kompilator czasami niepoprawnie ignoruje kwalifikator CV podczas generowania obiektu klasy za pośrednictwem wywołania konstruktora. Przyczyną tego problemu może być awaria lub nieoczekiwane zachowanie środowiska uruchomieniowego. Poniższy przykład kompiluje w programie Visual Studio 2015, ale wywołuje błąd kompilatora w programie Visual Studio 2017:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Aby poprawić błąd, zadeklaruj `operator int()` jako **`const`** .

### <a name="access-checking-on-qualified-names-in-templates"></a>Sprawdzanie dostępu do nazw kwalifikowanych w szablonach

Poprzednie wersje kompilatora nie sprawdziły dostępu do kwalifikowanych nazw w niektórych kontekstach szablonów. Ten problem może zakłócać oczekiwane zachowanie SFINAE, w którym zastępowanie nie powiedzie się z powodu niedostępności nazwy. Przyczyną może być awaria lub nieoczekiwane zachowanie w czasie wykonywania, ponieważ kompilator nieprawidłowo wywołuje nieprawidłowe Przeciążenie operatora. W programie Visual Studio 2017 został zgłoszony błąd kompilatora. Konkretny błąd może się różnić, ale zazwyczaj jest to C2672 `no matching overloaded function found` . Poniższy kod kompiluje się w programie Visual Studio 2015, ale zgłasza błąd w programie Visual Studio 2017:

```cpp
#include <type_traits>

template <class T> class S {
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```

### <a name="missing-template-argument-lists"></a>Brak list argumentów szablonu

W programie Visual Studio 2015 i starszych kompilator nie zdiagnozuje wszystkich brakujących list argumentów szablonu. Nie będzie to możliwe, gdy na liście parametrów szablonu pojawił się brakujący szablon: na przykład, gdy brakuje części argumentu szablonu domyślnego lub parametru szablonu bez typu. Przyczyną tego problemu może być nieprzewidywalne zachowanie, w tym awarie kompilatora lub nieoczekiwane zachowanie środowiska uruchomieniowego. Poniższy kod kompiluje się w programie Visual Studio 2015, ale generuje błąd w programie Visual Studio 2017.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>Wyrażenie — SFINAE

Aby można było obsługiwać wyrażenie SFINAE, kompilator analizuje argumenty, **`decltype`** gdy są one deklarowane zamiast tworzenia wystąpienia. W związku z tym, jeśli w argumencie decltype zostanie znaleziony niezależna specjalizacja, nie zostanie ona odroczona do utworzenia wystąpienia. Jest on przetwarzany natychmiast i wszystkie wynikłe błędy są zdiagnozowane w tym czasie.

Poniższy przykład pokazuje błąd kompilatora, który jest wywoływany w punkcie deklaracji:

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT>
class IsCallable
{
public:
    struct BadType {};

    template <class U>
    static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>

    template <class U>
    static BadType Test(...);

    static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

### <a name="classes-declared-in-anonymous-namespaces"></a>Klasy zadeklarowane w anonimowych przestrzeniach nazw

Zgodnie ze standardem C++ Klasa zadeklarowana wewnątrz anonimowej przestrzeni nazw ma połączenie wewnętrzne i oznacza, że nie można jej wyeksportować. W programie Visual Studio 2015 i starszych ta reguła nie została wymuszona. W programie Visual Studio 2017 reguła jest wymuszana częściowo. W programie Visual Studio 2017 następujący przykład zgłasza błąd C2201: `const anonymous namespace::S1::vftable: must have external linkage in order to be exported/imported.`

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Domyślne inicjatory dla elementów członkowskich klasy wartości (C++/CLI)

W programie Visual Studio 2015 i starszych kompilator dozwolony (ale ignorowany) domyślny inicjator elementu członkowskiego dla elementu członkowskiego klasy wartości. Domyślna Inicjalizacja klasy wartości zawsze zero — inicjuje członków. Konstruktor domyślny jest niedozwolony. W programie Visual Studio 2017 domyślne inicjatory elementów członkowskich zgłaszają błąd kompilatora, jak pokazano w tym przykładzie:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // isn't allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Indeksatory domyślne (C++/CLI)

W programie Visual Studio 2015 i starszych kompilator w niektórych przypadkach nie określił domyślnej właściwości jako domyślnego indeksatora. Można obejść ten problem, używając identyfikatora, **`default`** Aby uzyskać dostęp do właściwości. Samo obejście stało się problematyczne po **`default`** wprowadzeniu słowa kluczowego w języku c++ 11. W programie Visual Studio 2017 zostały naprawione błędy wymagające obejścia. Kompilator wywołuje teraz błąd, gdy **`default`** jest używany do uzyskania dostępu do właściwości domyślnej klasy.

```cpp
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

W programie Visual Studio 2017 można uzyskać dostęp do obu właściwości wartości według ich nazwy:

```cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="bug-fixes-in-153"></a><a name="update_153"></a> Poprawki błędów w 15,3

### <a name="calls-to-deleted-member-templates"></a>Wywołania usuniętych szablonów elementów członkowskich

W poprzednich wersjach programu Visual Studio kompilator w niektórych przypadkach nie wyemituje błędu dla niepoprawnie sformułowanych wywołań do usuniętego szablonu elementu członkowskiego. Te wywołania mogłyby powodować awarie w czasie wykonywania. Poniższy kod generuje teraz C2280 `'int S<int>::f<int>(void)': attempting to reference a deleted function` :

```cpp
template<typename T>
struct S {
   template<typename U> static int f() = delete;
};

void g()
{
   decltype(S<int>::f<int>()) i; // this should fail
}
```

Aby naprawić ten błąd, zadeklaruj `i` jako **`int`** .

### <a name="pre-condition-checks-for-type-traits"></a>Sprawdzanie warunków wstępnych dla cech typu

Program Visual Studio 2017 w wersji 15,3 poprawia warunki wstępne dla cech typu, aby dokładniej przestrzegać standardu. Takie sprawdzenie jest przeznaczone do przypisania. Poniższy kod generuje C2139 w programie Visual Studio 2017 w wersji 15,3:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Nowe ostrzeżenie kompilatora i testy środowiska uruchomieniowego na potrzeby organizowania w trybie macierzystym

Wywołanie z funkcji zarządzanych do funkcji natywnych wymaga organizowania. Środowisko CLR wykonuje kierowanie, ale nie rozpoznaje semantyki języka C++. W przypadku przekazania obiektu macierzystego przez wartość środowisko CLR wywołuje Konstruktor kopiujący obiektu lub używa `BitBlt` , co może spowodować niezdefiniowane zachowanie w czasie wykonywania.

Teraz kompilator emituje ostrzeżenie, jeśli odnajdzie ten błąd w czasie kompilacji: obiekt macierzysty z usuniętym elementem Copy ctor zostanie przeniesiony między natywną i zarządzaną granicą przez wartość. Dla tych przypadków, w których kompilator nie wie w czasie kompilacji, wprowadza sprawdzanie środowiska uruchomieniowego, tak że program wywołuje się `std::terminate` natychmiast po niepoprawnym kierowaniu. W programie Visual Studio 2017 w wersji 15,3 następujący kod generuje ostrzeżenie C4606 `'A': passing argument by value across native and managed boundary requires valid copy constructor. Otherwise, the runtime behavior is undefined.`

```cpp
class A
{
public:
   A() : p_(new int) {}
   ~A() { delete p_; }

   A(A const &) = delete;
   A(A &&rhs) {
   p_ = rhs.p_;
}

private:
   int *p_;
};

#pragma unmanaged

void f(A a)
{
}

#pragma managed

int main()
{
    f(A()); // This call from managed to native requires marshaling. The CLR doesn't understand C++ and uses BitBlt, which results in a double-free later.
}
```

Aby naprawić ten błąd, Usuń `#pragma managed` dyrektywę, aby oznaczyć obiekt wywołujący jako natywny i uniknąć organizowania.

### <a name="experimental-api-warning-for-winrt"></a>Ostrzeżenie eksperymentalnego interfejsu API dla środowiska WinRT

Interfejsy API WinRT, które są udostępniane na potrzeby eksperymentowania i przesyłania opinii, są dekoracyjne `Windows.Foundation.Metadata.ExperimentalAttribute` . W programie Visual Studio 2017 w wersji 15,3 kompilator tworzy ostrzeżenie C4698 dla tego atrybutu. Kilka interfejsów API we wcześniejszych wersjach Windows SDK zostało już uzupełnione atrybutem, a wywołania tych interfejsów API teraz wyzwalają to ostrzeżenie kompilatora. Nowsze zestawy SDK systemu Windows mają atrybuty usunięte ze wszystkich typów wysłanych. Jeśli używasz starszego zestawu SDK, musisz pominąć te ostrzeżenia dla wszystkich wywołań typów wysłanych.

Poniższy kod generuje ostrzeżenie C4698: `'Windows::Storage::IApplicationDataStatics2::GetForUserAsync' is for evaluation purposes only and is subject to change or removal in future updates` :

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); //C4698
```

Aby wyłączyć ostrzeżenie, Dodaj #pragma:

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>Definicja poza wierszem funkcji składowej szablonu

Program Visual Studio 2017 w wersji 15,3 generuje błąd w przypadku definicji poza wierszem funkcji składowej szablonu, która nie została zadeklarowana w klasie. Poniższy kod generuje teraz błąd C2039: `'f': is not a member of 'S'` :

```cpp
struct S {};

template <typename T>
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

Aby naprawić ten błąd, Dodaj deklarację do klasy:

```cpp
struct S {
    template <typename T>
    void f(T t);
};
template <typename T>
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>Podjęto próbę uzyskania adresu `this` wskaźnika

W języku C++ **`this`** to wartością prvalue bez typu wskaźnik do X. Nie można pobrać adresu **`this`** ani powiązać go z odwołaniem do lvalue. W poprzednich wersjach programu Visual Studio kompilator zezwolił na obejście tego ograniczenia przez użycie rzutowania. W programie Visual Studio 2017 w wersji 15,3 kompilator tworzy błąd C2664.

### <a name="conversion-to-an-inaccessible-base-class"></a>Konwersja do niedostępnej klasy bazowej

Program Visual Studio 2017 w wersji 15,3 generuje błąd podczas próby przekonwertowania typu na klasę bazową, która jest niedostępna. Kompilator podnosi teraz błąd C2243: `'type cast': conversion from 'D *' to 'B *' exists, but is inaccessible` . Następujący kod jest źle sformułowany i może spowodować awarię w czasie wykonywania. Kompilator tworzy teraz C2243, gdy widzi następujący kod:

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-arent-allowed-on-out-of-line-definitions-of-member-functions"></a>Argumenty domyślne nie są dozwolone dla definicji poza wierszem funkcji Członkowskich

Argumenty domyślne nie są dozwolone w definicjach wbudowanych funkcji Członkowskich w klasach szablonów. Kompilator wyda ostrzeżenie w obszarze **`/permissive`** i twardy błąd w obszarze [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

W poprzednich wersjach programu Visual Studio następujący źle skonstruowany kod może potencjalnie spowodować awarię środowiska uruchomieniowego. Program Visual Studio 2017 w wersji 15,3 generuje ostrzeżenie C5034: `'A\<T>::f': an out-of-line definition of a member of a class template cannot have default arguments` :

```cpp
template <typename T>
struct A {
    T f(T t, bool b = false);
};

template <typename T>
T A<T>::f(T t, bool b = false) // C5034
{
    // ...
}
```

Aby naprawić ten błąd, Usuń `= false` domyślny argument.

### <a name="use-of-offsetof-with-compound-member-designator"></a>Użycie `offsetof` ze wskaźnikiem złożonego elementu członkowskiego

W programie Visual Studio 2017 w wersji 15,3 przy użyciu `offsetof(T, m)` gdzie *m* jest "złożonego elementu członkowskiego" powoduje ostrzeżenie podczas kompilowania z **`/Wall`** opcją. Następujący kod jest źle sformułowany i może spowodować awarię w czasie wykonywania. Program Visual Studio 2017 w wersji 15,3 generuje ostrzeżenie C4841: `non-standard extension used: compound member designator in offsetof` :

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

Aby naprawić kod, Wyłącz ostrzeżenie przy użyciu dyrektywy pragma lub Zmień kod na nieużywany `offsetof` :

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Używanie `offsetof` ze statycznym elementem członkowskim danych lub funkcją członkowską

W programie Visual Studio 2017 w wersji 15,3, użycie `offsetof(T, m)` gdzie *m* odwołuje się do statycznej składowej danych lub funkcji członkowskiej powoduje błąd. Poniższy kod generuje błąd C4597: `undefined behavior: offsetof applied to member function 'example'` i Error C4597: `undefined behavior: offsetof applied to static data member 'sample'` :

```cpp
#include <cstddef>

struct A {
   int ten() { return 10; }
   static constexpr int two = 2;
};

constexpr auto off = offsetof(A, ten);
constexpr auto off2 = offsetof(A, two);
```

Ten kod jest źle sformułowany i może spowodować awarię w czasie wykonywania. Aby naprawić ten błąd, Zmień kod, aby nie wywoływać niezdefiniowanego zachowania. Nie jest to kod przenośny, który jest niedozwolony w standardzie C++.

### <a name="new-warning-on-__declspec-attributes"></a><a name="declspec"></a> Nowe ostrzeżenie dotyczące `__declspec` atrybutów

W programie Visual Studio 2017 w wersji 15,3 kompilator nie ignoruje atrybutów, jeśli `__declspec(...)` są stosowane przed `extern "C"` specyfikacją powiązania. Wcześniej kompilator zignoruje atrybut, który może mieć konsekwencje dla środowiska uruchomieniowego. Gdy **`/Wall`** Opcje i **`/WX`** są ustawione, poniższy kod generuje ostrzeżenie C4768: `__declspec attributes before linkage specification are ignored` :

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Aby usunąć ostrzeżenie, należy `extern "C"` najpierw umieścić:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

To ostrzeżenie jest domyślnie wyłączone w 15,3, ale domyślnie włączone w 15,5 i ma wpływ tylko na kod skompilowany przy użyciu  **`/Wall`** **`/WX`** .

### <a name="decltype-and-calls-to-deleted-destructors"></a>`decltype` i wywołania usuniętych destruktorów

W poprzednich wersjach programu Visual Studio kompilator nie wykrył, kiedy wywołanie usuniętego destruktora wystąpi w kontekście wyrażenia skojarzonego z **`decltype`** . W programie Visual Studio 2017 w wersji 15,3 następujący kod generuje błąd C2280: `'A<T>::~A(void)': attempting to reference a deleted function` :

```cpp
template<typename T>
struct A
{
   ~A() = delete;
};

template<typename T>
auto f() -> A<T>;

template<typename T>
auto g(T) -> decltype((f<T>()));

void h()
{
   g(42);
}
```

### <a name="uninitialized-const-variables"></a>Niezainicjowane zmienne const

Wersja programu Visual Studio 2017 RTW ma regresję: kompilator języka C++ nie wystawia diagnostyki dla niezainicjowanej **`const`** zmiennej. Ta regresja została naprawiona w programie Visual Studio 2017 w wersji 15,3. Poniższy kod generuje teraz ostrzeżenie C4132: `'Value': const object should be initialized` :

```cpp
const int Value; //C4132
```

Aby naprawić ten błąd, przypisz wartość do `Value` .

### <a name="empty-declarations"></a>Puste deklaracje

Program Visual Studio 2017 w wersji 15,3 wyświetla teraz ostrzeżenie dotyczące pustych deklaracji dla wszystkich typów, a nie tylko typów wbudowanych. Poniższy kod tworzy teraz ostrzeżenie C4091 poziomu 2 dla wszystkich czterech deklaracji:

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };

int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

Aby usunąć ostrzeżenia, skomentować lub usunąć puste deklaracje. W przypadkach, gdy obiekt bez nazwy ma wpływ na efekt uboczny (na przykład RAII), powinien mieć nazwę.

Ostrzeżenie jest wyłączone w obszarze **`/Wv:18`** i jest domyślnie włączone w obszarze ostrzeżenie poziom W2.

### <a name="stdis_convertible-for-array-types"></a>`std::is_convertible` dla typów tablicowych

Poprzednie wersje kompilatora udzieliły nieprawidłowych wyników dla typów tablicowych [std:: is_convertible](../standard-library/is-convertible-class.md) . Te wymagane przez bibliotekę moduły zapisujące do specjalnego przypadku kompilator języka Microsoft C++ w przypadku używania `std::is_convertible<...>` cech typu. W poniższym przykładzie, statyczne potwierdzenia są przekazywane we wcześniejszych wersjach programu Visual Studio, ale kończą się niepowodzeniem w programie Visual Studio 2017 w wersji 15,3:

```cpp
#include <type_traits>

using Array = char[1];

static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

`std::is_convertible<From, To>` jest obliczany przez sprawdzenie, czy definicja funkcji urojonej jest poprawnie sformułowana:

```cpp
   To test() { return std::declval<From>(); }
```

### <a name="private-destructors-and-stdis_constructible"></a>Destruktory prywatne i `std::is_constructible`

Poprzednie wersje kompilatora zostały zignorowane, niezależnie od tego, czy destruktor był prywatny podczas decydowania o wyniku [std:: is_constructible](../standard-library/is-constructible-class.md). Teraz traktuje je. W poniższym przykładzie, statyczne potwierdzenia są przekazywane we wcześniejszych wersjach programu Visual Studio, ale kończą się niepowodzeniem w programie Visual Studio 2017 w wersji 15,3:

```cpp
#include <type_traits>

class PrivateDtor {
   PrivateDtor(int) { }
private:
   ~PrivateDtor() { }
};

// This assertion used to succeed. It now correctly fails.
static_assert(std::is_constructible<PrivateDtor, int>::value);
```

Prywatne destruktory powodują, że typ nie jest konstrukcyjną. `std::is_constructible<T, Args...>` jest obliczana tak, jakby została zapisywana następująca deklaracja:

```cpp
   T obj(std::declval<Args>()...)
```

To wywołanie implikuje wywołanie destruktora.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: niejednoznaczne Rozpoznanie przeciążenia

W poprzednich wersjach kompilatora czasami nie można wykryć niejednoznaczności, gdy znaleziono wiele kandydatów za pośrednictwem deklaracji using i wyszukiwania zależnego od argumentów. Ten błąd może prowadzić do wybranego błędnego przeciążenia i do nieoczekiwanego zachowania w czasie wykonywania. W poniższym przykładzie program Visual Studio 2017 w wersji 15,3 poprawnie podnosi C2668 `'f': ambiguous call to overloaded function` :

```cpp
namespace N {
   template<class T>
   void f(T&, T&);

   template<class T>
   void f();
}

template<class T>
void f(T&, T&);

struct S {};
void f()
{
   using N::f;

   S s1, s2;
   f(s1, s2); // C2668
}
```

Aby naprawić kod, Usuń instrukcję using, `N::f` Jeśli zamierzasz wywołać metodę `::f()` .

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: lokalne deklaracje funkcji i wyszukiwanie zależne od argumentów

Deklaracje funkcji lokalnych — ukrywanie deklaracji funkcji w otaczającym zakresie i wyłączanie wyszukiwania zależnego od argumentów. Jednak poprzednie wersje kompilatora zawsze przeprowadził wyszukiwanie zależne od argumentów w tym przypadku. Może to spowodować błędne Przeciążenie i nieoczekiwane zachowanie w czasie wykonywania. Zazwyczaj błąd jest spowodowany niepoprawną sygnaturą deklaracji funkcji lokalnej. W poniższym przykładzie program Visual Studio 2017 w wersji 15,3 poprawnie podnosi C2660 `'f': function does not take two arguments` :

```cpp
struct S {};
void f(S, int);

void g()
{
   void f(S); // C2660 'f': function does not take 2 arguments:
   // or void f(S, int);
   S s;
   f(s, 0);
}
```

Aby rozwiązać ten problem, Zmień `f(S)` podpis lub usuń go.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: kolejność inicjowania na listach inicjatorów

Elementy członkowskie klasy są inicjowane w kolejności, w jakiej zostały zadeklarowane, a nie kolejności, w której występują listy inicjatorów. Poprzednie wersje kompilatora nie ostrzegają, gdy porządek listy inicjatora różni się od kolejności deklaracji. Ten problem może prowadzić do niezdefiniowanego zachowania środowiska uruchomieniowego, jeśli jedna składowa jest zależna od innego elementu członkowskiego na liście, który jest już zainicjowany. W poniższym przykładzie program Visual Studio 2017 w wersji 15,3 (z **`/Wall`** ) podnosi ostrzeżenie C5038: `data member 'A::y' will be initialized after data member 'A::x'` :

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Aby rozwiązać ten problem, Rozmieść listę inicjatorów tak samo jak w przypadku deklaracji. Podobne ostrzeżenie jest zgłaszane, gdy jeden lub oba inicjatory odnoszą się do składowych klasy bazowej.

To ostrzeżenie jest domyślnie wyłączone i ma wpływ tylko na kod skompilowany przy użyciu **`/Wall`** .

## <a name="bug-fixes-and-other-behavior-changes-in-155"></a><a name="update_155"></a> Poprawki błędów i inne zmiany zachowań w 15,5

### <a name="partial-ordering-change"></a>Zmiana kolejności częściowej

Kompilator prawidłowo odrzuca Poniższy kod i wyświetla prawidłowy komunikat o błędzie:

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(const T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);    // C2668
}
```

```Output
t161.cpp
t161.cpp(16): error C2668: 'f': ambiguous call to overloaded function
t161.cpp(8): note: could be 'int f<int*>(const T &)'
        with
        [
            T=int*
        ]
t161.cpp(2): note: or       'int f<int>(int*)'
t161.cpp(16): note: while trying to match the argument list '(int*)'
```

Problem opisany w powyższym przykładzie polega na tym, że istnieją dwie różnice w typach (const a non-const i Pack a pakiet poza pakietem). Aby wyeliminować błąd kompilatora, Usuń jedną z różnic. Następnie kompilator może jednoznaczowo zamówić funkcje.

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);
}
```

### <a name="exception-handlers"></a>Obsługa wyjątków

Procedury obsługi odwołania do typu tablicy lub funkcji nigdy nie są zgodne z żadnym obiektem wyjątku. Kompilator prawidłowo przestrzega tej reguły i wywołuje ostrzeżenie poziomu 4. Nie dopasowuje już również procedury obsługi `char*` lub `wchar_t*` do literału ciągu, gdy **`/Zc:strictStrings`** jest używany.

```cpp
int main()
{
    try {
        throw "";
    }
    catch (int (&)[1]) {} // C4843 (This should always be dead code.)
    catch (void (&)()) {} // C4843 (This should always be dead code.)
    catch (char*) {} // This should not be a match under /Zc:strictStrings
}
```

```Output
warning C4843: 'int (&)[1]': An exception handler of reference to array or function type is unreachable, use 'int*' instead
warning C4843: 'void (__cdecl &)(void)': An exception handler of reference to array or function type is unreachable, use 'void (__cdecl*)(void)' instead
```

Poniższy kod pozwala uniknąć błędu:

```cpp
catch (int (*)[1]) {}
```

### <a name="stdtr1-namespace-is-deprecated"></a><a name="tr1"></a>`std::tr1`przestrzeń nazw jest przestarzała

Niestandardowa `std::tr1` przestrzeń nazw jest teraz oznaczona jako przestarzała w trybach c++ 14 i c++ 17. W programie Visual Studio 2017 w wersji 15,5 następujący kod wywołuje C4996:

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::tr1::function<int (int, int)> f = std::plus<int>(); //C4996
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

```Output
warning C4996: 'std::tr1': warning STL4002: The non-standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
```

Aby naprawić ten błąd, usuń odwołanie do `tr1` przestrzeni nazw:

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::function<int (int, int)> f = std::plus<int>();
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

### <a name="standard-library-features-in-annex-d-are-marked-as-deprecated"></a><a name="annex_d"></a> Standardowe funkcje biblioteki w załączniku D są oznaczone jako przestarzałe

Gdy **`/std:c++17`** przełącznik kompilatora trybu jest ustawiony, prawie wszystkie standardowe funkcje biblioteki w załączniku D są oznaczane jako przestarzałe.

W programie Visual Studio 2017 w wersji 15,5 następujący kod wywołuje C4996:

```cpp
#include <iterator>

class MyIter : public std::iterator<std::random_access_iterator_tag, int> {
public:
    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

```Output
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
```

Aby naprawić ten błąd, postępuj zgodnie z instrukcjami wyświetlanymi w tekście ostrzegawczym, jak pokazano w poniższym kodzie:

```cpp
#include <iterator>

class MyIter {
public:
    typedef std::random_access_iterator_tag iterator_category;
    typedef int value_type;
    typedef ptrdiff_t difference_type;
    typedef int* pointer;
    typedef int& reference;

    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

### <a name="unreferenced-local-variables"></a>Zmienne lokalne, do których nie istnieją odwołania

W programie Visual Studio 15,5 ostrzeżenie C4189 jest emitowane w więcej przypadków, jak pokazano w poniższym kodzie:

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}
```

```Output
warning C4189: 's': local variable is initialized but not referenced
```

Aby naprawić ten błąd, Usuń nieużywaną zmienną.

### <a name="single-line-comments"></a>Komentarze jednowierszowe

W programie Visual Studio 2017 w wersji 15,5 ostrzeżenia C4001 i C4179 nie są już emitowane przez kompilator języka C. Wcześniej były emitowane tylko pod **`/Za`** przełącznikiem kompilatora.  Ostrzeżenia nie są już potrzebne, ponieważ Komentarze jednowierszowe były częścią standardu C od C99.

```cpp
/* C only */
#pragma warning(disable:4001) //C4619
#pragma warning(disable:4179)
// single line comment
//* single line comment */
```

```Output
warning C4619: #pragma warning: there is no warning number '4001'
```

Gdy kod nie musi być zgodny z poprzednimi wersjami, można uniknąć ostrzeżenia przez usunięcie pomijania C4001/C4179. Jeśli kod musi być zgodny z poprzednimi wersjami, Pomiń tylko C4619.

```C

/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="__declspec-attributes-with-extern-c-linkage"></a>`__declspec` atrybuty z `extern "C"` powiązaniem

We wcześniejszych wersjach programu Visual Studio kompilator zignorował atrybuty, `__declspec(...)` gdy `__declspec(...)` zostały zastosowane przed `extern "C"` specyfikacją powiązania. To zachowanie spowodowało wygenerowanie kodu, który nie jest przeznaczony dla użytkownika, z możliwymi implikacjami środowiska uruchomieniowego. Ostrzeżenie zostało dodane w programie Visual Studio w wersji 15,3, ale było domyślnie wyłączone. W programie Visual Studio 2017 w wersji 15,5 ostrzeżenie jest domyślnie włączone.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

Aby naprawić ten błąd, należy umieścić specyfikację powiązania przed atrybutem __declspec:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Ten nowy C4768 ostrzegawczy jest określony w niektórych nagłówkach Windows SDK, które zostały dostarczone z programem Visual Studio 2017 15,3 lub starszym (na przykład: Version 10.0.15063.0, znanym również jako RS2 SDK). Jednak późniejsze wersje nagłówków Windows SDK (w tym ShlObj. h i ShlObj_core. h) zostały naprawione, aby nie wygenerowały ostrzeżenia. Po wyświetleniu tego ostrzeżenia pochodzącego z nagłówków Windows SDK można wykonać następujące czynności:

1. Przejdź do najnowszego Windows SDK dołączonego do wersji 15,5 programu Visual Studio 2017.

1. Wyłącz ostrzeżenie wokół #include instrukcji Windows SDK nagłówka:

```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern-constexpr-linkage"></a><a name="extern_linkage"></a>`extern constexpr`połączenie

We wcześniejszych wersjach programu Visual Studio kompilator zawsze udzielił **`constexpr`** zmiennej wewnętrznej powiązania, nawet gdy zmienna została oznaczona **`extern`** . W programie Visual Studio 2017 w wersji 15,5 nowy przełącznik kompilatora ( **`/Zc:externConstexpr`** ) umożliwia poprawne, zgodne ze standardami zachowanie. Ostatecznie to zachowanie stanie się wartością domyślną.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Jeśli plik nagłówkowy zawiera zadeklarowaną zmienną **`extern constexpr`** , należy ją oznaczyć, `__declspec(selectany)` aby pozostały prawidłowo połączone deklaracje:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>`typeid` nie można użyć dla niekompletnego typu klasy

We wcześniejszych wersjach programu Visual Studio kompilator niepoprawnie zezwolił na następujący kod, co spowodowało nieprawidłowe informacje o typie. W programie Visual Studio 2017 w wersji 15,5 kompilator prawidłowo zgłasza błąd:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdis_convertible-target-type"></a>`std::is_convertible` Typ docelowy

`std::is_convertible` wymaga, aby typ docelowy był prawidłowym zwracanym typem. We wcześniejszych wersjach programu Visual Studio kompilator nieprawidłowo zezwolił typy abstrakcyjne, co może prowadzić do niepoprawnego rozpoznawania przeciążenia i niezamierzonego zachowania w czasie wykonywania.  Następujący kod teraz prawidłowo podnosi C2338:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

Aby uniknąć błędu, w przypadku użycia należy `is_convertible` porównać typy wskaźnika, ponieważ porównanie typu niebędącego wskaźnikiem może zakończyć się niepowodzeniem, jeśli jeden typ jest abstrakcyjny:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="dynamic-exception-specification-removal-and-noexcept"></a><a name="noexcept_removal"></a> Usuwanie specyfikacji wyjątku dynamicznego i `noexcept`

W języku C++ 17 `throw()` jest alias dla **`noexcept`** i jest `throw(<type list>)` `throw(...)` usuwany, a niektóre typy mogą obejmować **`noexcept`** . Ta zmiana może powodować problemy ze zgodnością źródła z kodem, który jest zgodny z językiem C++ 14 lub wcześniejszym. **`/Zc:noexceptTypes-`** Przełącznik może być używany do przywracania wersji c++ 14 systemu, w którym jest **`noexcept`** używany tryb c++ 17. Umożliwia zaktualizowanie kodu źródłowego tak, aby był zgodny z językiem C++ 17 bez konieczności ponownego pisania całego `throw()` kodu.

Kompilator również diagnozuje teraz bardziej niezgodne specyfikacje wyjątków w deklaracjach w trybie C++ 17 lub z [`/permissive-`](../build/reference/permissive-standards-conformance.md) nowym C5043 ostrzegawczym.

Poniższy kod generuje C5043 i C5040 w programie Visual Studio 2017 w wersji 15,5 w przypadku **`/std:c++17`** zastosowania przełącznika:

```cpp
void f() throw(); // equivalent to void f() noexcept;
void f() {} // warning C5043
void g() throw(); // warning C5040

struct A {
    virtual void f() throw();
};

struct B : A {
    virtual void f() { } // error C2694
};
```

Aby usunąć błędy nadal przy użyciu programu **`/std:c++17`** , Dodaj **`/Zc:noexceptTypes-`** przełącznik do wiersza polecenia lub w przeciwnym razie zaktualizuj kod, który ma być używany **`noexcept`** , jak pokazano w następującym przykładzie:

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A {
    virtual void f() noexcept;
};

struct B : A {
    virtual void f() noexcept { }
};
```

### <a name="inline-variables"></a>Zmienne wbudowane

Statyczne **`constexpr`** elementy członkowskie danych są teraz niejawnie **`inline`** , co oznacza, że ich deklaracja w klasie jest teraz definicją. Używanie definicji out-of-line dla **`static constexpr`** elementu członkowskiego danych jest nadmiarowe i obecnie przestarzałe. W programie Visual Studio 2017 w wersji 15,5, gdy **`/std:c++17`** przełącznik zostanie zastosowany, poniższy kod generuje teraz ostrzeżenie C5041 `'size': out-of-line definition for constexpr static data member is not needed and is deprecated in C++17` :

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-__declspec-warning-c4768-now-on-by-default"></a>`extern "C" __declspec(...)` Ostrzeżenie C4768 teraz domyślnie

Ostrzeżenie zostało dodane w programie Visual Studio 2017 w wersji 15,3, ale było domyślnie wyłączone. W programie Visual Studio 2017 w wersji 15,5 ostrzeżenie jest domyślnie włączone. Aby uzyskać więcej informacji, zobacz [nowe ostrzeżenie na temat \_ \_ atrybutów declspec](#declspec).

### <a name="defaulted-functions-and-__declspecnothrow"></a>Funkcje domyślne i `__declspec(nothrow)`

Kompilator wcześniej zezwolił na Zadeklarowanie funkcji domyślnych, `__declspec(nothrow)` gdy odpowiadające im funkcje podstawowe/składowe dopuszczają wyjątki. To zachowanie jest sprzeczne ze standardem C++ i może spowodować niezdefiniowane zachowanie w czasie wykonywania. Standard wymaga, aby te funkcje były zdefiniowane jako usunięte, jeśli występuje niezgodność specyfikacji wyjątków.  W obszarze **`/std:c++17`** , poniższy kod wywołuje C2280 `attempting to reference a deleted function. Function was implicitly deleted because the explicit exception specification is incompatible with that of the implicit declaration.`

```cpp
struct A {
    A& operator=(const A& other) { // No exception specification; this function may throw.
        ...
    }
};

struct B : public A {
    __declspec(nothrow) B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1; // error C2280
}
```

Aby poprawić ten kod, Usuń __declspec (nothrow) z funkcji Default lub Usuń `= default` i podaj definicję dla funkcji wraz z dowolną wymaganą obsługą wyjątków:

```cpp
struct A {
    A& operator=(const A& other) {
        // ...
    }
};

struct B : public A {
    B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1;
}
```

### <a name="noexcept-and-partial-specializations"></a>`noexcept` i Częściowa specjalizacja

**`noexcept`** W przypadku systemu typu, Częściowa specjalizacja dla dopasowania określonych typów "możliwy do przełączenia" może nie zostać skompilowana lub nie można wybrać szablonu podstawowego z powodu braku częściowej specjalizacji dla wskaźników do-noexcept — Functions.

W takich przypadkach może być konieczne dodanie kolejnych częściowych specjalizacji do obsługi **`noexcept`** wskaźników funkcji i **`noexcept`** wskaźników do funkcji składowych. Te przeciążenia są dozwolone tylko w **`/std:c++17`** trybie. Jeśli należy zachować zgodność z poprzednimi wersjami przy użyciu języka C++ 14 i napisać kod, który są używane przez inne osoby, należy chronić te nowe przeciążenia wewnątrz `#ifdef` dyrektyw. Jeśli pracujesz w module, a następnie korzystasz z funkcji Guard, możesz `#ifdef` po prostu skompilować ją z **`/Zc:noexceptTypes-`** przełącznikiem.

Poniższy kod kompiluje się w obszarze, **`/std:c++14`** ale nie działa w ramach **`/std:c++17`** programu `error C2027: use of undefined type 'A<T>'` :

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // C2027
}
```

Następujący kod powiódł się, **`/std:c++17`** ponieważ kompilator wybiera nową częściową specjalizację `A<void (*)() noexcept>` :

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <>
struct A<void(*)() noexcept>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // OK
}
```

## <a name="bug-fixes-and-other-behavior-changes-in-157"></a><a name="update_157"></a> Poprawki błędów i inne zmiany zachowań w 15,7

### <a name="c17-default-argument-in-the-primary-class-template"></a>C++ 17: domyślny argument w szablonie klasy podstawowej

Ta zmiana zachowania jest warunkiem wstępnym [odejmowania argumentu szablonu dla szablonów klas — P0091R3](https://wg21.link/p0091r3).

Wcześniej kompilator zignorował domyślny argument w szablonie klasy podstawowej:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int = 0) {} // Re-definition necessary
```

W **`/std:c++17`** trybie w programie Visual Studio 2017 w wersji 15,7 domyślny argument nie jest ignorowany:

```cpp
template<typename T>
struct S {
    void f(int = 0);
};

template<typename T>
void S<T>::f(int) {} // Default argument is used
```

### <a name="dependent-name-resolution"></a>Rozpoznawanie nazw zależnych

Ta zmiana zachowania jest warunkiem wstępnym [odejmowania argumentu szablonu dla szablonów klas — P0091R3](https://wg21.link/p0091r3).

W poniższym przykładzie kompilator w Visual Studio 15,6 i wcześniejszy jest rozpoznawany `D::type` jako `B<T>::type` w szablonie klasy podstawowej.

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = B<T*>::type;
};
```

Program Visual Studio 2017 w wersji 15,7 w **`/std:c++17`** trybie wymaga **`typename`** słowa kluczowego w **`using`** instrukcji w D. Bez **`typename`** , kompilator zgłasza ostrzeżenie C4346: `'B<T*>::type': dependent name is not a type` i Error C2061: `syntax error: identifier 'type'` :

```cpp
template<typename T>
struct B {
    using type = T;
};

template<typename T>
struct D : B<T*> {
    using type = typename B<T*>::type;
};
```

### <a name="c17-nodiscard-attribute---warning-level-increase"></a>C++ 17: `[[nodiscard]]` zwiększenie poziomu ostrzeżenia dla atrybutu

W trybie programu Visual Studio 2017 w wersji 15,7 **`/std:c++17`** poziom ostrzeżeń C4834 `discarding return value of function with 'nodiscard' attribute` został zwiększony z platformy W3 do W1. Można wyłączyć ostrzeżenie z rzutowaniem na **`void`** lub przez przekazanie **`/wd:4834`** do kompilatora

```cpp
[[nodiscard]] int f() { return 0; }

int main() {
    f(); // warning: discarding return value
         // of function with 'nodiscard'
}
```

### <a name="variadic-template-constructor-base-class-initialization-list"></a>Lista inicjowania klasy bazowej konstruktora szablonów wariadyczne

W poprzednich wersjach programu Visual Studio Lista inicjowania klasy bazowej konstruktora szablonów wariadyczne, w której brakuje argumentów szablonu, została błędnie dozwolona bez błędu. W programie Visual Studio 2017 w wersji 15,7 występuje błąd kompilatora.

Poniższy przykład kodu w programie Visual Studio 2017 w wersji 15,7 zgłasza błąd C2614: `D<int>: illegal member initialization: 'B' is not a base or member` .

```cpp
template<typename T>
struct B {};

template<typename T>
struct D : B<T>
{

    template<typename ...C>
    D() : B() {} // C2614. Missing template arguments to B.
};

D<int> d;
```

Aby naprawić ten błąd, zmień wyrażenie B () na B \<T> ().

### <a name="constexpr-aggregate-initialization"></a>`constexpr` Inicjalizacja agregacji

Poprzednie wersje kompilatora języka C++ niepoprawnie obsłużyć **`constexpr`** inicjalizację agregacji. Kompilator zaakceptował nieprawidłowy kod, w którym lista agregacji init ma zbyt wiele elementów i wygenerowała złą codegen dla niego. Poniższy kod jest przykładem takiego kodu:

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {
        { 1, 2 },
        { 3, 4 }
    };
    return 0;
}
```

W programie Visual Studio 2017 w wersji 15,7 Update 3 i nowszych, poprzedni przykład teraz podnosi C2078 `too many initializers` . Poniższy przykład pokazuje, jak naprawić kod. Po zainicjowaniu `std::array` z zagnieżdżonymi nawiasami klamrowymi-init-list nadaj wewnętrznej tablicy listę własnych:

```cpp
#include <array>
struct X {
    unsigned short a;
    unsigned char b;
};

int main() {
    constexpr std::array<X, 2> xs = {{ // note double braces
        { 1, 2 },
        { 3, 4 }
    }}; // note double braces
    return 0;
}
```

## <a name="bug-fixes-and-behavior-changes-in-158"></a><a name="update_158"></a> Poprawki błędów i zmiany zachowań w 15,8

Zmiany w kompilatorze w programie Visual Studio 2017 w wersji 15,8 to wszystkie poprawki błędów i zachowania. Są one wymienione poniżej:

### <a name="typename-on-unqualified-identifiers"></a>`typename` w niekwalifikowanych identyfikatorach

W [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybie in fałszywe **`typename`** słowa kluczowe w niekwalifikowanych identyfikatorach w definicjach szablonów aliasów nie są już akceptowane przez kompilator. Poniższy kod generuje teraz C7511 `'T': 'typename' keyword must be followed by a qualified name` :

```cpp
template <typename T>
using  X = typename T;
```

Aby naprawić ten błąd, Zmień drugi wiersz na `using  X = T;` .

### <a name="__declspec-on-right-side-of-alias-template-definitions"></a>`__declspec()` po prawej stronie definicji szablonu aliasu

[__declspec](../cpp/declspec.md) nie jest już dozwolony po prawej stronie definicji szablonu aliasu. Wcześniej kompilator zaakceptował, ale zignorował ten kod. Nigdy nie spowoduje ostrzeżenia o zaniechaniu, gdy alias został użyty.

Zamiast tego można użyć standardowego atrybutu języka C++, który jest [ \[ \[ \] \] przestarzały](../cpp/attributes.md) , i jest przestrzegany w programie Visual Studio 2017 w wersji 15,6. Poniższy kod generuje teraz C2760 `syntax error: unexpected token '__declspec', expected 'type specifier'` :

```cpp
template <typename T>
using X = __declspec(deprecated("msg")) T;
```

Aby naprawić ten błąd, Zmień kod na następujący (z atrybutem umieszczonym przed znakiem "=" definicji aliasu):

```cpp
template <typename T>
using  X [[deprecated("msg")]] = T;
```

### <a name="two-phase-name-lookup-diagnostics"></a>Dwufazowe Diagnostyka wyszukiwania nazw

Dwufazowe wyszukiwanie nazw wymaga, aby nazwy niezależne używane w treści szablonu musiały być widoczne dla szablonu w czasie definicji. Wcześniej kompilator języka Microsoft C++ pozostawi nieznalezioną nazwę jako nieszukaną do czasu utworzenia wystąpienia. Teraz wymaga, aby nazwy niezależne były powiązane z treścią szablonu.

Jeden ze sposobów to manifest jest z wyszukiwaniem w zależnych klasach bazowych. Wcześniej kompilator mógł używać nazw, które są zdefiniowane w zależnych klasach bazowych. Wynika to z tego, że są one wyszukiwane podczas tworzenia wystąpienia po rozwiązaniu wszystkich typów. Teraz kod jest traktowany jako błąd. W takich przypadkach można wymusić wyszukanie zmiennej w czasie tworzenia wystąpienia, kwalifikując ją z typem klasy bazowej lub w inny sposób, na przykład przez dodanie `this->` wskaźnika.

W [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybie w programie Poniższy kod teraz podnosi C3861: `'base_value': identifier not found` :

```cpp
template <class T>
struct Base {
    int base_value = 42;
};

template <class T>
struct S : Base<T> {
    int f() {
        return base_value;
    }
};
```

Aby naprawić ten błąd, Zmień **`return`** instrukcję na `return this->base_value;` .

**Uwaga:** W bibliotece o zwiększeniu poziomu języka Python istnieje MSVC obejście dla deklaracji do przodu szablonu w [unwind_type. HPP](https://github.com/boostorg/python/blame/develop/include/boost/python/detail/unwind_type.hpp). W obszarze [`/permissive-`](../build/reference/permissive-standards-conformance.md) tryb rozpoczynający się w programie Visual Studio 2017 w wersji 15,8 ( \_ MSC \_ Ver = 1915) kompilator MSVC wykonuje prawidłowo wyszukiwanie nazw zależne od argumentów (ADL). Jest ona teraz spójna z innymi kompilatorami, co sprawia, że nie jest to konieczne. Aby uniknąć błędu C3861: `'unwind_type': identifier not found` , zobacz [PR 229](https://github.com/boostorg/python/pull/229) w obszarze zwiększenie poziomu repozytorium, aby zaktualizować plik nagłówkowy. Pakiet [vcpkg](../build/vcpkg.md) został już poprawiony, więc jeśli uzyskasz lub uaktualnisz swoje źródła wzrostu od vcpkg, nie musisz oddzielnie stosować poprawki.

### <a name="forward-declarations-and-definitions-in-namespace-std"></a>przekazywanie deklaracji i definicji w przestrzeni nazw `std`

Standard C++ nie zezwala użytkownikowi na dodawanie deklaracji lub definicji do przodu w przestrzeni nazw `std` . Dodawanie deklaracji lub definicji do przestrzeni nazw `std` lub do przestrzeni nazw w przestrzeni nazw spowoduje `std` teraz niezdefiniowane zachowanie.

W przyszłości firma Microsoft przeniesie lokalizację, w której są zdefiniowane niektóre standardowe typy bibliotek. Ta zmiana spowoduje uszkodzenie istniejącego kodu, który dodaje deklaracje przesyłania dalej do przestrzeni nazw `std` . Nowe ostrzeżenie, C4643, ułatwia identyfikowanie takich problemów źródłowych. Ostrzeżenie jest włączone w **`/default`** trybie i jest domyślnie wyłączone. Będzie to miało wpływ na programy skompilowane przy użyciu **`/Wall`** lub **`/WX`** .

Poniższy kod teraz podnosi C4643: `Forward declaring 'vector' in namespace std is not permitted by the C++ Standard` .

```cpp
namespace std {
    template<typename T> class vector;
}
```

Aby naprawić ten błąd, użyj dyrektywy **include** zamiast deklaracji do przodu:

```cpp
#include <vector>
```

### <a name="constructors-that-delegate-to-themselves"></a>Konstruktory, które są delegatem do siebie

Standard C++ sugeruje, że kompilator powinien emitować diagnostykę, gdy delegat delegowany do samego siebie. Kompilator Microsoft C++ w [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) trybie i [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) teraz podnosi C7535: `'X::X': delegating constructor calls itself` .

Bez tego błędu następujący program zostanie skompilowany, ale wygeneruje nieskończoną pętlę:

```cpp
class X {
public:
    X(int, int);
    X(int v) : X(v){}
};
```

Aby uniknąć nieskończonej pętli, delegat do innego konstruktora:

```cpp
class X {
public:

    X(int, int);
    X(int v) : X(v, 0) {}
};
```

### <a name="offsetof-with-constant-expressions"></a>`offsetof` z wyrażeniami stałymi

[makro OffsetOf](../c-runtime-library/reference/offsetof-macro.md) tradycyjnie zaimplementowano przy użyciu makra, które wymaga [reinterpret_cast](../cpp/reinterpret-cast-operator.md). To użycie jest niedozwolone w kontekstach, które wymagają wyrażenia stałego, ale kompilator języka Microsoft C++ tradycyjnie go zezwala. `offsetof`Makro, które jest dostarczane jako część biblioteki standardowej, prawidłowo używa wewnętrznego kompilatora ( **__builtin_offsetof** ), ale wiele osób użyło lew makro do definiowania własnych `offsetof` .

W programie Visual Studio 2017 w wersji 15,8 kompilator ogranicza obszary, które te **`reinterpret_cast`** Operatory mogą wyświetlać w trybie domyślnym, aby pomóc w kodzie zgodnym ze standardowym zachowaniem języka C++. W obszarze [`/permissive-`](../build/reference/permissive-standards-conformance.md) ograniczenia są jeszcze bardziej rygorystyczne. Użycie wyniku `offsetof` w miejscach, które wymagają wyrażeń stałych może spowodować powstanie kodu, który wystawia ostrzeżenie C4644 `usage of the macro-based offsetof pattern in constant expressions is non-standard; use offsetof defined in the C++ standard library instead` lub C2975 `invalid template argument, expected compile-time constant expression` .

Poniższy kod wywołuje C4644 w trybach **`/default`** i **`/std:c++17`** C2975 w [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybie:

```cpp
struct Data {
    int x;
};

// Common pattern of user-defined offsetof
#define MY_OFFSET(T, m) (unsigned long long)(&(((T*)nullptr)->m))

int main()

{
    switch (0) {
    case MY_OFFSET(Data, x): return 0;
    default: return 1;
    }
}
```

Aby naprawić ten błąd, użyj `offsetof` zdefiniowanego za pośrednictwem \<cstddef> :

```cpp
#include <cstddef>

struct Data {
    int x;
};

int main()
{
    switch (0) {
    case offsetof(Data, x): return 0;
    default: return 1;
    }
}
```

### <a name="cv-qualifiers-on-base-classes-subject-to-pack-expansion"></a>kwalifikatory OKS w klasach bazowych, które podlegają rozwinięciu pakietu

Poprzednie wersje kompilatora języka Microsoft C++ nie wykryły, że klasa bazowa miała kwalifikatory OKS, jeśli była również przedmiotem rozwinięcia pakietu.

W programie Visual Studio 2017 w wersji 15,8 w [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybie Poniższy kod wywołuje C3770 `'const S': is not a valid base class` :

```cpp
template<typename... T>
class X : public T... { };

class S { };

int main()
{
    X<const S> x;
}
```

### <a name="template-keyword-and-nested-name-specifiers"></a>`template` Specyfikator słowa kluczowego i zagnieżdżonej nazwy

W [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybie, kompilator wymaga teraz **`template`** słowa kluczowego, aby poprzedzać nazwę szablonu, gdy jest on dostępny Po specyfikatorze zagnieżdżonej nazwy.

Następujący kod w [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybie teraz podnosi C7510: `'example': use of dependent template name must be prefixed with 'template'. note: see reference to class template instantiation 'X<T>' being compiled` :

```cpp
template<typename T> struct Base
{
    template<class U> void example() {}
};

template<typename T>
struct X : Base<T>
{
    void example()
    {
        Base<T>::example<int>();
    }
};
```

Aby naprawić ten błąd, Dodaj **`template`** słowo kluczowe do `Base<T>::example<int>();` instrukcji, jak pokazano w następującym przykładzie:

```cpp
template<typename T> struct Base
{
    template<class U> void example() {}
};

template<typename T>
struct X : Base<T>
{
    void example()
    {
        // Add template keyword here:
        Base<T>::template example<int>();
    }
};
```

## <a name="bug-fixes-and-behavior-changes-in-159"></a><a name="update_159"></a> Poprawki błędów i zmiany zachowań w 15,9

### <a name="identifiers-in-member-alias-templates"></a>Identyfikatory w szablonach aliasów elementów członkowskich

Identyfikator używany w definicji szablonu aliasu składowej musi być zadeklarowany przed użyciem.

W poprzednich wersjach kompilatora można było użyć następującego kodu:

```cpp
template <typename... Ts>
struct A
{
  public:
    template <typename U>
    using from_template_t = decltype(from_template(A<U>{}));

  private:
    template <template <typename...> typename Type, typename... Args>
    static constexpr A<Args...> from_template(A<Type<Args...>>);
};

A<>::from_template_t<A<int>> a;
```

W programie Visual Studio 2017 w wersji 15,9 w [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybie kompilator podnosi C3861: `'from_template': identifier not found` .

Aby naprawić ten błąd, zadeklaruj `from_template` przed `from_template_t` .

### <a name="modules-changes"></a>Zmiany modułów

W programie Visual Studio 2017 w wersji 15,9 kompilator podnosi C5050 za każdym razem, gdy opcje wiersza polecenia modułów nie są spójne między elementami tworzenia modułu i zużycia modułu. W poniższym przykładzie występują dwa problemy:

- Opcja nie jest określona na stronie użycie (główna. cpp) **`/EHsc`** .

- Wersja języka C++ jest po **`/std:c++17`** stronie tworzenia i po **`/std:c++14`** stronie użycie.

```cmd
cl /EHsc /std:c++17 m.ixx /experimental:module
cl /experimental:module /module:reference m.ifc main.cpp /std:c++14
```

Kompilator podnosi C5050 dla obu tych przypadków: `warning C5050: Possible incompatible environment while importing module 'm': mismatched C++ versions.  Current "201402" module version "201703"` .

Kompilator podnosi także C7536 za każdym razem, gdy plik. IFC został naruszony. Nagłówek interfejsu modułu zawiera skrót algorytmu SHA2 zawartości poniżej. Podczas importowania plik. IFC jest używany do mieszania, a następnie sprawdzany pod kątem skrótu podanego w nagłówku. Jeśli te nie są zgodne, zostanie zgłoszony błąd C7536: `ifc failed integrity checks.  Expected SHA2: '66d5c8154df0c71d4cab7665bab4a125c7ce5cb9a401a4d8b461b706ddd771c6'` .

### <a name="partial-ordering-involving-aliases-and-non-deduced-contexts"></a>Kolejność częściowa obejmująca aliasy i niewnioskowane konteksty

Implementacje różnią się w regułach kolejności częściowej obejmujących aliasy w kontekstach niebędących wnioskami. W poniższym przykładzie w trakcie działania w ramach programu i kompilatora języka Microsoft C++ (w [`/permissive-`](../build/reference/permissive-standards-conformance.md) trybie) wystąpi błąd, podczas gdy Clang akceptuje kod.

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <class T, class Alloc>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

Poprzedni przykład podnosi C2668:

```Output
partial_alias.cpp(32): error C2668: 'f': ambiguous call to overloaded function
partial_alias.cpp(18): note: could be 'int f<Alloc,void>(A<void> &,const AlignedBuffer<10,4> &)'
partial_alias.cpp(12): note: or       'int f<Alloc,A<void>>(Alloc &,const AlignedBuffer<10,4> &)'
        with
        [
            Alloc=A<void>
        ]
partial_alias.cpp(32): note: while trying to match the argument list '(A<void>, AlignedBuffer<10,4>)'
```

Rozbieżność implementacji jest spowodowana regresją w standardowym edytorze języka C++. Problem z rozwiązaniem Core 2235 usunął jakiś tekst, który zezwoli na porządkowanie tych przeciążeń. Bieżący Standard języka C++ nie zapewnia mechanizmu do częściowo uporządkowania tych funkcji, więc są uważane za niejednoznaczne.

Aby obejść ten problem, zaleca się, aby nie polegać na częściowej kolejności tego problemu. Zamiast tego należy użyć SFINAE do usunięcia konkretnych przeciążeń. W poniższym przykładzie użyto klasy pomocnika `IsA` do usunięcia pierwszego przeciążenia, gdy `Alloc` jest specjalizacją `A` :

```cpp
#include <utility>
using size_t = std::size_t;

template <typename T>
struct A {};
template <size_t, size_t>
struct AlignedBuffer {};
template <size_t len>
using AlignedStorage = AlignedBuffer<len, 4>;

template <typename T> struct IsA : std::false_type {};
template <typename T> struct IsA<A<T>> : std::true_type {};

template <class T, class Alloc, typename = std::enable_if_t<!IsA<Alloc>::value>>
int f(Alloc &alloc, const AlignedStorage<T::size> &buffer)
{
    return 1;
}

template <class T, class Alloc>
int f(A<Alloc> &alloc, const AlignedStorage<T::size> &buffer)
{
    return 2;
}

struct Alloc
{
    static constexpr size_t size = 10;
};

int main()
{
    A<void> a;
    AlignedStorage<Alloc::size> buf;
    if (f<Alloc>(a, buf) != 2)
    {
        return 1;
    }

    return 0;
}
```

### <a name="illegal-expressions-and-non-literal-types-in-templated-function-definitions"></a>Niedozwolone wyrażenia i typy niebędące literałami w definicjach funkcji z szablonami

Niedozwolone wyrażenia i typy niebędące literałami są teraz prawidłowo zdiagnozowane w definicjach funkcji opartych na szablonach, które są jawnie wyspecjalizowane. Wcześniej takie błędy nie były emitowane dla definicji funkcji. Jednak niedozwolone wyrażenie lub typ niebędący literałem nadal będą zdiagnozowane, jeśli zostanie obliczony jako część wyrażenia stałej.

W poprzednich wersjach programu Visual Studio następujący kod kompiluje się bez ostrzeżenia:

```cpp
void g();

template<typename T>
struct S
{
    constexpr void f();
};

template<>
constexpr void S<int>::f()
{
    g(); // C3615 in 15.9
}
```

W programie Visual Studio 2017 w wersji 15,9 kod zgłasza ten błąd:

```Output
error C3615: constexpr function 'S<int>::f' cannot result in a constant expression.
note: failure was caused by call of undefined function or one not declared 'constexpr'
note: see usage of 'g'.
```

Aby uniknąć tego błędu, Usuń **`constexpr`** kwalifikator z jawnego tworzenia wystąpienia funkcji `f()` .

::: moniker-end

::: moniker range="msvc-140"

## <a name="c-conformance-improvements-in-visual-studio-2015"></a>Udoskonalenia zgodności języka C++ w programie Visual Studio 2015

Mamy pełną listę ulepszeń zgodności w programie Visual Studio 2015 Update 3. Aby uzyskać więcej informacji, zobacz [Visual C++ nowości od 2003 do 2015](../porting/visual-cpp-what-s-new-2003-through-2015.md).

::: moniker-end

## <a name="see-also"></a>Zobacz także

[Tabela zgodności języka Microsoft C++](visual-cpp-language-conformance.md)

---
description: Dowiedz się więcej na temat klasy regex_token_iterator
title: regex_token_iterator — Klasa
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_token_iterator
- regex/std::regex_token_iterator::regex_type
- regex/std::regex_token_iterator::value_type
- regex/std::regex_token_iterator::iterator_category
- regex/std::regex_token_iterator::difference_type
- regex/std::regex_token_iterator::pointer
- regex/std::regex_token_iterator::reference
- regex/std::regex_token_iterator::operator==
- regex/std::regex_token_iterator::operator!=
- regex/std::regex_token_iterator::operator*
- regex/std::regex_token_iterator::operator->
- regex/std::regex_token_iterator::operator++
helpviewer_keywords:
- std::regex_token_iterator [C++]
- std::regex_token_iterator [C++], regex_type
- std::regex_token_iterator [C++], value_type
- std::regex_token_iterator [C++], iterator_category
- std::regex_token_iterator [C++], difference_type
- std::regex_token_iterator [C++], pointer
- std::regex_token_iterator [C++], reference
ms.assetid: a213ba48-8e4e-4b6b-871a-2637acf05f15
ms.openlocfilehash: 752ff44864b435100bacb83250a5c6a792cab502
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243890"
---
# <a name="regex_token_iterator-class"></a>regex_token_iterator — Klasa

Klasa iteratora dla podpasowań.

## <a name="syntax"></a>Składnia

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_token_iterator
```

## <a name="parameters"></a>Parametry

*BidIt*\
Typ iteratora dla podpasowań.

*Elem*\
Typ elementów, do których ma pasować.

*RXtraits*\
Klasa cech dla elementów.

## <a name="remarks"></a>Uwagi

Szablon klasy opisuje stały obiekt iteratora do przodu. Koncepcyjnie przechowuje `regex_iterator` obiekt, którego używa do wyszukiwania zgodności wyrażeń regularnych w sekwencji znaków. Wyodrębnia obiekty typu `sub_match<BidIt>` reprezentujące poddopasowania identyfikowane przez wartości indeksu w przechowywanym wektorze `subs` dla każdego dopasowania wyrażenia regularnego.

Wartość indeksu-1 oznacza sekwencję znaków rozpoczynającą się natychmiast po zakończeniu poprzedniego wyrażenia regularnego lub Zaczynając od początku sekwencji znaków, jeśli nie ma żadnego dopasowania do wyrażenia regularnego, i rozszerza do, ale nie uwzględnia pierwszego znaku bieżącego wyrażenia regularnego lub na koniec sekwencji znaków, jeśli nie ma bieżącego dopasowania. Każda inna wartość indeksu `idx` wyznacza zawartość grupy przechwytywania przechowywanej w `it.match[idx]` .

### <a name="members"></a>Elementy członkowskie

|Członek|Wartość domyślna|
|-|-|
|`private regex_iterator<BidIt, Elem, RXtraits> it`||
|`private vector<int> subs`||
|`private int pos`||

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[regex_token_iterator](#regex_token_iterator)|Konstruuje iterator.|

### <a name="typedefs"></a>Typedefs

|Nazwa typu|Opis|
|-|-|
|[difference_type](#difference_type)|Typ różnicy iteratora.|
|[iterator_category](#iterator_category)|Typ kategorii iteratora.|
|[pointer](#pointer)|Typ wskaźnika do dopasowania.|
|[odwoła](#reference)|Typ odwołania do poddopasowania.|
|[regex_type](#regex_type)|Typ wyrażenia regularnego do dopasowania.|
|[value_type](#value_type)|Typ poddopasowania.|

### <a name="operators"></a>Operatory

|Operator|Opis|
|-|-|
|[operator! =](#op_neq)|Porównuje Iteratory pod kątem nierówności.|
|[zakład](#op_star)|Uzyskuje dostęp do wyoznaczonego dopasowania.|
|[operator + +](#op_add_add)|Zwiększa iterator.|
|[operator = =](#op_eq_eq)|Porównuje Iteratory dla równości.|
|[operator — >](#op_arrow)|Uzyskuje dostęp do wyoznaczonego dopasowania.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<regex>

**Przestrzeń nazw:** std

## <a name="example"></a>Przykład

```cpp
#include <regex>
#include <iostream>

typedef std::regex_token_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "aaxaayaaz";
    Myiter::regex_type rx("(a)a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

// show whole match
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefix before match
    next = Myiter(pat, pat + strlen(pat), rx, -1);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show (a) submatch only
    next = Myiter(pat, pat + strlen(pat), rx, 1);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefixes and submatches
    std::vector<int> vec;
    vec.push_back(-1);
    vec.push_back(1);
    next = Myiter(pat, pat + strlen(pat), rx, vec);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefixes and whole matches
    int arr[] = {-1, 0};
    next = Myiter(pat, pat + strlen(pat), rx, arr);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == aa
match == aa
match == aa

match ==
match == x
match == y
match == z

match == a
match == a
match == a

match ==
match == a
match == x
match == a
match == y
match == a
match == z

match ==
match == aa
match == x
match == aa
match == y
match == aa
match == z
```

## <a name="regex_token_iteratordifference_type"></a><a name="difference_type"></a> regex_token_iterator::d ifference_type

Typ różnicy iteratora.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla `std::ptrdiff_t` .

## <a name="regex_token_iteratoriterator_category"></a><a name="iterator_category"></a> regex_token_iterator:: iterator_category

Typ kategorii iteratora.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla `std::forward_iterator_tag` .

## <a name="regex_token_iteratoroperator"></a><a name="op_neq"></a> regex_token_iterator:: operator! =

Porównuje Iteratory pod kątem nierówności.

```cpp
bool operator!=(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
Iterator, do którego ma zostać wykonane porównanie.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca wartość `!(*this == right)` .

## <a name="regex_token_iteratoroperator"></a><a name="op_star"></a> regex_token_iterator:: operator *

Uzyskuje dostęp do wyoznaczonego dopasowania.

```cpp
const sub_match<BidIt>& operator*();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca `sub_match<BidIt>` obiekt reprezentujący grupę przechwytywania identyfikowaną przez wartość indeksu `subs[pos]` .

## <a name="regex_token_iteratoroperator"></a><a name="op_add_add"></a> regex_token_iterator:: operator + +

Zwiększa iterator.

```cpp
regex_token_iterator& operator++();

regex_token_iterator& operator++(int);
```

### <a name="remarks"></a>Uwagi

Jeśli zapisywany iterator `it` jest iteratorem End-of-Sequence, Pierwszy operator ustawia wartość przechowywaną `pos` na wartość (w `subs.size()` ten sposób iterator End-of-Sequence). W przeciwnym razie operator zwiększa wartość przechowywaną `pos` ; Jeśli wynik jest równy wartości, `subs.size()` ustawia wartość przechowywaną `pos` na zero i zwiększa przechowywany iterator `it` . Jeśli zwiększanie składowanego iteratora pozostawia nie równe iteratorowi z końcówką sekwencji, operator nie wykonuje żadnych dalszych operacji. W przeciwnym razie, jeśli koniec poprzedniego dopasowania znajdował się na końcu sekwencji znaków, operator ustawia przechowywaną wartość `pos` do `subs.size()` . W przeciwnym razie operator wielokrotnie zwiększa przechowywaną wartość `pos` do `pos == subs.size()` lub (w związku z tym `subs[pos] == -1` , że następne odwołanie iteratora zwróci ogon sekwencji znaków, jeśli jedna z wartości indeksu wynosi-1). We wszystkich przypadkach operator zwraca obiekt.

Drugi operator wykonuje kopię obiektu, zwiększa obiekt, a następnie zwraca kopię.

## <a name="regex_token_iteratoroperator"></a><a name="op_eq_eq"></a> regex_token_iterator:: operator = =

Porównuje Iteratory dla równości.

```cpp
bool operator==(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parametry

*Kliknij*\
Iterator, do którego ma zostać wykonane porównanie.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca wartość `it == right.it && subs == right.subs && pos == right.pos` .

## <a name="regex_token_iteratoroperator-gt"></a><a name="op_arrow"></a> regex_token_iterator:: operator-&gt;

Uzyskuje dostęp do wyoznaczonego dopasowania.

```cpp
const sub_match<BidIt> * operator->();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca wskaźnik do `sub_match<BidIt>` obiektu reprezentującego grupę przechwytywania identyfikowaną przez wartość indeksu `subs[pos]` .

## <a name="regex_token_iteratorpointer"></a><a name="pointer"></a> regex_token_iterator::p ointer

Typ wskaźnika do dopasowania.

```cpp
typedef sub_match<BidIt> *pointer;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla `sub_match<BidIt>*` , gdzie `BidIt` jest parametrem szablonu.

## <a name="regex_token_iteratorreference"></a><a name="reference"></a> regex_token_iterator:: Reference

Typ odwołania do poddopasowania.

```cpp
typedef sub_match<BidIt>& reference;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla `sub_match<BidIt>&` , gdzie `BidIt` jest parametrem szablonu.

## <a name="regex_token_iteratorregex_token_iterator"></a><a name="regex_token_iterator"></a> regex_token_iterator:: regex_token_iterator

Konstruuje iterator.

```cpp
regex_token_iterator();

regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, int submatch = 0,
    regex_constants::match_flag_type f = regex_constants::match_default);

regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, const vector<int> submatches,
    regex_constants::match_flag_type f = regex_constants::match_default);

template <std::size_t N>
regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, const int (&submatches)[N],
    regex_constants::match_flag_type f = regex_constants::match_default);
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Początek sekwencji do dopasowania.

*ostatniego*\
Koniec sekwencji do dopasowania.

*Eksport*\
Wyrażenie regularne dla dopasowania.

*n*\
Flagi dla dopasowania.

### <a name="remarks"></a>Uwagi

Pierwszy Konstruktor konstruuje iterator końca sekwencji.

Drugi Konstruktor konstruuje obiekt `it` , którego zainicjowano iterator `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)` , do którego przechowywany wektor ma `subs` dokładnie jedną liczbę całkowitą, z wartością `submatch` i której wartość składowana `pos` jest równa zero. Uwaga: obiekt wyniku wyodrębnia poddopasowanie identyfikowane przez wartość indeksu `submatch` dla każdego pomyślnego dopasowania wyrażenia regularnego.

Trzeci Konstruktor konstruuje obiekt `it` , którego zainicjowano iterator `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)` , do którego przechowywany wektor `subs` przechowuje kopię argumentu konstruktora `submatches` , a wartość przechowywana `pos` jest równa zero.

Czwarty Konstruktor konstruuje obiekt, którego składowany iterator `it` jest zainicjowany `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)` , którego przechowywany wektor `subs` przechowuje `N` wartości wskazywane przez argument konstruktora `submatches` , a wartość przechowywana `pos` jest równa zero.

## <a name="regex_token_iteratorregex_type"></a><a name="regex_type"></a> regex_token_iterator:: regex_type

Typ wyrażenia regularnego do dopasowania.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Uwagi

Element typedef jest synonimem dla `basic_regex<Elem, RXtraits>` .

## <a name="regex_token_iteratorvalue_type"></a><a name="value_type"></a> regex_token_iterator:: value_type

Typ poddopasowania.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla `sub_match<BidIt>` , gdzie `BidIt` jest parametrem szablonu.

## <a name="see-also"></a>Zobacz też

[\<regex>](../standard-library/regex.md)\
[Klasa regex_constants](../standard-library/regex-constants-class.md)\
[Klasa regex_error](../standard-library/regex-error-class.md)\
[\<regex> obowiązki](../standard-library/regex-functions.md)\
[Klasa regex_iterator](../standard-library/regex-iterator-class.md)\
[\<regex> zainteresowanych](../standard-library/regex-operators.md)\
[Klasa regex_traits](../standard-library/regex-traits-class.md)\
[\<regex> definicje typów](../standard-library/regex-typedefs.md)

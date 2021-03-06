---
description: Dowiedz się więcej na temat klasy regex_traits
title: regex_traits — Klasa
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_traits
- regex/std::regex_traits::char_type
- regex/std::regex_traits::size_type
- regex/std::regex_traits::string_type
- regex/std::regex_traits::locale_type
- regex/std::regex_traits::char_class_type
- regex/std::regex_traits::length
- regex/std::regex_traits::translate
- regex/std::regex_traits::translate_nocase
- regex/std::regex_traits::transform
- regex/std::regex_traits::transform_primary
- regex/std::regex_traits::lookup_classname
- regex/std::regex_traits::lookup_collatename
- regex/std::regex_traits::isctype
- regex/std::regex_traits::value
- regex/std::regex_traits::imbue
- regex/std::regex_traits::getloc
helpviewer_keywords:
- std::regex_traits [C++]
- std::regex_traits [C++], char_type
- std::regex_traits [C++], size_type
- std::regex_traits [C++], string_type
- std::regex_traits [C++], locale_type
- std::regex_traits [C++], char_class_type
- std::regex_traits [C++], length
- std::regex_traits [C++], translate
- std::regex_traits [C++], translate_nocase
- std::regex_traits [C++], transform
- std::regex_traits [C++], transform_primary
- std::regex_traits [C++], lookup_classname
- std::regex_traits [C++], lookup_collatename
- std::regex_traits [C++], isctype
- std::regex_traits [C++], value
- std::regex_traits [C++], imbue
- std::regex_traits [C++], getloc
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
ms.openlocfilehash: 419e0d242c43c644b6c67c48b0c28b09e96e59b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243812"
---
# <a name="regex_traits-class"></a>regex_traits — Klasa

Opisuje charakterystykę elementów do dopasowania.

## <a name="syntax"></a>Składnia

```cpp
template<class Elem>
class regex_traits
```

## <a name="parameters"></a>Parametry

*Elem*\
Typ elementu znaku do opisania.

## <a name="remarks"></a>Uwagi

Szablon klasy opisuje różne cechy wyrażeń regularnych dla typu *elem*. Klasa szablonu klasy [basic_regex](../standard-library/basic-regex-class.md) używa tych informacji do manipulowania elementami typu *elem*.

Każdy `regex_traits` obiekt zawiera obiekt typu `regex_traits::locale` , który jest używany przez niektóre z jego funkcji składowych. Domyślne ustawienia regionalne to kopia `regex_traits::locale()` . Funkcja członkowska `imbue` zastępuje obiekt ustawień regionalnych, a funkcja członkowska `getloc` zwraca kopię obiektu ustawień regionalnych.

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[regex_traits](#regex_traits)|Konstruuje obiekt.|

### <a name="typedefs"></a>Typedefs

|Nazwa typu|Opis|
|-|-|
|[char_class_type](#char_class_type)|Typ wyznaczania klasy znaków.|
|[char_type](#char_type)|Typ elementu.|
|[locale_type](#locale_type)|Typ przechowywanego obiektu ustawień regionalnych.|
|[size_type](#size_type)|Typ długości sekwencji.|
|[string_type](#string_type)|Typ ciągu elementów.|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[getloc](#getloc)|Zwraca przechowywany obiekt locale.|
|[imbue —](#imbue)|Zmienia przechowywany obiekt locale.|
|[isctype —](#isctype)|Testy dla członkostwa w klasie.|
|[length](#length)|Zwraca długość sekwencji zakończonych znakiem null.|
|[lookup_classname](#lookup_classname)|Mapuje sekwencję do klasy znaków.|
|[lookup_collatename](#lookup_collatename)|Mapuje sekwencję do elementu sortowania.|
|[przekształcania](#transform)|Konwertuje na równoważną uporządkowaną sekwencję.|
|[transform_primary](#transform_primary)|Konwertuje na równoważną sekwencję uporządkowaną bezliterowo.|
|[Przetłumacz](#translate)|Konwertuje na odpowiedni pasujący element.|
|[translate_nocase](#translate_nocase)|Konwertuje do równoważnego elementu pasującego do samego wielkości liter.|
|[wartość](#value)|Konwertuje element na wartość cyfrową.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<regex>

**Przestrzeń nazw:** std

## <a name="example"></a>Przykład

```cpp
// std__regex__regex_traits.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_traits<char> Mytr;
int main()
    {
    Mytr tr;

    Mytr::char_type ch = tr.translate('a');
    std::cout << "translate('a') == 'a' == " << std::boolalpha
        << (ch == 'a') << std::endl;

    std::cout << "nocase 'a' == 'A' == " << std::boolalpha
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))
        << std::endl;

    const char *lbegin = "abc";
    const char *lend = lbegin + strlen(lbegin);
    Mytr::size_type size = tr.length(lbegin);
    std::cout << "length(\"abc\") == " << size <<std::endl;

    Mytr::string_type str = tr.transform(lbegin, lend);
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha
        << (str < "abc") << std::endl;

    const char *ubegin = "ABC";
    const char *uend = ubegin + strlen(ubegin);
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha
        << (tr.transform_primary(ubegin, uend) <
            tr.transform_primary(lbegin, lend))
        << std::endl;

    const char *dig = "digit";
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);
    std::cout << "class digit == d == " << std::boolalpha
        << (cl == tr.lookup_classname(dig, dig + 1))
        << std::endl;

    std::cout << "'3' is digit == " <<std::boolalpha
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))
        << std::endl;

    std::cout << "hex C == " << tr.value('C', 16) << std::endl;

// other members
    str = tr.lookup_collatename(dig, dig + 5);

    Mytr::locale_type loc = tr.getloc();
    tr.imbue(loc);

    return (0);
    }
```

```Output
translate('a') == 'a' == true
nocase 'a' == 'A' == true
length("abc") == 3
transform("abc") < "abc" == false
primary "ABC" < "abc" == false
class digit == d == true
'3' is digit == true
hex C == 12
```

## <a name="regex_traitschar_class_type"></a><a name="char_class_type"></a> regex_traits:: char_class_type

Typ wyznaczania klasy znaków.

```cpp
typedef T8 char_class_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla nieokreślonego typu, który wyznacza klasy znaków. Wartości tego typu można łączyć za pomocą operatora, `|` Aby wyznaczyć klasy znaków, które są Unią klas wyznaczonych przez operandy.

## <a name="regex_traitschar_type"></a><a name="char_type"></a> regex_traits:: char_type

Typ elementu.

```cpp
typedef Elem char_type;
```

### <a name="remarks"></a>Uwagi

Element typedef jest synonimem argumentu szablonu `Elem` .

## <a name="regex_traitsgetloc"></a><a name="getloc"></a> regex_traits:: getloc

Zwraca przechowywany obiekt locale.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca przechowywany `locale` obiekt.

## <a name="regex_traitsimbue"></a><a name="imbue"></a> regex_traits:: imbue —

Zmienia przechowywany obiekt locale.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Parametry

*Loc*\
Obiekt ustawień regionalnych do przechowywania.

### <a name="remarks"></a>Uwagi

Funkcja członkowska kopiuje element *Loc* do przechowywanego `locale` obiektu i zwraca kopię poprzedniej wartości przechowywanego `locale` obiektu.

## <a name="regex_traitsisctype"></a><a name="isctype"></a> regex_traits:: isctype —

Testy dla członkostwa w klasie.

```cpp
bool isctype(char_type ch, char_class_type cls) const;
```

### <a name="parameters"></a>Parametry

*ch*\
Element do przetestowania.

*ze*\
Klasy do przetestowania.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca wartość true tylko wtedy, gdy znak *ch* jest w klasie znakowej oznaczonej przez *CLS*.

## <a name="regex_traitslength"></a><a name="length"></a> regex_traits:: length

Zwraca długość sekwencji zakończonych znakiem null.

```cpp
static size_type length(const char_type *str);
```

### <a name="parameters"></a>Parametry

*str*\
Sekwencja zakończona wartością null.

### <a name="remarks"></a>Uwagi

Statyczna funkcja członkowska zwraca wartość `std::char_traits<char_type>::length(str)` .

## <a name="regex_traitslocale_type"></a><a name="locale_type"></a> regex_traits:: locale_type

Typ przechowywanego obiektu ustawień regionalnych.

```cpp
typedef T7 locale_type;
```

### <a name="remarks"></a>Uwagi

Element typedef jest synonimem typu, który hermetyzuje ustawienia regionalne. W specjalizacjach `regex_traits<char>` i `regex_traits<wchar_t>` jest synonimem dla `std::locale` .

## <a name="regex_traitslookup_classname"></a><a name="lookup_classname"></a> regex_traits:: lookup_classname

Mapuje sekwencję do klasy znaków.

```cpp
template <class FwdIt>
char_class_type lookup_classname(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Początek sekwencji do wyszukania.

*ostatniego*\
Koniec sekwencji do wyszukania.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca wartość, która wyznacza klasę znaku o nazwie w sekwencji znaków wskazywanej przez argumenty. Wartość nie jest zależna od wielkości liter w sekwencji.

Specjalizacja rozpoznaje nazwiska,,,,,,,,,, `regex_traits<char>` `"d"` `"s"` `"w"` `"alnum"` `"alpha"` `"blank"` `"cntrl"` `"digit"` `"graph"` `"lower"` `"print"` ,, `"punct"` , `"space"` `"upper"` i `"xdigit"` , bez uwzględniania wielkości liter.

Specjalizacja rozpoznaje nazwiska,,,,,,,,,, `regex_traits<wchar_t>` `L"d"` `L"s"` `L"w"` `L"alnum"` `L"alpha"` `L"blank"` `L"cntrl"` `L"digit"` `L"graph"` `L"lower"` `L"print"` ,, `L"punct"` , `L"space"` `L"upper"` i `L"xdigit"` , bez uwzględniania wielkości liter.

## <a name="regex_traitslookup_collatename"></a><a name="lookup_collatename"></a> regex_traits:: lookup_collatename

Mapuje sekwencję do elementu sortowania.

```cpp
template <class FwdIt>
string_type lookup_collatename(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Początek sekwencji do wyszukania.

*ostatniego*\
Koniec sekwencji do wyszukania.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca obiekt String zawierający element sortowania odpowiadający sekwencji `[first, last)` lub pusty ciąg, jeśli sekwencja nie jest prawidłowym elementem sortowania.

## <a name="regex_traitsregex_traits"></a><a name="regex_traits"></a> regex_traits:: regex_traits

Konstruuje obiekt.

```cpp
regex_traits();
```

### <a name="remarks"></a>Uwagi

Konstruktor konstruuje obiekt, którego przechowywany `locale` obiekt jest zainicjowany do domyślnych ustawień regionalnych.

## <a name="regex_traitssize_type"></a><a name="size_type"></a> regex_traits:: size_type

Typ długości sekwencji.

```cpp
typedef T6 size_type;
```

### <a name="remarks"></a>Uwagi

Element typedef jest synonimem dla niepodpisanego typu całkowitego. W specjalizacjach `regex_traits<char>` i `regex_traits<wchar_t>` jest synonimem dla `std::size_t` .

Element typedef jest synonimem dla `std::size_t` .

## <a name="regex_traitsstring_type"></a><a name="string_type"></a> regex_traits:: string_type

Typ ciągu elementów.

```cpp
typedef basic_string<Elem> string_type;
```

### <a name="remarks"></a>Uwagi

Element typedef jest synonimem dla `basic_string<Elem>` .

## <a name="regex_traitstransform"></a><a name="transform"></a> regex_traits:: Transform

Konwertuje na równoważną uporządkowaną sekwencję.

```cpp
template <class FwdIt>
string_type transform(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Początek sekwencji do przekształcenia.

*ostatniego*\
Koniec sekwencji do przekształcenia.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca ciąg wygenerowany przy użyciu reguły transformacji, która zależy od przechowywanego `locale` obiektu. Dla dwóch sekwencji znaków wyznaczono przez zakresy iteratora `[first1, last1)` i `[first2, last2)` , `transform(first1, last1) < transform(first2, last2)` Jeśli sekwencja znaków oznaczona przez zakres iteratora jest `[first1, last1)` sortowana przed sekwencją znaków wydaną przez zakres iteratora `[first2, last2)` .

## <a name="regex_traitstransform_primary"></a><a name="transform_primary"></a> regex_traits:: transform_primary

Konwertuje na równoważną sekwencję uporządkowaną bezliterowo.

```cpp
template <class FwdIt>
string_type transform_primary(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Początek sekwencji do przekształcenia.

*ostatniego*\
Koniec sekwencji do przekształcenia.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca ciąg wygenerowany przy użyciu reguły transformacji, która zależy od przechowywanego `locale` obiektu. Dla dwóch sekwencji znaków wyznacznych przez zakresy iteratora `[first1, last1)` i `[first2, last2)` , `transform_primary(first1, last1) < transform_primary(first2, last2)` Jeśli sekwencja znaków oznaczona przez zakres iteratora jest `[first1, last1)` sortowana przed sekwencją znaków wydaną przez zakres iteratora `[first2, last2)` bez uwzględniania wielkości liter lub akcentów.

## <a name="regex_traitstranslate"></a><a name="translate"></a> regex_traits:: tłumaczyć

Konwertuje na odpowiedni pasujący element.

```cpp
char_type translate(char_type ch) const;
```

### <a name="parameters"></a>Parametry

*ch*\
Element do przekonwertowania.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca znak generowany przy użyciu reguły transformacji, która zależy od przechowywanego `locale` obiektu. Dla dwóch `char_type` obiektów `ch1` i `ch2` , tylko wtedy, gdy `translate(ch1) == translate(ch2)` `ch1` i `ch2` powinny być zgodne, gdy występuje w definicji wyrażenia regularnego, a drugi występuje w odpowiedniej pozycji w sekwencji docelowej dla dopasowania z uwzględnieniem ustawień regionalnych.

## <a name="regex_traitstranslate_nocase"></a><a name="translate_nocase"></a> regex_traits:: translate_nocase

Konwertuje do równoważnego elementu pasującego do samego wielkości liter.

```cpp
char_type translate_nocase(char_type ch) const;
```

### <a name="parameters"></a>Parametry

*ch*\
Element do przekonwertowania.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca znak generowany przy użyciu reguły transformacji, która zależy od przechowywanego `locale` obiektu. Dla dwóch `char_type` obiektów `ch1` i `ch2` , tylko wtedy, gdy `translate_nocase(ch1) == translate_nocase(ch2)` `ch1` i `ch2` powinny być zgodne, gdy występuje w definicji wyrażenia regularnego, a drugi występuje w odpowiedniej pozycji w sekwencji docelowej dla dopasowania bez uwzględniania wielkości liter.

## <a name="regex_traitsvalue"></a><a name="value"></a> regex_traits:: value

Konwertuje element na wartość cyfrową.

```cpp
int value(Elem ch, int radix) const;
```

### <a name="parameters"></a>Parametry

*ch*\
Element do przekonwertowania.

*podstawy*\
Baza arytmetyczna, która ma zostać użyta.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca wartość reprezentowaną przez znak *ch* w podstawowym *podstawy* lub-1 Jeśli *ch* nie jest prawidłową cyfrą w podstawowym *podstawy*. Funkcja będzie wywoływana tylko z argumentem *podstawy* o wartości 8, 10 lub 16.

## <a name="see-also"></a>Zobacz też

[\<regex>](../standard-library/regex.md)\
[Klasa regex_constants](../standard-library/regex-constants-class.md)\
[Klasa regex_error](../standard-library/regex-error-class.md)\
[\<regex> obowiązki](../standard-library/regex-functions.md)\
[Klasa regex_iterator](../standard-library/regex-iterator-class.md)\
[\<regex> zainteresowanych](../standard-library/regex-operators.md)\
[Klasa regex_token_iterator](../standard-library/regex-token-iterator-class.md)\
[\<regex> definicje typów](../standard-library/regex-typedefs.md)\
[\<char>klasa regex_traits](../standard-library/regex-traits-char-class.md)\
[\<wchar_t>klasa regex_traits](../standard-library/regex-traits-wchar-t-class.md)

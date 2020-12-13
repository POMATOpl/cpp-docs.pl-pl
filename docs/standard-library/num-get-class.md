---
description: Dowiedz się więcej na temat klasy num_get
title: num_get — Klasa
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::num_get
- locale/std::num_get::char_type
- locale/std::num_get::iter_type
- locale/std::num_get::do_get
- locale/std::num_get::get
helpviewer_keywords:
- std::num_get [C++]
- std::num_get [C++], char_type
- std::num_get [C++], iter_type
- std::num_get [C++], do_get
- std::num_get [C++], get
ms.assetid: 9933735d-3918-4b17-abad-5fca2adc62d7
ms.openlocfilehash: 0236aac2e7c7859f966430bd276b4dffc42820b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338086"
---
# <a name="num_get-class"></a>num_get — Klasa

Szablon klasy, który opisuje obiekt, który może stanowić zestaw reguł ustawień regionalnych w celu kontroli konwersji sekwencji typu `CharType` na wartości liczbowe.

## <a name="syntax"></a>Składnia

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class num_get : public locale::facet;
```

### <a name="parameters"></a>Parametry

*CharType*\
Typ używany w programie do kodowania znaków w ustawieniach regionalnych.

*InputIterator*\
Typ iteratora, z którego liczbowe funkcje get odczytują swoje dane wejściowe.

## <a name="remarks"></a>Uwagi

Podobnie jak w przypadku dowolnego zestawu reguł ustawień regionalnych, identyfikator obiektu statycznego ma początkową przechowywaną wartość zero. Pierwsza próba uzyskania dostępu do przechowywanej wartości przechowuje unikatową wartość dodatnią w **identyfikatorze.**

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[num_get](#num_get)|Konstruktor dla obiektów typu `num_get` , które są używane do wyodrębniania wartości liczbowych z sekwencji.|

### <a name="typedefs"></a>Typedefs

|Nazwa typu|Opis|
|-|-|
|[char_type](#char_type)|Typ opisujący znak używany przez ustawienie regionalne.|
|[iter_type](#iter_type)|Typ, który opisuje iterator danych wejściowych.|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[do_get](#do_get)|Funkcja wirtualna wywoływana w celu wyodrębniania wartości liczbowej lub logicznej z sekwencji znaków.|
|[get](#get)|Wyodrębnia wartość liczbową lub logiczną z sekwencji znaków.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<locale>

**Przestrzeń nazw:** std

## <a name="num_getchar_type"></a><a name="char_type"></a> num_get:: char_type

Typ opisujący znak używany przez ustawienie regionalne.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla parametru szablonu **CharType**.

## <a name="num_getdo_get"></a><a name="do_get"></a> num_get::d o_get

Funkcja wirtualna wywoływana w celu wyodrębniania wartości liczbowej lub logicznej z sekwencji znaków.

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Początek zakresu znaków, z którego ma zostać odczytana liczba.

*ostatniego*\
Koniec zakresu znaków, z którego ma zostać odczytana liczba.

*iosbase*\
[Ios_base](../standard-library/ios-base-class.md) którego flagi są używane przez konwersję.

*Państwu*\
Stan, do którego zostanie dodany failbit (zobacz [ios_base:: iostate](../standard-library/ios-base-class.md#iostate)) w przypadku niepowodzenia.

*użyte*\
Wartość, która została odczytana.

### <a name="return-value"></a>Wartość zwracana

Iterator po odczytaniu wartości.

### <a name="remarks"></a>Uwagi

Pierwsza wirtualna chroniona funkcja członkowska,

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;
```

dopasowuje elementy sekwencyjne zaczynające się na *pierwszy* dzień w sekwencji, `[first, last)` dopóki nie rozpoznano kompletnego, niepustego pola wejściowego liczby całkowitej. Jeśli to się powiedzie, konwertuje to pole na jego równoważną wartość jako typ **`long`** i zapisuje wynik w wartości *Val*. Zwraca iterator wyznaczający pierwszy element poza liczbowe pole wejściowe. W przeciwnym razie funkcja przechowuje Nothing w wartości *Val* i ustawia `ios_base::failbit` w `state` . Zwraca iterator wyznaczający pierwszy element poza dowolnym prefiksem prawidłowego pola wejściowego Integer. W obu przypadkach, jeśli wartość zwracana jest równa `last` , funkcja ustawia `ios_base::eofbit` w `state` .

Pole danych wejściowych Integer jest konwertowane na te same reguły, które są używane przez funkcje skanowania do dopasowywania i konwertowania serii **`char`** elementów z pliku. (Każdy taki **`char`** element jest założono, że mapuje się do równoważnego elementu typu `Elem` przez proste, jeden do jednego, mapowanie.) Zgodna specyfikacja konwersji skanowania jest określana w następujący sposób:

Jeśli `iosbase.` [ios_base:: flage](../standard-library/ios-base-class.md#flags) `() & ios_base::basefield == ios_base::` [KTZ](../standard-library/ios-functions.md#oct), specyfikacja konwersji to `lo` .

W przypadku `iosbase.flags() & ios_base::basefield == ios_base::` [znaków szesnastkowych](../standard-library/ios-functions.md#hex)specyfikacja konwersji to `lx` .

Jeśli `iosbase.flags() & ios_base::basefield == 0` jest, specyfikacja konwersji to `li` .

W przeciwnym razie specyfikacja konwersji to `ld` .

Format pola wejściowego Integer jest bardziej określony przez zestaw [reguł ustawień regionalnych](../standard-library/locale-class.md#facet_class) `fac` zwrócony przez wywołanie [use_facet](../standard-library/locale-functions.md#use_facet) `<` [numpunct](../standard-library/numpunct-class.md) `<Elem>(iosbase.` [ios_base:: getloc](../standard-library/ios-base-class.md#getloc) `())` . W szczególności:

`fac.`[numpunct:: Grouping](../standard-library/numpunct-class.md#grouping) `()` Określa sposób grupowania cyfr na lewo od dowolnego punktu dziesiętnego.

`fac.`[numpunct:: thousands_sep](../standard-library/numpunct-class.md#thousands_sep) `()` Określa sekwencję oddzielającą grupy cyfr po lewej stronie dowolnego miejsca dziesiętnego.

Jeśli `fac.thousands_sep()` w polu numeryczne dane wejściowe nie występują wystąpienia wystąpień, nie zostanie nałożone ograniczenie grupowania. W przeciwnym razie wszystkie ograniczenia grupowania narzucone przez `fac.grouping()` są wymuszane, a separatory zostaną usunięte przed wykonaniem konwersji skanowania.

Czwarta chroniona funkcja wirtualna elementu członkowskiego:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

zachowuje się tak samo jak pierwszy, z tą różnicą, że zastępuje specyfikację konwersji `ld` z `lu` . W przypadku pomyślnego przekonwertowania pola dane wejściowe na wartość typu **`unsigned long`** i zapisu wartości w *Val*.

Piąta chroniona funkcja wirtualna elementu członkowskiego:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;
```

zachowuje się tak samo jak pierwszy, z tą różnicą, że zastępuje specyfikację konwersji `ld` z `lld` . W przypadku pomyślnego przekonwertowania pola dane wejściowe na wartość typu **`long long`** i zapisu wartości w *Val*.

Szósta chroniona funkcja wirtualna elementu członkowskiego:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;
```

zachowuje się tak samo jak pierwszy, z tą różnicą, że zastępuje specyfikację konwersji `ld` z `llu` . W przypadku pomyślnego przekonwertowania pola dane wejściowe na wartość typu **`unsigned long long`** i zapisu wartości w *Val*.

Siódma wirtualna chroniona funkcja członkowska:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;
```

zachowuje się tak samo jak pierwszy, z tą różnicą, że przedsięwzięciach się na wypełnienie kompletnego, niepustego pola wejściowego zmiennoprzecinkowego. `fac.`[numpunct::d ecimal_point](../standard-library/numpunct-class.md#decimal_point) `()` Określa sekwencję oddzielające cyfry całkowite od cyfr ułamkowych. Odpowiednik specyfikatora przeliczeniowego skanowania to `lf` .

Ósma wirtualna chroniona funkcja członkowska:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

zachowuje się tak samo jak pierwszy, z tą różnicą, że przedsięwzięciach się na wypełnienie kompletnego, niepustego pola wejściowego zmiennoprzecinkowego. `fac.`[numpunct::d ecimal_point](../standard-library/numpunct-class.md#decimal_point) `()` Określa sekwencję oddzielające cyfry całkowite od cyfr ułamkowych. Odpowiednik specyfikatora przeliczeniowego skanowania to `lf` .

Dziewiąta chroniona funkcja wirtualna elementu członkowskiego:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

zachowuje się tak samo, jak osiem, z tą różnicą, że równoważnego specyfikatora konwersji skanowania jest `Lf` .

Dziesiąta chroniona funkcja wirtualna elementu członkowskiego:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

zachowuje się tak samo, z tą różnicą, że równoważnego specyfikatora konwersji skanowania jest `p` .

Ostatnia (jedenasta) wirtualna funkcja chronionego elementu członkowskiego:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

zachowuje się tak samo jak pierwszy, z tą różnicą, że przedsięwzięciach się na wypełnienie kompletnego, niepustego pola wejściowego Boolean. W przypadku pomyślnego przeprowadzenia konwersji pola danych wejściowych Boolean na wartość typu **`bool`** i zapisuje tę wartość w *Val*.

Pole danych wejściowych Boolean przyjmuje jeden z dwóch form. Jeśli `iosbase.flags() & ios_base::` [boolalpha](../standard-library/ios-functions.md#boolalpha) ma wartość false, jest taka sama jak pole danych wejściowych Integer, z tą różnicą, że przekonwertowana wartość musi być równa 0 (dla wartości false) lub 1 (dla prawdy). W przeciwnym razie sekwencja musi być zgodna z `fac.` [numpunct:: falsename](../standard-library/numpunct-class.md#falsename) `()` (dla false) lub `fac.` [numpunct:: TrueName](../standard-library/numpunct-class.md#truename) `()` (dla prawdy).

### <a name="example"></a>Przykład

Zobacz przykład dla [Get](#get), gdzie wirtualna funkcja członkowska jest wywoływana przez `do_get` .

## <a name="num_getget"></a><a name="get"></a> num_get:: Get

Wyodrębnia wartość liczbową lub logiczną z sekwencji znaków.

```cpp
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Początek zakresu znaków, z którego ma zostać odczytana liczba.

*ostatniego*\
Koniec zakresu znaków, z którego ma zostać odczytana liczba.

*iosbase*\
[Ios_base](../standard-library/ios-base-class.md) którego flagi są używane przez konwersję.

*Państwu*\
Stan, do którego zostanie dodany failbit (zobacz [ios_base:: iostate](../standard-library/ios-base-class.md#iostate)) w przypadku niepowodzenia.

*użyte*\
Wartość, która została odczytana.

### <a name="return-value"></a>Wartość zwracana

Iterator po odczytaniu wartości.

### <a name="remarks"></a>Uwagi

Wszystkie funkcje członkowskie zwracają [do_get](#do_get) `( first, last, iosbase, state, val)` .

Pierwsza wirtualna chroniona funkcja członkowska próbuje dopasować elementy sekwencyjne zaczynające się od pierwszej w sekwencji [ `first` , `last` ), dopóki nie rozpoznano kompletnego, niepustego pola wejściowego. Jeśli to się powiedzie, konwertuje to pole na jego równoważną wartość jako typ **`long`** i zapisuje wynik w wartości *Val*. Zwraca iterator wyznaczający pierwszy element poza liczbowe pole wejściowe. W przeciwnym razie funkcja przechowuje Nothing w wartości *Val* i ustawia `ios_base::failbit` w *stanie*. Zwraca iterator wyznaczający pierwszy element poza dowolnym prefiksem prawidłowego pola wejściowego Integer. W obu przypadkach, jeśli wartość zwracana jest równa *Last*, funkcja ustawia `ios_base::eofbit` w *stanie*.

Pole danych wejściowych Integer jest konwertowane na te same reguły, które są używane przez funkcje skanowania do dopasowywania i konwertowania serii **`char`** elementów z pliku. Każdy taki **`char`** element jest założono, że mapuje do równoważnego elementu typu `CharType` przez proste, jedno-do-jednego mapowania. Zgodna specyfikacja konwersji skanowania jest określana w następujący sposób:

- Jeśli `iosbase.` [flagami](../standard-library/ios-base-class.md#flags) `& ios_base::basefield == ios_base::` jest[OCT](../standard-library/ios-functions.md#oct), specyfikacja konwersji to `lo` .

- W przypadku `iosbase.flags & ios_base::basefield == ios_base::` [znaków szesnastkowych](../standard-library/ios-functions.md#hex)specyfikacja konwersji to `lx` .

- Jeśli `iosbase.flags & ios_base::basefield == 0` jest, specyfikacja konwersji to `li` .

- W przeciwnym razie specyfikacja konwersji to `ld` .

Format pola wejściowego Integer jest bardziej określony przez zestaw [reguł ustawień regionalnych](../standard-library/locale-class.md#facet_class) `fac` zwrócony przez wywołanie [use_facet](../standard-library/locale-functions.md#use_facet) `<` [`numpunct`](../standard-library/numpunct-class.md) `<Elem>(iosbase.` [getloc](../standard-library/ios-base-class.md#getloc) `())` . W szczególności:

- `fac.`[grupowanie](../standard-library/numpunct-class.md#grouping) określa sposób grupowania cyfr na lewo od dowolnego punktu dziesiętnego.

- `fac.`[thousands_sep](../standard-library/numpunct-class.md#thousands_sep) Określa sekwencję oddziela grupy cyfr po lewej stronie dowolnego miejsca dziesiętnego.

Jeśli `fac.thousands_sep` w polu numeryczne dane wejściowe nie występują wystąpienia wystąpień, nie zostanie nałożone ograniczenie grupowania. W przeciwnym razie wszystkie ograniczenia grupowania narzucone przez program `fac.grouping` są wymuszane, a separatory zostaną usunięte przed wykonaniem konwersji skanowania.

Druga wirtualna chroniona funkcja członkowska:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

zachowuje się tak samo jak pierwszy, z tą różnicą, że zastępuje specyfikację konwersji `ld` z `lu` . Jeśli to się powiedzie, konwertuje pole liczbowe dane wejściowe na wartość typu **`unsigned long`** i zapisuje tę wartość w *Val*.

Trzecia wirtualna chroniona funkcja członkowska:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

zachowuje się tak samo jak pierwszy, z tą różnicą, że próbuje dopasować kompletne, niepuste pole wejściowe zmiennoprzecinkowe. `fac.`[decimal_point](../standard-library/numpunct-class.md#decimal_point) Określa sekwencję oddzielające cyfry całkowite od cyfr ułamkowych. Odpowiednik specyfikatora przeliczeniowego skanowania to `lf` .

Czwarta chroniona funkcja wirtualna elementu członkowskiego:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

zachowuje się tak samo trzeci, z tą różnicą, że równoważny specyfikator przeliczeniowego skanowania `Lf` .

Piąta chroniona funkcja wirtualna elementu członkowskiego:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

zachowuje się tak samo, z tą różnicą, że równoważnego specyfikatora konwersji skanowania jest `p` .

Szósta chroniona funkcja wirtualna elementu członkowskiego:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

zachowuje się tak samo jak pierwszy, z tą różnicą, że próbuje dopasować kompletne, niepuste pole wejściowej wartości logicznej. W przypadku pomyślnego przeprowadzenia konwersji pola danych wejściowych Boolean na wartość typu **`bool`** i zapisuje tę wartość w *Val*.

Pole danych wejściowych Boolean przyjmuje jeden z dwóch form. Jeśli `iosbase.flags & ios_base::` [boolalpha](../standard-library/ios-functions.md#boolalpha) jest **`false`** , jest taka sama jak pole danych wejściowych Integer, z tą różnicą, że przekonwertowana wartość musi być równa 0 (dla **`false`** ) lub 1 (dla **`true`** ). W przeciwnym razie sekwencja musi być zgodna z wartością `fac.` [falsename](../standard-library/numpunct-class.md#falsename) (dla **`false`** ) lub `fac.` [TrueName](../standard-library/numpunct-class.md#truename) (for **`true`** ).

### <a name="example"></a>Przykład

```cpp
// num_get_get.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   basic_stringstream<char> psz, psz2;
   psz << "-1000,56";

   ios_base::iostate st = 0;
   long double fVal;
   cout << use_facet <numpunct <char> >(loc).thousands_sep( ) << endl;

   psz.imbue( loc );
   use_facet <num_get <char> >
   (loc).get( basic_istream<char>::_Iter( psz.rdbuf( ) ),
           basic_istream<char>::_Iter(0), psz, st, fVal );

   if ( st & ios_base::failbit )
      cout << "money_get( ) FAILED" << endl;
   else
      cout << "money_get( ) = " << fVal << endl;
}
```

## <a name="num_getiter_type"></a><a name="iter_type"></a> num_get:: iter_type

Typ, który opisuje iterator danych wejściowych.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla parametru szablonu `InputIterator` .

## <a name="num_getnum_get"></a><a name="num_get"></a> num_get:: num_get

Konstruktor dla obiektów typu `num_get` , które są używane do wyodrębniania wartości liczbowych z sekwencji.

```cpp
explicit num_get(size_t refs = 0);
```

### <a name="parameters"></a>Parametry

*System*\
Wartość całkowita służąca do określania typu zarządzania pamięcią dla obiektu.

### <a name="remarks"></a>Uwagi

Możliwe wartości parametru *ReFS* i ich znaczenie są następujące:

- 0: okres istnienia obiektu jest zarządzany przez elementy lokalne, które go zawierają.

- 1: okres istnienia obiektu musi być zarządzany ręcznie.

- \> 1: te wartości nie są zdefiniowane.

Nie są możliwe żadne bezpośrednie przykłady, ponieważ destruktor jest chroniony.

Konstruktor inicjuje swój obiekt podstawowy z zestawem `locale::` [reguł](../standard-library/locale-class.md#facet_class) `(refs)` .

## <a name="see-also"></a>Zobacz też

[\<locale>](../standard-library/locale.md)\
[facet — Klasa](../standard-library/locale-class.md#facet_class)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

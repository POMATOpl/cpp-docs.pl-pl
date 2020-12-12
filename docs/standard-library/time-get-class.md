---
description: Dowiedz się więcej na temat klasy time_get
title: time_get — Klasa
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get
- locale/std::time_get::char_type
- locale/std::time_get::iter_type
- locale/std::time_get::date_order
- locale/std::time_get::do_date_order
- locale/std::time_get::do_get
- locale/std::time_get::do_get_date
- locale/std::time_get::do_get_monthname
- locale/std::time_get::do_get_time
- locale/std::time_get::do_get_weekday
- locale/std::time_get::do_get_year
- locale/std::time_get::get
- locale/std::time_get::get_date
- locale/std::time_get::get_monthname
- locale/std::time_get::get_time
- locale/std::time_get::get_weekday
- locale/std::time_get::get_year
helpviewer_keywords:
- std::time_get [C++]
- std::time_get [C++], char_type
- std::time_get [C++], iter_type
- std::time_get [C++], date_order
- std::time_get [C++], do_date_order
- std::time_get [C++], do_get
- std::time_get [C++], do_get_date
- std::time_get [C++], do_get_monthname
- std::time_get [C++], do_get_time
- std::time_get [C++], do_get_weekday
- std::time_get [C++], do_get_year
- std::time_get [C++], get
- std::time_get [C++], get_date
- std::time_get [C++], get_monthname
- std::time_get [C++], get_time
- std::time_get [C++], get_weekday
- std::time_get [C++], get_year
ms.assetid: 869d5f5b-dbab-4628-8333-bdea7e272023
ms.openlocfilehash: 079929d66ceb124fbceb1a908fbe9a868c446471
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167295"
---
# <a name="time_get-class"></a>time_get — Klasa

Szablon klasy opisuje obiekt, który może być używany jako zestaw reguł ustawień regionalnych w celu kontrolowania konwersji sekwencji typów `CharType` do wartości czasu.

## <a name="syntax"></a>Składnia

```cpp
template <class CharType,
    class InputIterator = istreambuf_iterator<CharType>>
class time_get : public time_base;
```

### <a name="parameters"></a>Parametry

*CharType*\
Typ używany w programie do kodowania znaków.

*InputIterator*\
Iterator, z którego są odczytywane wartości czasu.

## <a name="remarks"></a>Uwagi

Podobnie jak w przypadku dowolnego zestawu reguł ustawień regionalnych, identyfikator obiektu statycznego ma początkową przechowywaną wartość zero. Pierwsza próba uzyskania dostępu do przechowywanej wartości przechowuje unikatową wartość dodatnią w **identyfikatorze.**

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[time_get](#time_get)|Konstruktor dla obiektów typu `time_get` .|

### <a name="typedefs"></a>Typedefs

|Nazwa typu|Opis|
|-|-|
|[char_type](#char_type)|Typ opisujący znak używany przez ustawienie regionalne.|
|[iter_type](#iter_type)|Typ, który opisuje iterator danych wejściowych.|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[date_order](#date_order)|Zwraca kolejność dat używaną przez zestaw reguł.|
|[do_date_order](#do_date_order)|Chroniona funkcja wirtualna elementu członkowskiego, wywoływana, aby zwrócić kolejność dat używaną przez zestaw reguł.|
|[do_get](#do_get)|Odczytuje i konwertuje dane znakowe na wartość czasu.|
|[do_get_date](#do_get_date)|Chroniona funkcja wirtualna elementu członkowskiego, która jest wywoływana, aby przeanalizować ciąg jako datę wygenerowaną przez `x` specyfikator dla `strftime` .|
|[do_get_monthname](#do_get_monthname)|Chroniona funkcja wirtualna elementu członkowskiego, która jest wywoływana, aby przeanalizować ciąg jako nazwę miesiąca.|
|[do_get_time](#do_get_time)|Chroniona funkcja wirtualna elementu członkowskiego, która jest wywoływana, aby przeanalizować ciąg jako datę wygenerowaną przez `X` specyfikator dla `strftime` .|
|[do_get_weekday](#do_get_weekday)|Chroniona funkcja wirtualna elementu członkowskiego, która jest wywoływana, aby przeanalizować ciąg jako nazwę dnia tygodnia.|
|[do_get_year](#do_get_year)|Chroniona funkcja wirtualna elementu członkowskiego, która jest wywoływana, aby przeanalizować ciąg jako nazwę roku.|
|[get](#get)|Odczytuje ze źródła danych znakowych i konwertuje te dane na czas, który jest przechowywany w strukturze czasu.|
|[get_date](#get_date)|Analizuje ciąg jako datę wygenerowaną przez `x` specyfikator dla elementu `strftime` .|
|[get_monthname](#get_monthname)|Analizuje ciąg jako nazwę miesiąca.|
|[get_time](#get_time)|Analizuje ciąg jako datę wygenerowaną przez `X` specyfikator dla elementu `strftime` .|
|[get_weekday](#get_weekday)|Analizuje ciąg jako nazwę dnia tygodnia.|
|[get_year](#get_year)|Analizuje ciąg jako nazwę roku.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<locale>

**Przestrzeń nazw:** std

## <a name="time_getchar_type"></a><a name="char_type"></a> time_get:: char_type

Typ opisujący znak używany przez ustawienie regionalne.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla parametru szablonu **CharType**.

## <a name="time_getdate_order"></a><a name="date_order"></a> time_get::d ate_order

Zwraca kolejność dat używaną przez zestaw reguł.

```cpp
dateorder date_order() const;
```

### <a name="return-value"></a>Wartość zwracana

Kolejność dat używana przez zestaw reguł.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca [do_date_order](#do_date_order).

### <a name="example"></a>Przykład

```cpp
// time_get_date_order.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
void po( char *p )
{
   locale loc( p );

   time_get <char>::dateorder order = use_facet <time_get <char> >( loc ).date_order ( );
   cout << loc.name( );
   switch (order){
      case time_base::dmy: cout << "(day, month, year)" << endl;
      break;
      case time_base::mdy: cout << "(month, day, year)" << endl;
      break;
      case time_base::ydm: cout << "(year, day, month)" << endl;
      break;
      case time_base::ymd: cout << "(year, month, day)"<< endl;
      break;
      case time_base::no_order: cout << "(no_order)"<< endl;
      break;
   }
}

int main( )
{
   po( "C" );
   po( "german" );
   po( "English_Britain" );
}
```

```Output
C(month, day, year)
German_Germany.1252(day, month, year)
English_United Kingdom.1252(day, month, year)
```

## <a name="time_getdo_date_order"></a><a name="do_date_order"></a> time_get::d o_date_order

Chroniona funkcja wirtualna elementu członkowskiego, wywoływana, aby zwrócić kolejność dat używaną przez zestaw reguł.

```cpp
virtual dateorder do_date_order() const;
```

### <a name="return-value"></a>Wartość zwracana

Kolejność dat używana przez zestaw reguł.

### <a name="remarks"></a>Uwagi

Wirtualna funkcja chroniona składowa zwraca wartość typu **time_base::d ateorder**, która opisuje kolejność, w jakiej składniki daty są dopasowane przez [do_get_date](#do_get_date). W tej implementacji wartość jest **time_base:: MDR**, odpowiadającą dacie formularza 2 grudnia 1979.

### <a name="example"></a>Przykład

Zapoznaj się z przykładem dla [date_order](#date_order), które wywołuje `do_date_order` .

## <a name="time_getdo_get"></a><a name="do_get"></a> time_get::d o_get

Odczytuje i konwertuje dane znakowe na wartość czasu. Akceptuje jeden specyfikator konwersji i modyfikator.

```cpp
virtual iter_type
    do_get(
iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm,
    char fmt,
    char mod) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych, który wskazuje początek sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych, który wskazuje koniec sekwencji.

*iosbase*\
Obiekt strumienia.

*Państwu*\
Pole w iosbase, gdzie odpowiednie elementy maski bitowej są ustawione tak, aby wskazywały błędy.

*ptm*\
Wskaźnik do struktury czasu, w którym ma być przechowywany czas.

*FMT*\
Znak specyfikatora konwersji.

*Funkcja*\
Opcjonalny znak modyfikatora.

### <a name="return-value"></a>Wartość zwracana

Zwraca iterator, który wyznacza pierwszy nieprzekonwertowany element. Błędy konwersji są ustawiane `ios_base::failbit` w `state` i zwracane *jako pierwsze*.

### <a name="remarks"></a>Uwagi

Wirtualna funkcja członkowska konwertuje i pomija jeden lub więcej elementów wejściowych z zakresu [ `first` ,), `last` Aby określić wartości przechowywane w jednym lub większej liczbie elementów członkowskich `*pt` . Błędy konwersji są ustawiane `ios_base::failbit` w `state` i zwracane *jako pierwsze*. W przeciwnym razie funkcja zwraca iterator wyznaczający pierwszy nieprzekonwertowany element.

Specyfikatory konwersji są następujące:

`'a'` lub `'A'` --zachowuje się tak samo jak [time_get:: get_weekday](#get_weekday).

`'b'`, `'B'` , lub `'h'` --zachowuje się tak samo jak [time_get:: get_monthname](#get_monthname).

`'c'` --zachowuje się tak samo jak `"%b %d %H : %M : %S %Y"` .

`'C'` --konwertuje pole wejściowe dziesiętne z zakresu [0, 99] na wartość `val` i zapisuje `val * 100 - 1900` w `pt-&tm_year` .

`'d'` lub `'e'` — konwertuje dziesiętne pole wejściowe z zakresu [1, 31] i zapisuje jego wartość w `pt-&tm_mday` .

`'D'` --zachowuje się tak samo jak `"%m / %d / %y"` .

`'H'` --konwertuje pole wejściowe dziesiętne w zakresie [0, 23] i zapisuje jego wartość w `pt-&tm_hour` .

`'I'` --konwertuje pole wejściowe dziesiętne z zakresu [0, 11] i zapisuje jego wartość w `pt-&tm_hour` .

`'j'` --konwertuje pole wejściowe dziesiętne z zakresu [1, 366] i zapisuje jego wartość w `pt-&tm_yday` .

`'m'` --Konwertuje dziesiętne pole wejściowe z zakresu [1, 12] na wartość `val` i zapisuje `val - 1` w i zapisuje jego wartość w `pt-&tm_mon` .

`'M'` --konwertuje pole wejściowe dziesiętne z zakresu [0, 59] i zapisuje jego wartość w `pt-&tm_min` .

`'n'` lub `'t'` --zachowuje się tak samo jak `" "` .

`'p'` --Konwertuje wartość "AM" lub "am" na zero, a "PM" lub "PM" do 12 i dodaje ją do `pt-&tm_hour` .

`'r'` --zachowuje się tak samo jak `"%I : %M : %S %p"` .

`'R'` --zachowuje się tak samo jak `"%H %M"` .

`'S'` --konwertuje pole wejściowe dziesiętne z zakresu [0, 59] i zapisuje jego wartość w `pt-&tm_sec` .

`'T'` lub `'X'` --zachowuje się tak samo jak `"%H : %M : S"` .

`'U'` --konwertuje pole wejściowe dziesiętne z zakresu [0, 53] i zapisuje jego wartość w `pt-&tm_yday` .

`'w'` --konwertuje pole wejściowe dziesiętne w zakresie [0, 6] i zapisuje jego wartość w `pt-&tm_wday` .

`'W'` --konwertuje pole wejściowe dziesiętne z zakresu [0, 53] i zapisuje jego wartość w `pt-&tm_yday` .

`'x'` --zachowuje się tak samo jak `"%d / %m / %y"` .

`'y'` --konwertuje pole wejściowe dziesiętne z zakresu [0, 99] na wartość `val` i zapisuje `val < 69  val + 100 : val` w `pt-&tm_year` .

`'Y'` --zachowuje się tak samo jak [time_get:: get_year](#get_year).

Wszystkie inne Specyfikatory konwersji są ustawiane `ios_base::failbit` w `state` i zwracają. W tej implementacji dowolny modyfikator nie ma wpływu.

## <a name="time_getdo_get_date"></a><a name="do_get_date"></a> time_get::d o_get_date

Chroniona funkcja wirtualna elementu członkowskiego, która jest wywoływana, aby przeanalizować ciąg jako datę wygenerowaną przez specyfikator *x* dla `strftime` .

```cpp
virtual iter_type do_get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych odnoszący się do początku sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych odnoszący się do końca sekwencji do przekonwertowania.

*iosbase*\
Flaga formatu, która po ustawieniu wskazuje, że symbol waluty jest opcjonalny. w przeciwnym razie jest to wymagane.

*Państwu*\
Ustawia odpowiednie elementy maski bitowej dla stanu strumienia w zależności od tego, czy operacje zakończyły się powodzeniem.

*ptm*\
Wskaźnik do lokalizacji, w której mają być przechowywane informacje o dacie.

### <a name="return-value"></a>Wartość zwracana

Iterator danych wejściowych odnoszący się do pierwszego elementu poza polem wejściowym.

### <a name="remarks"></a>Uwagi

Wirtualna funkcja chronionego elementu członkowskiego próbuje dopasować elementy sekwencyjne zaczynające się od pierwszej w sekwencji [ `first` , `last` ), dopóki nie rozpoznano kompletnego, niepustego pola wejściowego daty. Jeśli to się powiedzie, konwertuje to pole na jego równoważną wartość jako składniki **TM:: TM \_ Mon**, **TM:: TM \_ Day** i **TM:: TM \_ Year**, a wyniki są przechowywane `ptm->tm_mon` odpowiednio w, `ptm->tm_day` i `ptm->tm_year` . Zwraca iterator wyznaczający pierwszy element poza pole danych wejściowych daty. W przeciwnym razie funkcje są ustawiane `iosbase::failbit` w *stanie*. Zwraca iterator wyznaczający pierwszy element poza dowolnym prefiksem prawidłowego pola wejściowego daty. W obu przypadkach, jeśli wartość zwracana jest równa *Last*, funkcja ustawia `ios_base::eofbit` w *stanie*.

Format pola danych wejściowych daty jest zależny od ustawień regionalnych. W przypadku domyślnych ustawień regionalnych pole daty wejścia ma postać MMM DD, rrrr, gdzie:

- MMM jest dopasowywany przez wywoływanie [get_monthname](#get_monthname), co oznacza miesiąc.

- DD jest sekwencją cyfr dziesiętnych, których odpowiadająca wartość liczbowa musi należeć do zakresu [1, 31], co oznacza dzień miesiąca.

- RRRR jest dopasowywane przez wywołanie [get_year](#get_year), co oznacza rok.

Spacje w postaci literałów i przecinki muszą być zgodne z odpowiednimi elementami w sekwencji wejściowej.

### <a name="example"></a>Przykład

Zapoznaj się z przykładem dla [get_date](#get_date), które wywołuje `do_get_date` .

## <a name="time_getdo_get_monthname"></a><a name="do_get_monthname"></a> time_get::d o_get_monthname

Chroniona funkcja wirtualna elementu członkowskiego, która jest wywoływana, aby przeanalizować ciąg jako nazwę miesiąca.

```cpp
virtual iter_type do_get_monthname(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych odnoszący się do początku sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych odnoszący się do końca sekwencji do przekonwertowania.

*iosbase*\
Nieużywany.

*Państwu*\
Parametr wyjściowy, który ustawia odpowiednie elementy maski bitowej dla stanu strumienia w zależności od tego, czy operacja zakończyła się pomyślnie.

*ptm*\
Wskaźnik do lokalizacji, w której mają być przechowywane informacje o miesiącach.

### <a name="return-value"></a>Wartość zwracana

Iterator danych wejściowych odnoszący się do pierwszego elementu poza polem wejściowym.

### <a name="remarks"></a>Uwagi

Wirtualna chroniona funkcja członkowska próbuje dopasować elementy sekwencyjne zaczynające się od pierwszej w sekwencji [ `first` , `last` ), dopóki nie rozpoznano kompletnego, niepustego miesiąca pola wejściowego. Jeśli to się powiedzie, konwertuje to pole na jego równoważną wartość jako składnik **TM:: TM \_ Mon** i zapisuje wynik w `ptm->tm_mon` . Zwraca iterator wyznaczający pierwszy element wykraczający poza pole danych wejściowych miesiąca. W przeciwnym razie funkcje są ustawiane `ios_base::failbit` w *stanie*. Zwraca iterator wyznaczający pierwszy element poza dowolnym prefiksem prawidłowego pola wejściowego miesiąca. W obu przypadkach, jeśli wartość zwracana jest równa *Last*, funkcja ustawia `ios_base::eofbit` w *stanie*.

Pole danych wejściowych miesiąca jest sekwencją, która jest zgodna z najdłuższym zestawem sekwencji specyficznych dla ustawień regionalnych, takich jak Jan, styczeń, luty, luty itd. Przekonwertowana wartość to liczba miesięcy od stycznia.

### <a name="example"></a>Przykład

Zapoznaj się z przykładem dla [get_monthname](#get_monthname), które wywołuje `do_get_monthname` .

## <a name="time_getdo_get_time"></a><a name="do_get_time"></a> time_get::d o_get_time

Chroniona funkcja wirtualna elementu członkowskiego, która jest wywoływana, aby przeanalizować ciąg jako datę wygenerowaną przez specyfikator *X* dla `strftime` .

```cpp
virtual iter_type do_get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych odnoszący się do początku sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych odnoszący się do końca sekwencji do przekonwertowania.

*iosbase*\
Nieużywany.

*Państwu*\
Ustawia odpowiednie elementy maski bitowej dla stanu strumienia w zależności od tego, czy operacje zakończyły się powodzeniem.

*ptm*\
Wskaźnik do lokalizacji, w której mają być przechowywane informacje o dacie.

### <a name="return-value"></a>Wartość zwracana

Iterator danych wejściowych odnoszący się do pierwszego elementu poza polem wejściowym.

### <a name="remarks"></a>Uwagi

Wirtualna funkcja chronionego elementu członkowskiego próbuje dopasować elementy sekwencyjne zaczynające się od pierwszej w sekwencji [ `first` , `last` ), dopóki nie rozpoznano kompletnego, niepustego pola wejściowego czasu. Jeśli to się powiedzie, konwertuje to pole na jego równoważną wartość jako składniki `tm::tm_hour` , `tm::tm_min` , i `tm::tm_sec` , i przechowuje wyniki w `ptm->tm_hour` , `ptm->tm_min` , i `ptm->tm_sec` , odpowiednio. Zwraca iterator wyznaczający pierwszy element poza pole wejściowy czas. W przeciwnym razie funkcje są ustawiane `ios_base::failbit` w *stanie*. Zwraca iterator wyznaczający pierwszy element poza dowolnym prefiksem prawidłowego pola wejściowego czasu. W obu przypadkach, jeśli wartość zwracana jest równa *Last*, funkcja ustawia `ios_base::eofbit` w *stanie*.

W tej implementacji pole Input Time ma postać HH: MM: SS, gdzie:

- HH jest sekwencją cyfr dziesiętnych, których odpowiadająca wartość liczbowa musi należeć do zakresu [0, 24), co oznacza godzinę dnia.

- MM jest sekwencją cyfr dziesiętnych, których odpowiadająca wartość liczbowa musi znajdować się w zakresie [0, 60), co oznacza, że liczba minut przypada na godzinę.

- SS jest sekwencją cyfr dziesiętnych, których odpowiadająca wartość liczbowa musi należeć do zakresu [0, 60), co powoduje, że sekundy czas przypada na minutę.

Dwukropki w literałach muszą być zgodne z odpowiednimi elementami w sekwencji wejściowej.

### <a name="example"></a>Przykład

Zapoznaj się z przykładem dla [get_time](#get_time), które wywołuje `do_get_time` .

## <a name="time_getdo_get_weekday"></a><a name="do_get_weekday"></a> time_get::d o_get_weekday

Chroniona funkcja wirtualna elementu członkowskiego, która jest wywoływana, aby przeanalizować ciąg jako nazwę dnia tygodnia.

```cpp
virtual iter_type do_get_weekday(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych odnoszący się do początku sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych odnoszący się do końca sekwencji do przekonwertowania.

*iosbase*\
Flaga formatu, która po ustawieniu wskazuje, że symbol waluty jest opcjonalny. w przeciwnym razie jest to wymagane.

*Państwu*\
Ustawia odpowiednie elementy maski bitowej dla stanu strumienia w zależności od tego, czy operacje zakończyły się powodzeniem.

*ptm*\
Wskaźnik do lokalizacji, do której mają być przechowywane informacje o dniu tygodnia.

### <a name="return-value"></a>Wartość zwracana

Iterator danych wejściowych odnoszący się do pierwszego elementu poza polem wejściowym.

### <a name="remarks"></a>Uwagi

Wirtualna chroniona funkcja członkowska próbuje dopasować elementy sekwencyjne zaczynające się od *pierwszej* w sekwencji [ `first` , `last` ), dopóki nie rozpoznano kompletnego, niepustego pola wejściowego dnia tygodnia. Jeśli to się powiedzie, konwertuje to pole na jego równoważną wartość jako składnik **TM:: TM \_ wDay** i zapisuje wynik w `ptm->tm_wday` . Zwraca iterator wyznaczający pierwszy element poza pole danych wejściowych dnia tygodnia. W przeciwnym razie funkcje są ustawiane `ios_base::failbit` w *stanie*. Zwraca iterator wyznaczający pierwszy element poza dowolnym prefiksem prawidłowego pola wejściowego dnia tygodnia. W obu przypadkach, jeśli wartość zwracana jest równa *Last*, funkcja ustawia `ios_base::eofbit` w *stanie*.

Pole danych wejściowych dnia tygodnia jest sekwencją, która jest zgodna z najdłuższym zestawem sekwencji specyficznych dla ustawień regionalnych, takich jak Sun, niedziela, PN, poniedziałek itd. Przekonwertowana wartość to liczba dni od niedzieli.

### <a name="example"></a>Przykład

Zapoznaj się z przykładem dla [get_weekday](#get_weekday), które wywołuje `do_get_weekday` .

## <a name="time_getdo_get_year"></a><a name="do_get_year"></a> time_get::d o_get_year

Chroniona funkcja wirtualna elementu członkowskiego, która jest wywoływana, aby przeanalizować ciąg jako nazwę roku.

```cpp
virtual iter_type do_get_year(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych odnoszący się do początku sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych odnoszący się do końca sekwencji do przekonwertowania.

*iosbase*\
Flaga formatu, która po ustawieniu wskazuje, że symbol waluty jest opcjonalny. w przeciwnym razie jest to wymagane.

*Państwu*\
Ustawia odpowiednie elementy maski bitowej dla stanu strumienia w zależności od tego, czy operacje zakończyły się powodzeniem.

*ptm*\
Wskaźnik do lokalizacji, w której mają być przechowywane informacje o roku.

### <a name="return-value"></a>Wartość zwracana

Iterator danych wejściowych odnoszący się do pierwszego elementu poza polem wejściowym.

### <a name="remarks"></a>Uwagi

Wirtualna chroniona funkcja członkowska próbuje dopasować elementy sekwencyjne zaczynające się od *pierwszej* w sekwencji [ `first` , `last` ), dopóki nie rozpoznano kompletnego, niepustego pola wejściowego roku. Jeśli to się powiedzie, konwertuje to pole na odpowiadającą mu wartość jako składnik **TM:: TM \_ roku** i zapisuje wynik w `ptm->tm_year` . Zwraca iterator wyznaczający pierwszy element poza pole danych wejściowych roku. W przeciwnym razie funkcje są ustawiane `ios_base::failbit` w *stanie*. Zwraca iterator wyznaczający pierwszy element poza dowolnym prefiksem pola wejściowego w prawidłowym roku. W obu przypadkach, jeśli wartość zwracana jest równa *Last*, funkcja ustawia `ios_base::eofbit` w *stanie*.

Pole wejściowe Year jest sekwencją cyfr dziesiętnych, których odpowiadająca wartość liczbowa musi należeć do zakresu [1900, 2036). Wartość przechowywana jest wartością minus 1900. W tej implementacji wartości z zakresu [69, 136) reprezentują zakres lat [1969, 2036). Dozwolone są również wartości z zakresu [0, 69), ale mogą one reprezentować albo zakres lat [1900, 1969), albo [2000, 2069), w zależności od konkretnego środowiska tłumaczenia.

### <a name="example"></a>Przykład

Zapoznaj się z przykładem dla [get_year](#get_year), które wywołuje `do_get_year` .

## <a name="time_getget"></a><a name="get"></a> time_get:: Get

Odczytuje ze źródła danych znakowych i konwertuje te dane na czas, który jest przechowywany w strukturze czasu. Pierwsza funkcja akceptuje jeden specyfikator konwersji i modyfikator, drugi akceptuje kilka.

```cpp
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm,
    char fmt,
    char mod) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm,
    char_type* fmt_first,
    char_type* fmt_last) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych, który wskazuje, gdzie zaczyna się sekwencja konwersji.

*ostatniego*\
Iterator danych wejściowych, który wskazuje koniec sekwencji do przekonwertowania.

*iosbase*\
Strumień.

*Państwu*\
Odpowiednie elementy masek bitowych są ustawiane dla stanu strumienia, aby wskazywały błędy.

*ptm*\
Wskaźnik na strukturę czasu, w której ma być przechowywany czas.

*FMT*\
Znak specyfikatora konwersji.

*Funkcja*\
Opcjonalny znak modyfikatora.

*fmt_first*\
Wskazuje, gdzie rozpoczyna się dyrektywa format.

*fmt_last*\
Wskazuje koniec dyrektyw formatu.

### <a name="return-value"></a>Wartość zwracana

Zwraca iterator do pierwszego znaku po danych, które zostały użyte do przypisania struktury czasu `*ptm` .

### <a name="remarks"></a>Uwagi

Pierwsza funkcja elementu członkowskiego zwraca `do_get(first, last, iosbase, state, ptm, fmt, mod)` .

Druga funkcja elementu członkowskiego wywołuje `do_get` kontrolę w formacie rozdzielonym przez `[fmt_first, fmt_last)` . Traktuje format jako sekwencję pól, z których każdy określa konwersję zero lub więcej elementów wejściowych rozdzielanych przez `[first, last)` . Zwraca iterator wyznaczający pierwszy nieprzekonwertowany element. Istnieją trzy rodzaje pól:

Procent (%) w formacie, po którym następuje opcjonalny modyfikator *mod* w zestawie [EOQ #], po którym następuje specyfikator konwersji *FMT*, zastępuje *najpierw* wartość zwróconą przez `do_get(first, last, iosbase, state, ptm, fmt, mod)` . Zestaw błędów konwersji `ios_base::failbit` w *stanie* i zwraca wartość.

Element odstępu w formacie powoduje pominięcie ostatnich zero lub więcej elementów odstępów wejściowych.

Każdy inny element w formacie musi pasować do następnego elementu wejściowego, który jest pomijany. Zestawy błędów dopasowania `ios_base::failbit` w *stanie* i Returns.

## <a name="time_getget_date"></a><a name="get_date"></a> time_get:: get_date

Analizuje ciąg jako datę wygenerowaną przez specyfikator *x* dla `strftime` .

```cpp
iter_type get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych odnoszący się do początku sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych odnoszący się do końca sekwencji do przekonwertowania.

*iosbase*\
Flaga formatu, która po ustawieniu wskazuje, że symbol waluty jest opcjonalny. w przeciwnym razie jest to wymagane.

*Państwu*\
Ustawia odpowiednie elementy maski bitowej dla stanu strumienia w zależności od tego, czy operacje zakończyły się powodzeniem.

*ptm*\
Wskaźnik do lokalizacji, w której mają być przechowywane informacje o dacie.

### <a name="return-value"></a>Wartość zwracana

Iterator danych wejściowych odnoszący się do pierwszego elementu poza polem wejściowym.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca [do_get_date](#do_get_date)( `first` , `last` ,,, `iosbase` `state` `ptm` ).

Należy pamiętać, że miesiące są liczone od 0 do 11.

### <a name="example"></a>Przykład

```cpp
// time_get_get_date.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream< char > pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset(&t, 0, sizeof(struct tm));

   pszGetF << "July 4, 2000";
   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet <time_get<char> >
   (loc).get_date(basic_istream<char>::_Iter(pszGetF.rdbuf( ) ),
            basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if ( st & ios_base::failbit )
      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_sec: " << t.tm_sec
      << "\ntm_min: " << t.tm_min
      << "\ntm_hour: " << t.tm_hour
      << "\ntm_mday: " << t.tm_mday
      << "\ntm_mon: " << t.tm_mon
      << "\ntm_year: " << t.tm_year
      << "\ntm_wday: " << t.tm_wday
      << "\ntm_yday: " << t.tm_yday
      << "\ntm_isdst: " << t.tm_isdst
      << endl;
}
```

```Output
time_get(July 4, 2000) =
tm_sec: 0
tm_min: 0
tm_hour: 0
tm_mday: 4
tm_mon: 6
tm_year: 100
tm_wday: 0
tm_yday: 0
tm_isdst: 0
```

## <a name="time_getget_monthname"></a><a name="get_monthname"></a> time_get:: get_monthname

Analizuje ciąg jako nazwę miesiąca.

```cpp
iter_type get_monthname(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych odnoszący się do początku sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych odnoszący się do końca sekwencji do przekonwertowania.

*iosbase*\
Nieużywany.

*Państwu*\
Parametr wyjściowy, który ustawia odpowiednie elementy maski bitowej dla stanu strumienia w zależności od tego, czy operacja zakończyła się pomyślnie.

*ptm*\
Wskaźnik do lokalizacji, w której mają być przechowywane informacje o miesiącach.

### <a name="return-value"></a>Wartość zwracana

Iterator danych wejściowych odnoszący się do pierwszego elementu poza polem wejściowym.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca [do_get_monthname](#do_get_monthname)( `first` , `last` ,,, `iosbase` `state` `ptm` ).

### <a name="example"></a>Przykład

```cpp
// time_get_get_monthname.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc ( "French" );
   basic_stringstream<char> pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "juillet";
   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet <time_get <char> >
   (loc).get_monthname(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
              basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_sec: " << t.tm_sec
      << "\ntm_min: " << t.tm_min
      << "\ntm_hour: " << t.tm_hour
      << "\ntm_mday: " << t.tm_mday
      << "\ntm_mon: " << t.tm_mon
      << "\ntm_year: " << t.tm_year
      << "\ntm_wday: " << t.tm_wday
      << "\ntm_yday: " << t.tm_yday
      << "\ntm_isdst: " << t.tm_isdst
      << endl;
}
```

```Output
time_get(juillet) =
tm_sec: 0
tm_min: 0
tm_hour: 0
tm_mday: 0
tm_mon: 6
tm_year: 0
tm_wday: 0
tm_yday: 0
tm_isdst: 0
```

## <a name="time_getget_time"></a><a name="get_time"></a> time_get:: get_time

Analizuje ciąg jako datę wygenerowaną przez specyfikator *X* dla `strftime` .

```cpp
iter_type get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych odnoszący się do początku sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych odnoszący się do końca sekwencji do przekonwertowania.

*iosbase*\
Nieużywany.

*Państwu*\
Ustawia odpowiednie elementy maski bitowej dla stanu strumienia w zależności od tego, czy operacje zakończyły się powodzeniem.

*ptm*\
Wskaźnik do lokalizacji, w której mają być przechowywane informacje o dacie.

### <a name="return-value"></a>Wartość zwracana

Iterator danych wejściowych odnoszący się do pierwszego elementu poza polem wejściowym.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca [do_get_time](#do_get_time)( `first` , `last` ,,, `iosbase` `state` `ptm` ).

### <a name="example"></a>Przykład

```cpp
// time_get_get_time.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "11:13:20";
   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet
      <time_get <char> >
      (loc).get_time(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
               basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_sec: " << t.tm_sec
      << "\ntm_min: " << t.tm_min
      << "\ntm_hour: " << t.tm_hour
      << endl;
}
```

```Output
time_get::get_time(11:13:20) =
tm_sec: 20
tm_min: 13
tm_hour: 11
```

## <a name="time_getget_weekday"></a><a name="get_weekday"></a> time_get:: get_weekday

Analizuje ciąg jako nazwę dnia tygodnia.

```cpp
iter_type get_weekday(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych odnoszący się do początku sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych odnoszący się do końca sekwencji do przekonwertowania.

*iosbase*\
Flaga formatu, która po ustawieniu wskazuje, że symbol waluty jest opcjonalny. w przeciwnym razie jest to wymagane.

*Państwu*\
Ustawia odpowiednie elementy maski bitowej dla stanu strumienia w zależności od tego, czy operacje zakończyły się powodzeniem.

*ptm*\
Wskaźnik do lokalizacji, do której mają być przechowywane informacje o dniu tygodnia.

### <a name="return-value"></a>Wartość zwracana

Iterator danych wejściowych odnoszący się do pierwszego elementu poza polem wejściowym.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca [do_get_weekday](#do_get_weekday)( `first` , `last` ,,, `iosbase` `state` `ptm` ).

### <a name="example"></a>Przykład

```cpp
// time_get_get_weekday.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc ( "French" );
   basic_stringstream< char > pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "mercredi";
   pszGetF.imbue(loc);
   basic_istream<char>::_Iter i = use_facet
      <time_get<char> >
      (loc).get_weekday(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
               basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_wday: " << t.tm_wday
      << endl;
}
```

```Output
time_get::get_time(mercredi) =
tm_wday: 3
```

## <a name="time_getget_year"></a><a name="get_year"></a> time_get:: get_year

Analizuje ciąg jako nazwę roku.

```cpp
iter_type get_year(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametry

*pierwszego*\
Iterator danych wejściowych odnoszący się do początku sekwencji do przekonwertowania.

*ostatniego*\
Iterator danych wejściowych odnoszący się do końca sekwencji do przekonwertowania.

*iosbase*\
Flaga formatu, która po ustawieniu wskazuje, że symbol waluty jest opcjonalny. w przeciwnym razie jest to wymagane.

*Państwu*\
Ustawia odpowiednie elementy maski bitowej dla stanu strumienia w zależności od tego, czy operacje zakończyły się powodzeniem.

*ptm*\
Wskaźnik do lokalizacji, w której mają być przechowywane informacje o roku.

### <a name="return-value"></a>Wartość zwracana

Iterator danych wejściowych odnoszący się do pierwszego elementu poza polem wejściowym.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca [do_get_year](#do_get_year)( `first` , `last` ,,, `iosbase` `state` `ptm` ).

### <a name="example"></a>Przykład

```cpp
// time_get_get_year.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "1928";

   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet
      <time_get<char> >
      (loc).get_year(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
               basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get::get_year("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get::get_year("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_year: " << t.tm_year
      << endl;
}
```

```Output
time_get::get_year(1928) =
tm_year: 28
```

## <a name="time_getiter_type"></a><a name="iter_type"></a> time_get:: iter_type

Typ, który opisuje iterator danych wejściowych.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla parametru szablonu **InputIterator**.

## <a name="time_gettime_get"></a><a name="time_get"></a> time_get:: time_get

Konstruktor dla obiektów typu `time_get` .

```cpp
explicit time_get(size_t refs = 0);
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

Konstruktor inicjuje swój obiekt podstawowy przy użyciu **ustawień regionalnych::**[facet](../standard-library/locale-class.md#facet_class)( `refs` ).

## <a name="see-also"></a>Zobacz też

[\<locale>](../standard-library/locale.md)\
[Klasa time_base](../standard-library/time-base-class.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

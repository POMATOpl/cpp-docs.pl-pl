---
description: 'Dowiedz się więcej na temat: hash_set (STL/CLR)'
title: hash_set (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::hash_set
- cliext::hash_set::begin
- cliext::hash_set::bucket_count
- cliext::hash_set::clear
- cliext::hash_set::const_iterator
- cliext::hash_set::const_reference
- cliext::hash_set::const_reverse_iterator
- cliext::hash_set::count
- cliext::hash_set::difference_type
- cliext::hash_set::empty
- cliext::hash_set::end
- cliext::hash_set::equal_range
- cliext::hash_set::erase
- cliext::hash_set::find
- cliext::hash_set::generic_container
- cliext::hash_set::generic_iterator
- cliext::hash_set::generic_reverse_iterator
- cliext::hash_set::generic_value
- cliext::hash_set::hash_delegate
- cliext::hash_set::hash_set
- cliext::hash_set::hasher
- cliext::hash_set::insert
- cliext::hash_set::iterator
- cliext::hash_set::key_comp
- cliext::hash_set::key_compare
- cliext::hash_set::key_type
- cliext::hash_set::load_factor
- cliext::hash_set::lower_bound
- cliext::hash_set::make_value
- cliext::hash_set::max_load_factor
- cliext::hash_set::operator=
- cliext::hash_set::rbegin
- cliext::hash_set::reference
- cliext::hash_set::rehash
- cliext::hash_set::rend
- cliext::hash_set::reverse_iterator
- cliext::hash_set::size
- cliext::hash_set::size_type
- cliext::hash_set::swap
- cliext::hash_set::to_array
- cliext::hash_set::upper_bound
- cliext::hash_set::value_comp
- cliext::hash_set::value_compare
- cliext::hash_set::value_type
helpviewer_keywords:
- <cliext/hash_set> header [STL/CLR]
- hash_set class [STL/CLR]
- <hash_set> header [STL/CLR]
- begin member [STL/CLR]
- bucket_count member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- hash_delegate member [STL/CLR]
- hash_set member [STL/CLR]
- hasher member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- load_factor member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- max_load_factor member [STL/CLR]
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rehash member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: d110e356-ba3e-4e52-9e2d-d997bf975c96
ms.openlocfilehash: 0705dd674af21958b5d4f4b0a5a904eb42aff76a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335470"
---
# <a name="hash_set-stlclr"></a>hash_set (STL/CLR)

Klasa szablonu opisuje obiekt, który kontroluje różnej długości sekwencje elementów, które mają dostęp dwukierunkowy. Kontener służy `hash_set` do zarządzania sekwencją elementów jako tabelą skrótów, każdy wpis w tabeli przechowujący dwukierunkową listę węzłów oraz każdy węzeł przechowujący jeden element. Wartość każdego elementu jest używana jako klucz do porządkowania sekwencji.

W poniższym opisie `GValue` jest taka sama jak `GKey` , która z kolei jest taka sama jak *klucz* , chyba że ostatni jest typem ref, w takim przypadku jest to `Key^` .

## <a name="syntax"></a>Składnia

```cpp
template<typename Key>
    ref class hash_set
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>Parametry

*Klucz*<br/>
Typ składnika klucza elementu w kontrolowanej sekwencji.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<cliext/hash_set>

**Przestrzeń nazw:** cliext

## <a name="declarations"></a>Deklaracje

|Definicja typu|Opis|
|---------------------|-----------------|
|[hash_set::const_iterator (STL/CLR)](#const_iterator)|Typ iteratora stałego dla kontrolowanej sekwencji.|
|[hash_set::const_reference (STL/CLR)](#const_reference)|Typ stałego odwołania do elementu.|
|[hash_set::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Typ iteratora stałego zwrotnego dla kontrolowanej sekwencji.|
|[hash_set::difference_type (STL/CLR)](#difference_type)|Typ (prawdopodobnie podpisany) odległości między dwoma elementami.|
|[hash_set::generic_container (STL/CLR)](#generic_container)|Typ interfejsu generycznego dla kontenera.|
|[hash_set::generic_iterator (STL/CLR)](#generic_iterator)|Typ iteratora dla interfejsu generycznego dla kontenera.|
|[hash_set::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Typ iteratora odwrotnego dla interfejsu generycznego dla kontenera.|
|[hash_set::generic_value (STL/CLR)](#generic_value)|Typ elementu dla interfejsu generycznego dla kontenera.|
|[hash_set::hasher (STL/CLR)](#hasher)|Delegat skrótu dla klucza.|
|[hash_set::iterator (STL/CLR)](#iterator)|Typ iteratora dla kontrolowanej sekwencji.|
|[hash_set::key_compare (STL/CLR)](#key_compare)|Delegat porządkowania dla dwóch kluczy.|
|[hash_set::key_type (STL/CLR)](#key_type)|Typ klucza sortowania.|
|[hash_set::reference (STL/CLR)](#reference)|Typ odwołania do elementu.|
|[hash_set::reverse_iterator (STL/CLR)](#reverse_iterator)|Typ iteratora odwrotnego dla kontrolowanej sekwencji.|
|[hash_set::size_type (STL/CLR)](#size_type)|Typ (nieujemnej) odległości między dwoma elementami.|
|[hash_set::value_compare (STL/CLR)](#value_compare)|Delegat porządkowania dla dwóch wartości elementów.|
|[hash_set::value_type (STL/CLR)](#value_type)|Typ elementu.|

|Funkcja elementów członkowskich|Opis|
|---------------------|-----------------|
|[hash_set::begin (STL/CLR)](#begin)|Określa początek kontrolowanej sekwencji.|
|[hash_set::bucket_count (STL/CLR)](#bucket_count)|Zlicza liczbę przedziałów.|
|[hash_set::clear (STL/CLR)](#clear)|Usuwa wszystkie elementy.|
|[hash_set::count (STL/CLR)](#count)|Zlicza elementy pasujące do określonego klucza.|
|[hash_set::empty (STL/CLR)](#empty)|Sprawdza, czy nie ma żadnych elementów.|
|[hash_set::end (STL/CLR)](#end)|Określa koniec kontrolowanej sekwencji.|
|[hash_set::equal_range (STL/CLR)](#equal_range)|Wyszukuje zakres, który odpowiada określonemu kluczowi.|
|[hash_set::erase (STL/CLR)](#erase)|Usuwa elementy z określonych pozycji.|
|[hash_set::find (STL/CLR)](#find)|Wyszukuje element, który odpowiada określonemu kluczowi.|
|[hash_set::hash_delegate (STL/CLR)](#hash_delegate)|Kopiuje delegata wyznaczania wartości skrótu dla klucza.|
|[hash_set::hash_set (STL/CLR)](#hash_set)|Konstruuje obiekt kontenera.|
|[hash_set::insert (STL/CLR)](#insert)|Dodaje elementy.|
|[hash_set::key_comp (STL/CLR)](#key_comp)|Kopiuje delegata porządkowania dla dwóch kluczy.|
|[hash_set::load_factor (STL/CLR)](#load_factor)|Oblicza średnią liczbę elementów na przedział.|
|[hash_set::lower_bound (STL/CLR)](#lower_bound)|Znajduje początek zakresu, który odpowiada określonemu kluczowi.|
|[hash_set::make_value (STL/CLR)](#make_value)|Konstruuje obiekt wartości.|
|[hash_set::max_load_factor (STL/CLR)](#max_load_factor)|Pobiera lub ustawia maksymalną liczbę elementów na przedział.|
|[hash_set::rbegin (STL/CLR)](#rbegin)|Określa początek odwróconej sekwencji kontrolowanej.|
|[hash_set::rehash (STL/CLR)](#rehash)|Przebudowuje tabelę mieszania.|
|[hash_set::rend (STL/CLR)](#rend)|Określa koniec odwróconej kontrolowanej sekwencji.|
|[hash_set::size (STL/CLR)](#size)|Liczy liczbę elementów.|
|[hash_set::swap (STL/CLR)](#swap)|Zamienia zawartości dwóch kontenerów.|
|[hash_set::to_array (STL/CLR)](#to_array)|Kopiuje przekontrolowaną sekwencję do nowej tablicy.|
|[hash_set::upper_bound (STL/CLR)](#upper_bound)|Znajduje koniec zakresu, który odpowiada określonemu kluczowi.|
|[hash_set::value_comp (STL/CLR)](#value_comp)|Kopiuje delegata porządkowania dla dwóch wartości elementów.|

|Operator|Opis|
|--------------|-----------------|
|[hash_set::operator= (STL/CLR)](#op)|Zastępuje kontrolowaną sekwencję.|

## <a name="interfaces"></a>Interfejsy

|Interfejs|Opis|
|---------------|-----------------|
|<xref:System.ICloneable>|Duplikowanie obiektu.|
|<xref:System.Collections.IEnumerable>|Sekwencja przez elementy.|
|<xref:System.Collections.ICollection>|Obsługa grupy elementów.|
|<xref:System.Collections.Generic.IEnumerable%601>|Sekwencja przez wpisane elementy.|
|<xref:System.Collections.Generic.ICollection%601>|Obsługuj grupę wpisanych elementów.|
|IHash\<Key, Value>|Obsługa kontenera ogólnego.|

## <a name="remarks"></a>Uwagi

Obiekt przydziela i zwalnia magazyn dla sekwencji, która kontroluje jako pojedyncze węzły na liście połączonej dwukierunkowo. Aby przyspieszyć dostęp, obiekt przechowuje również tablicę o różnej długości wskaźników do listy (tabela skrótów), efektywnie zarządzając całą listą jako sekwencję podlistów lub zasobników. Wstawia elementy do zasobnika, który ma być uporządkowany przez zmianę linków między węzłami, bez kopiowania zawartości jednego węzła do drugiego. Oznacza to, że można wstawiać i usuwać elementy swobodnie bez zakłócania pozostałych elementów.

Obiekt porządkuje każdy przedział IT, wywołując zapisany obiekt delegata typu [hash_set:: key_compare (STL/CLR)](#key_compare). Podczas konstruowania hash_set można określić przechowywany obiekt delegata; Jeśli określisz brak obiektu delegowanego, wartością domyślną jest porównanie `operator<=(key_type, key_type)` .

Dostęp do przechowywanego obiektu delegata można uzyskać, wywołując funkcję członkowską [hash_set:: key_comp (STL/CLR)](#key_comp) `()` . Taki obiekt delegata musi definiować równoważne porządkowanie między kluczami typu [hash_set:: key_type (STL/CLR)](#key_type). Oznacza to, że dla dowolnych dwóch kluczy `X` i `Y` :

`key_comp()(X, Y)` zwraca ten sam wynik Boolean dla każdego wywołania.

Jeśli `key_comp()(X, Y) && key_comp()(Y, X)` ma wartość true, wówczas `X` i `Y` są określane jako równoważne porządkowanie.

Dowolna reguła porządkowania, która zachowuje się jak `operator<=(key_type, key_type)` `operator>=(key_type, key_type)` lub `operator==(key_type, key_type)` definiuje porządkowanie eqivalent.

Należy zauważyć, że kontener gwarantuje tylko te elementy, których klucze mają równoważne porządkowanie (i które mieszanie z tą samą wartością całkowitą) jest przyległy w obrębie przedziału. W przeciwieństwie do klas szablonu [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)obiekt klasy szablonu `hash_set` gwarantuje, że klucze dla wszystkich elementów są unikatowe. (Żadne dwa klucze nie mają równoważnej kolejności).

Obiekt określa, który zasobnik powinien zawierać dany klucz porządkowania, wywołując zapisany obiekt delegata typu [hash_set:: Hasher (STL/CLR)](#hasher). Dostęp do tego przechowywanego obiektu można uzyskać, wywołując funkcję członkowską [hash_set:: hash_delegate (STL/CLR)](#hash_delegate) `()` w celu uzyskania wartości całkowitej, która zależy od wartości klucza. Podczas konstruowania hash_set można określić przechowywany obiekt delegata; Jeśli określisz brak obiektu delegowanego, wartością domyślną jest funkcja `System::Object::hash_value(key_type)` . Oznacza to, że dla wszystkich kluczy `X` i `Y` :

`hash_delegate()(X)` zwraca ten sam wynik całkowity dla każdego wywołania.

Jeśli `X` i `Y` mają równoważne porządkowanie, wówczas `hash_delegate()(X)` powinna zwracać wynik tego samego typu Integer co `hash_delegate()(Y)` .

Każdy element służy jako klucz i wartość. Sekwencja jest reprezentowana w sposób umożliwiający wyszukiwanie, wstawianie i usuwanie dowolnego elementu z liczbą operacji, która jest niezależna od liczby elementów w sekwencji (stały czas) — co najmniej w najlepszym przypadku. Ponadto, wstawianie elementu nie unieważnia iteratorów, a usuwanie elementu unieważnia tylko te iteratory, które wskazują na usunięty element.

Jeśli wartości skrótów nie są dystrybuowane równomiernie, może to spowodować wygenerowanie tabeli skrótów. W skrajnym — dla funkcji skrótu, która zawsze zwraca tę samą wartość — wyszukiwanie, wstawianie i usuwanie jest proporcjonalna do liczby elementów w sekwencji (czas liniowy). Kontener przedsięwzięciach, aby wybrać rozsądną funkcję mieszania, średni rozmiar przedziału i rozmiar tabeli skrótów (łączna liczba przedziałów), ale można przesłonić dowolne lub wszystkie z tych opcji. Zobacz na przykład funkcje [hash_set:: max_load_factor (STL/CLR)](#max_load_factor) i [hash_set:: rehash (STL/CLR)](#rehash).

Hash_set obsługuje Iteratory dwukierunkowe, co oznacza, że można przechodzić do sąsiadujących elementów przy użyciu iteratora, który wyznacza element w kontrolowanej sekwencji. Specjalny węzeł główny odpowiada iteratorowi zwróconemu przez [hash_set:: end (STL/CLR)](#end) `()` . Można zmniejszyć ten iterator, aby dotrzeć do ostatniego elementu w kontrolowanej sekwencji, jeśli jest obecny. Można zwiększyć iterator hash_set, aby dotrzeć do węzła głównego. następnie będzie on porównywany z równą `end()` . Ale nie można usunąć odwołania do iteratora zwróconego przez `end()` .

Należy zauważyć, że nie można odwołać się do hash_set elementu bezpośrednio przy użyciu pozycji liczbowej — która wymaga iteratora dostępu swobodnego.

Iterator hash_set przechowuje dojście do skojarzonego z nim węzła hash_set, co z kolei przechowuje dojście do skojarzonego kontenera. Iteratorów można używać tylko ze skojarzonymi obiektami kontenera. Iterator hash_set pozostaje prawidłowy, dopóki jego skojarzony węzeł hash_set jest skojarzony z pewnymi hash_setami. Ponadto prawidłowy iterator jest dereferencable — można go użyć w celu uzyskania dostępu do lub zmiany wartości elementu, który wyznacza, tak długo, jak nie jest równa `end()` .

Wymazywanie lub usuwanie elementu wywołuje destruktor dla jego przechowywanej wartości. Niszczenie kontenera powoduje wymazanie wszystkich elementów. W tym celu kontener, którego typem elementu jest Klasa ref, zapewnia, że żadne elementy nie wyprowadzą kontenera. Należy jednak zauważyć, że kontener dojść *nie* niszczy swoich elementów.

## <a name="members"></a>Elementy członkowskie

## <a name="hash_setbegin-stlclr"></a><a name="begin"></a> hash_set:: begin (STL/CLR)

Określa początek kontrolowanej sekwencji.

### <a name="syntax"></a>Składnia

```cpp
iterator begin();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca iterator dwukierunkowy, który wyznacza pierwszy element kontrolowanej sekwencji lub tuż poza końcem pustej sekwencji. Służy do uzyskania iteratora, który wyznacza `current` początek kontrolowanej sekwencji, ale jego stan może ulec zmianie w przypadku zmiany długości kontrolowanej sekwencji.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_begin.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_set::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);
    return (0);
    }
```

## <a name="hash_setbucket_count-stlclr"></a><a name="bucket_count"></a> hash_set:: bucket_count (STL/CLR)

Zlicza liczbę przedziałów.

### <a name="syntax"></a>Składnia

```cpp
int bucket_count();
```

### <a name="remarks"></a>Uwagi

Funkcje członkowskie zwracają bieżącą liczbę zasobników. Służy do określania rozmiaru tabeli skrótów.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_bucket_count.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_setclear-stlclr"></a><a name="clear"></a> hash_set:: Clear (STL/CLR)

Usuwa wszystkie elementy.

### <a name="syntax"></a>Składnia

```cpp
void clear();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska skutecznie wywołuje [hash_set:: Erase (STL/CLR)](#erase) `(` [hash_set:: begin (STL/CLR)](#begin) `(),` [hash_set:: end (STL/CLR)](#end) `())` . Jest on używany do upewnienia się, że kontrolowana sekwencja jest pusta.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_clear.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    // add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 0
a b
size() = 0
```

## <a name="hash_setconst_iterator-stlclr"></a><a name="const_iterator"></a> hash_set:: const_iterator (STL/CLR)

Typ iteratora stałego dla kontrolowanej sekwencji.

### <a name="syntax"></a>Składnia

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>Uwagi

Typ opisuje obiekt nieokreślonego typu `T2` , który może obsłużyć jako stały iterator dwukierunkowy dla kontrolowanej sekwencji.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_const_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Myhash_set::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setconst_reference-stlclr"></a><a name="const_reference"></a> hash_set:: const_reference (STL/CLR)

Typ stałego odwołania do elementu.

### <a name="syntax"></a>Składnia

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>Uwagi

Typ opisuje stałe odwołanie do elementu.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_const_reference.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Myhash_set::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myhash_set::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a> hash_set:: const_reverse_iterator (STL/CLR)

Typ iteratora stałego zwrotnego dla kontrolowanej sekwencji.

### <a name="syntax"></a>Składnia

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>Uwagi

Typ opisuje obiekt nieokreślonego typu `T4` , który może być używany jako ciągły iterator odwrotny dla kontrolowanej sekwencji.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Myhash_set::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="hash_setcount-stlclr"></a><a name="count"></a> hash_set:: Count (STL/CLR)

Wyszukuje liczbę elementów pasujących do określonego klucza.

### <a name="syntax"></a>Składnia

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>Parametry

*głównych*<br/>
Wartość klucza do wyszukania.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca liczbę elementów w kontrolowanej sekwencji, które mają równoważną kolejność z *kluczem*. Służy do określania liczby elementów aktualnie w kontrolowanej sekwencji, która pasuje do określonego klucza.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_count.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
a b c
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="hash_setdifference_type-stlclr"></a><a name="difference_type"></a> hash_set::d ifference_type (STL/CLR)

Typy podpisanej odległości między dwoma elementami.

### <a name="syntax"></a>Składnia

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>Uwagi

Typ opisuje prawdopodobnie ujemną liczbę elementów.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_difference_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_set::difference_type diff = 0;
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Myhash_set::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="hash_setempty-stlclr"></a><a name="empty"></a> hash_set:: empty (STL/CLR)

Sprawdza, czy nie ma żadnych elementów.

### <a name="syntax"></a>Składnia

```cpp
bool empty();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca wartość true dla pustej kontrolowanej sekwencji. Jest równoważne [hash_set:: size (STL/CLR)](#size) `() == 0` . Służy do sprawdzania, czy hash_set jest puste.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_empty.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="hash_setend-stlclr"></a><a name="end"></a> hash_set:: end (STL/CLR)

Określa koniec kontrolowanej sekwencji.

### <a name="syntax"></a>Składnia

```cpp
iterator end();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca iterator dwukierunkowy, który wskazuje tuż poza końcem kontrolowanej sekwencji. Służy do uzyskania iteratora, który wyznacza koniec kontrolowanej sekwencji; jego stan nie zmienia się w przypadku zmiany długości kontrolowanej sekwencji.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_end.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    Myhash_set::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
```

## <a name="hash_setequal_range-stlclr"></a><a name="equal_range"></a> hash_set:: equal_range (STL/CLR)

Wyszukuje zakres, który odpowiada określonemu kluczowi.

### <a name="syntax"></a>Składnia

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>Parametry

*głównych*<br/>
Wartość klucza do wyszukania.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca parę iteratorów `cliext::pair<iterator, iterator>(` [hash_set:: lower_bound (STL/CLR)](#lower_bound) `(key),` [hash_set:: upper_bound (STL/CLR)](#upper_bound) `(key))` . Służy do określania zakresu elementów aktualnie w kontrolowanej sekwencji, która pasuje do określonego klucza.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_equal_range.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
typedef Myhash_set::pair_iter_iter Pairii;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

    // display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("{0} ", *pair1.first);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
equal_range(L'x') empty = True
b
```

## <a name="hash_seterase-stlclr"></a><a name="erase"></a> hash_set:: Erase (STL/CLR)

Usuwa elementy z określonych pozycji.

### <a name="syntax"></a>Składnia

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
bool erase(key_type key)
```

#### <a name="parameters"></a>Parametry

*pierwszego*<br/>
Początek zakresu do wymazania.

*głównych*<br/>
Wartość klucza do wymazania.

*ostatniego*<br/>
Koniec zakresu do wymazania.

*miejscu*<br/>
Element do wymazania.

### <a name="remarks"></a>Uwagi

Pierwsza funkcja członkowska usuwa element kontrolowanej sekwencji wskazywany przez *WHERE*, a zwraca iterator, który wyznacza pierwszy element, który został poza elementem usunięty, lub [hash_set:: end (STL/CLR)](#end) , `()` Jeśli taki element nie istnieje. Służy do usuwania pojedynczego elementu.

Druga funkcja członkowska usuwa elementy z kontrolowanej sekwencji z zakresu [ `first` , `last` ) i zwraca iterator, który wyznacza pierwszy element pozostały poza elementami usuniętymi lub `end()` Jeśli taki element nie istnieje. Jest on używany do usuwania elementów sąsiadujących lub więcej.

Trzecia funkcja członkowska usuwa każdy element kontrolowanej sekwencji, którego klucz ma równoważne porządkowanie do *klucza* i zwraca liczbę usuniętych elementów. Służy do usuwania i zliczania wszystkich elementów, które pasują do określonego klucza.

Każdy element wymazuje czas proporcjonalny do logarytmu liczby elementów w kontrolowanej sekwencji.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_erase.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

    // add elements and display " b c d e"
    c1.insert(L'd');
    c1.insert(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase all but end
    Myhash_set::iterator it = c1.end();
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",
        *c1.erase(c1.begin(), --it));
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
erase(begin()) = b
b c d e
erase(begin(), end()-1) = e
size() = 1
```

## <a name="hash_setfind-stlclr"></a><a name="find"></a> hash_set:: Find (STL/CLR)

Wyszukuje element, który odpowiada określonemu kluczowi.

### <a name="syntax"></a>Składnia

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>Parametry

*głównych*<br/>
Wartość klucza do wyszukania.

### <a name="remarks"></a>Uwagi

Jeśli co najmniej jeden element w kontrolowanej sekwencji ma równoważne porządkowanie z *kluczem*, funkcja członkowska zwraca iterator wyznaczający jeden z tych elementów. w przeciwnym razie zwraca [hash_set:: end (STL/CLR)](#end) `()` . Służy do lokalizowania elementu w kontrolowanej sekwencji, który odpowiada określonemu kluczowi.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_find.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());
    System::Console::WriteLine("find {0} = {1}",
        L'b', *c1.find(L'b'));
    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
a b c
find A = False
find b = b
find C = False
```

## <a name="hash_setgeneric_container-stlclr"></a><a name="generic_container"></a> hash_set:: generic_container (STL/CLR)

Typ interfejsu generycznego dla kontenera.

### <a name="syntax"></a>Składnia

```cpp
typedef Microsoft::VisualC::StlClr::
    IHash<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>Uwagi

Typ opisuje ogólny interfejs dla tej klasy kontenera szablonu.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_generic_container.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(L'e');
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c d
a b c d e
```

## <a name="hash_setgeneric_iterator-stlclr"></a><a name="generic_iterator"></a> hash_set:: generic_iterator (STL/CLR)

Typ iteratora do użycia z interfejsem ogólnym dla kontenera.

### <a name="syntax"></a>Składnia

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>Uwagi

Typ opisuje iterator ogólny, który może być używany z interfejsem ogólnym dla tej klasy kontenera szablonu.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_generic_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_set::generic_iterator gcit = gc1->begin();
    Myhash_set::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="hash_setgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a> hash_set:: generic_reverse_iterator (STL/CLR)

Typ iteratora odwrotnego do użycia z interfejsem ogólnym dla kontenera.

### <a name="syntax"></a>Składnia

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>Uwagi

Typ opisuje ogólny iterator odwrotny, który może być używany z ogólnym interfejsem klasy kontenera tego szablonu.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_set::generic_reverse_iterator gcit = gc1->rbegin();
    Myhash_set::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="hash_setgeneric_value-stlclr"></a><a name="generic_value"></a> hash_set:: generic_value (STL/CLR)

Typ elementu do użycia z interfejsem ogólnym dla kontenera.

### <a name="syntax"></a>Składnia

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>Uwagi

Typ opisuje obiekt typu `GValue` , który opisuje wartość przechowywanego elementu do użycia z interfejsem ogólnym dla tej klasy kontenera szablonu.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_generic_value.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Myhash_set::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Myhash_set::generic_iterator gcit = gc1->begin();
    Myhash_set::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="hash_sethash_delegate-stlclr"></a><a name="hash_delegate"></a> hash_set:: hash_delegate (STL/CLR)

Wyszukuje element, który odpowiada określonemu kluczowi.

### <a name="syntax"></a>Składnia

```cpp
hasher^ hash_delegate();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca delegata użyty do przekonwertowania wartości klucza na liczbę całkowitą. Jest on używany do mieszania klucza.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_hash_delegate.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_sethash_set-stlclr"></a><a name="hash_set"></a> hash_set:: hash_set (STL/CLR)

Konstruuje obiekt kontenera.

### <a name="syntax"></a>Składnia

```cpp
hash_set();
explicit hash_set(key_compare^ pred);
hash_set(key_compare^ pred, hasher^ hashfn);
hash_set(hash_set<Key>% right);
hash_set(hash_set<Key>^ right);
template<typename InIter>
    hash_sethash_set(InIter first, InIter last);
template<typename InIter>
    hash_set(InIter first, InIter last,
        key_compare^ pred);
template<typename InIter>
    hash_set(InIter first, InIter last,
        key_compare^ pred, hasher^ hashfn);
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right);
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred, hasher^ hashfn);
```

#### <a name="parameters"></a>Parametry

*pierwszego*<br/>
Początek zakresu do wstawienia.

*hashfn*<br/>
Funkcja skrótu do mapowania kluczy na przedziały.

*ostatniego*<br/>
Koniec zakresu do wstawienia.

*pred*<br/>
Predykat porządkowania dla kontrolowanej sekwencji.

*Kliknij*<br/>
Obiekt lub zakres do wstawienia.

### <a name="remarks"></a>Uwagi

Konstruktor:

`hash_set();`

Inicjuje kontrolowaną sekwencję bez elementów, z predykatem kolejności domyślnej `key_compare()` i z domyślną funkcją skrótu. Służy do określania pustej początkowej kontrolowanej sekwencji z zastosowaniem domyślnego predykatu porządkowania i funkcji skrótu.

Konstruktor:

`explicit hash_set(key_compare^ pred);`

Inicjuje kontrolowaną sekwencję bez elementów, z predykatem porządkowania *pred* i z domyślną funkcją skrótu. Służy do określania pustej początkowej kontrolowanej sekwencji z określonym predykatem porządkowania i domyślną funkcją skrótu.

Konstruktor:

`hash_set(key_compare^ pred, hasher^ hashfn);`

Inicjuje kontrolowaną sekwencję bez elementów, z predykatem porządkowania *pred* i funkcją hash *hashfn*. Służy do określania pustej początkowej kontrolowanej sekwencji z określonym predykatem porządkowania i funkcją skrótu.

Konstruktor:

`hash_set(hash_set<Key>% right);`

Inicjuje kontrolowaną sekwencję z sekwencją [ `right.begin()` , `right.end()` ) przy użyciu domyślnego predykatu porządkowania i z domyślną funkcją skrótu. Służy do określenia początkowej kontrolowanej sekwencji, która jest kopią sekwencji kontrolowanej przez obiekt hash_set *po prawej stronie*, przy użyciu domyślnego predykatu porządkowania i funkcji mieszania.

Konstruktor:

`hash_set(hash_set<Key>^ right);`

Inicjuje kontrolowaną sekwencję z sekwencją [ `right->begin()` , `right->end()` ) przy użyciu domyślnego predykatu porządkowania i z domyślną funkcją skrótu. Służy do określenia początkowej kontrolowanej sekwencji, która jest kopią sekwencji kontrolowanej przez obiekt hash_set *po prawej stronie*, przy użyciu domyślnego predykatu porządkowania i funkcji mieszania.

Konstruktor:

`template<typename InIter> hash_set(InIter first, InIter last);`

Inicjuje kontrolowaną sekwencję z sekwencją [ `first` , `last` ) przy użyciu domyślnego predykatu porządkowania i z domyślną funkcją skrótu. Służy do przetworzenia kontrolowanej sekwencji kopii kolejnej sekwencji z domyślnym predykatem porządkowania i funkcją skrótu.

Konstruktor:

`template<typename InIter> hash_set(InIter first, InIter last, key_compare^ pred);`

Inicjuje kontrolowaną sekwencję z sekwencją [ `first` , `last` ), z predykatem porządkowania *pred* oraz z domyślną funkcją skrótu. Służy do przetworzenia kontrolowanej sekwencji kopii innej sekwencji z określonym predykatem porządkowania i domyślną funkcją skrótu.

Konstruktor:

`template<typename InIter> hash_set(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`

Inicjuje kontrolowaną sekwencję z sekwencją [ `first` , `last` ), z predykatem porządkowania *pred* i funkcją hash *hashfn*. Służy do przetworzenia kontrolowanej sekwencji kopii innej sekwencji z określonym predykatem porządkowania i funkcją skrótu.

Konstruktor:

`hash_set(System::Collections::Generic::IEnumerable<Key>^ right);`

Inicjuje kontrolowaną sekwencję z sekwencją wyznaczonej przez moduł wyliczający *po prawej stronie*, przy użyciu domyślnego predykatu porządkowania i z domyślną funkcją skrótu. Służy do przetworzenia kontrolowanej sekwencji kopii kolejnej sekwencji opisanej przez moduł wyliczający z domyślnym predykatem porządkowania i funkcją skrótu.

Konstruktor:

`hash_set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

Inicjuje kontrolowaną sekwencję z sekwencją wyznaczonej przez moduł wyliczający *po prawej stronie* z predykatem porządkowania *pred* oraz z domyślną funkcją skrótu. Służy do przetworzenia kontrolowanej sekwencji kopii kolejnej sekwencji opisanej przez moduł wyliczający z określonym predykatem porządkowania i domyślną funkcją skrótu.

Konstruktor:

`hash_set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`

Inicjuje kontrolowaną sekwencję z sekwencją wyznaczonej przez moduł wyliczający *po prawej stronie*, z predykatem porządkowania *pred* i funkcją hash *hashfn*. Służy do przetworzenia kontrolowanej sekwencji kopii kolejnej sekwencji opisanej przez moduł wyliczający z określonym predykatem porządkowania i funkcją skrótu.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_construct.cpp
// compile with: /clr
#include <cliext/hash_set>

int myfun(wchar_t key)
    { // hash a key
    return (key ^ 0xdeadbeef);
    }

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
// construct an empty container
    Myhash_set c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Myhash_set c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule and hash function
    Myhash_set c2h(cliext::greater_equal<wchar_t>(),
        gcnew Myhash_set::hasher(&myfun));
    System::Console::WriteLine("size() = {0}", c2h.size());

    c2h.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an iterator range
    Myhash_set c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Myhash_set c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule and hash function
    Myhash_set c4h(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>(),
        gcnew Myhash_set::hasher(&myfun));
    for each (wchar_t elem in c4h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct with an enumeration
    Myhash_set c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Myhash_set c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule and hash function
    Myhash_set c6h(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>(),
                gcnew Myhash_set::hasher(&myfun));
    for each (wchar_t elem in c6h)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine();

    // construct from a generic container
    Myhash_set c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Myhash_set c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
a b c
size() = 0
a b c
size() = 0
c b a

a b c
a b c
c b a

a b c
a b c
c b a

a b c
a b c
```

## <a name="hash_sethasher-stlclr"></a><a name="hasher"></a> hash_set:: Hasher (STL/CLR)

Delegat skrótu dla klucza.

### <a name="syntax"></a>Składnia

```cpp
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>
    hasher;
```

### <a name="remarks"></a>Uwagi

Typ opisuje delegata, który konwertuje wartość klucza na liczbę całkowitą.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_hasher.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::hasher^ myhash = c1.hash_delegate();

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 1616896120
hash(L'b') = 570892832
```

## <a name="hash_setinsert-stlclr"></a><a name="insert"></a> hash_set:: Insert (STL/CLR)

Dodaje elementy.

### <a name="syntax"></a>Składnia

```cpp
cliext::pair<iterator, bool> insert(value_type val);
iterator insert(iterator where, value_type val);
template<typename InIter>
    void insert(InIter first, InIter last);
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);
```

#### <a name="parameters"></a>Parametry

*pierwszego*<br/>
Początek zakresu do wstawienia.

*ostatniego*<br/>
Koniec zakresu do wstawienia.

*Kliknij*<br/>
Wyliczenie do wstawienia.

*użyte*<br/>
Wartość klucza do wstawienia.

*miejscu*<br/>
Gdzie w kontenerze do wstawienia (tylko Wskazówka).

### <a name="remarks"></a>Uwagi

Każda funkcja członkowska wstawia sekwencję określoną przez pozostałe operandy.

Pierwsza funkcja członkowska przedsięwzięciach do wstawienia elementu z wartością *Val* i zwraca parę wartości `X` . Jeśli `X.second` ma wartość true, `X.first` oznacza nowo wstawiony element; w przeciwnym razie `X.first` oznacza element o równoważnej kolejności, która już istnieje, a nowy element nie zostanie wstawiony. Służy do wstawiania pojedynczego elementu.

Druga funkcja członkowska wstawia element z wartością *Val* przy użyciu instrukcji *WHERE* jako wskazówkę (w celu zwiększenia wydajności) i zwraca iterator, który wyznacza nowo wstawiony element. Służy do wstawiania pojedynczego elementu, który może być przyległy do elementu, który znasz.

Trzecia funkcja członkowska wstawia sekwencję [ `first` , `last` ). Służy do wstawiania elementów, które zostały skopiowane z innej sekwencji.

Czwarta funkcja członkowska wstawia sekwencję wydaną po *prawej stronie*. Służy do wstawiania sekwencji opisanej przez moduł wyliczający.

Każde wstawienie elementu ma czas proporcjonalny do logarytmu liczby elementów w kontrolowanej sekwencji. Wstawianie może odbywać się w amortyzowanym stałym czasie, Jednakże z uwzględnieniem wskazówki, która wyznacza element przyległy do punktu wstawiania.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_insert.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
typedef Myhash_set::pair_iter_bool Pairib;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
    Pairib pair1 = c1.insert(L'x');
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",
        *pair1.first, pair1.second);

    pair1 = c1.insert(L'b');
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",
        *pair1.first, pair1.second);

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value with hint
    System::Console::WriteLine("insert(begin(), L'y') = {0}",
        *c1.insert(c1.begin(), L'y'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an iterator range
    Myhash_set c2;
    Myhash_set::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an enumeration
    Myhash_set c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
insert(L'x') = [x True]
insert(L'b') = [b False]
a b c x
insert(begin(), L'y') = y
a b c x y
a b c x
a b c x y
```

## <a name="hash_setiterator-stlclr"></a><a name="iterator"></a> hash_set:: iterator (STL/CLR)

Typ iteratora dla kontrolowanej sekwencji.

### <a name="syntax"></a>Składnia

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>Uwagi

Typ opisuje obiekt nieokreślonego typu `T1` , który może obsłużyć iterator dwukierunkowy dla kontrolowanej sekwencji.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Myhash_set::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setkey_comp-stlclr"></a><a name="key_comp"></a> hash_set:: key_comp (STL/CLR)

Kopiuje delegata porządkowania dla dwóch kluczy.

### <a name="syntax"></a>Składnia

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca delegat porządkowania używany do uporządkowania kontrolowanej sekwencji. Służy do porównywania dwóch kluczy.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_key_comp.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_set c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="hash_setkey_compare-stlclr"></a><a name="key_compare"></a> hash_set:: key_compare (STL/CLR)

Delegat porządkowania dla dwóch kluczy.

### <a name="syntax"></a>Składnia

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla delegata, który określa kolejność argumentów klucza.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_key_compare.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Myhash_set c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="hash_setkey_type-stlclr"></a><a name="key_type"></a> hash_set:: key_type (STL/CLR)

Typ klucza sortowania.

### <a name="syntax"></a>Składnia

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla *klucza* parametru szablonu.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_key_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using key_type
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myhash_set::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setload_factor-stlclr"></a><a name="load_factor"></a> hash_set:: load_factor (STL/CLR)

Oblicza średnią liczbę elementów na przedział.

### <a name="syntax"></a>Składnia

```cpp
float load_factor();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca `(float)` [hash_set:: size (STL/CLR)](#size) `() /` [hash_set:: bucket_count (STL/CLR)](#bucket_count) `()` . Służy do określania średniego rozmiaru przedziału.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_load_factor.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_setlower_bound-stlclr"></a><a name="lower_bound"></a> hash_set:: lower_bound (STL/CLR)

Znajduje początek zakresu, który odpowiada określonemu kluczowi.

### <a name="syntax"></a>Składnia

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>Parametry

*głównych*<br/>
Wartość klucza do wyszukania.

### <a name="remarks"></a>Uwagi

Funkcja członkowska określa pierwszy element `X` w kontrolowanej sekwencji, który miesza się do tego samego zasobnika co *klucz* i ma równoważne porządkowanie do *klucza*. Jeśli taki element nie istnieje, zwraca [hash_set:: end (STL/CLR)](#end) `()` ; w przeciwnym razie zwraca iterator, który wyznacza `X` . Służy do lokalizowania początku sekwencji elementów aktualnie w kontrolowanej sekwencji, która pasuje do określonego klucza.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_lower_bound.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    System::Console::WriteLine("*lower_bound(L'a') = {0}",
        *c1.lower_bound(L'a'));
    System::Console::WriteLine("*lower_bound(L'b') = {0}",
        *c1.lower_bound(L'b'));
    return (0);
    }
```

```Output
a b c
lower_bound(L'x')==end() = True
*lower_bound(L'a') = a
*lower_bound(L'b') = b
```

## <a name="hash_setmake_value-stlclr"></a><a name="make_value"></a> hash_set:: make_value (STL/CLR)

Konstruuje obiekt wartości.

### <a name="syntax"></a>Składnia

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>Parametry

*głównych*<br/>
Wartość klucza do użycia.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca `value_type` obiekt, którego klucz jest *kluczem*. Służy do redagowania obiektu odpowiedniego do użycia z kilkoma innymi funkcjami składowymi.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_make_value.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(Myhash_set::make_value(L'a'));
    c1.insert(Myhash_set::make_value(L'b'));
    c1.insert(Myhash_set::make_value(L'c'));

    // display contents " a b c"
    for each (Myhash_set::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setmax_load_factor-stlclr"></a><a name="max_load_factor"></a> hash_set:: max_load_factor (STL/CLR)

Pobiera lub ustawia maksymalną liczbę elementów na przedział.

### <a name="syntax"></a>Składnia

```cpp
float max_load_factor();
void max_load_factor(float new_factor);
```

#### <a name="parameters"></a>Parametry

*new_factor*<br/>
Nowy maksymalny współczynnik obciążenia do zapisania.

### <a name="remarks"></a>Uwagi

Pierwsza funkcja członkowska zwraca bieżący przechowywany maksymalny współczynnik obciążenia. Służy do określenia maksymalnego średniego rozmiaru przedziału.

Druga funkcja członkowska zastępuje maksymalny współczynnik obciążenia magazynu *new_factor*. Automatyczne ponowne tworzenie skrótów nie odbywa się do kolejnych operacji wstawiania.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_max_load_factor.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

## <a name="hash_setoperator-stlclr"></a><a name="op"></a> hash_set:: operator = (STL/CLR)

Zastępuje kontrolowaną sekwencję.

### <a name="syntax"></a>Składnia

```cpp
hash_set<Key>% operator=(hash_set<Key>% right);
```

#### <a name="parameters"></a>Parametry

*Kliknij*<br/>
Kontener do skopiowania.

### <a name="remarks"></a>Uwagi

Operator elementu członkowskiego kopiuje *prawo* do obiektu, a następnie zwraca **`*this`** . Służy do zastępowania kontrolowanej sekwencji kopią kontrolowanej sekwencji *po prawej stronie*.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_operator_as.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (Myhash_set::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Myhash_set c2;
    c2 = c1;
// display contents " a b c"
    for each (Myhash_set::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="hash_setrbegin-stlclr"></a><a name="rbegin"></a> hash_set:: rbegin (STL/CLR)

Określa początek odwróconej sekwencji kontrolowanej.

### <a name="syntax"></a>Składnia

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca iterator odwrotny, który wyznacza ostatni element kontrolowanej sekwencji lub tuż poza początkiem pustej sekwencji. W związku z tym określa `beginning` odwrotną sekwencję. Służy do uzyskania iteratora, który wyznacza `current` początek kontrolowanej sekwencji widoczny w kolejności odwrotnej, ale jego stan może ulec zmianie w przypadku zmiany długości kontrolowanej sekwencji.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_rbegin.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Myhash_set::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
```

## <a name="hash_setreference-stlclr"></a><a name="reference"></a> hash_set:: Reference (STL/CLR)

Typ odwołania do elementu.

### <a name="syntax"></a>Składnia

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>Uwagi

Typ opisuje odwołanie do elementu.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_reference.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Myhash_set::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myhash_set::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="hash_setrehash-stlclr"></a><a name="rehash"></a> hash_set:: rehash (STL/CLR)

Przebudowuje tabelę mieszania.

### <a name="syntax"></a>Składnia

```cpp
void rehash();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska ponownie kompiluje tablicę skrótów, upewniając się, że [hash_set:: load_factor (STL/CLR)](#load_factor) `() <=` [hash_set:: max_load_factor (STL/CLR)](#max_load_factor). W przeciwnym razie tabela skrótów zwiększa rozmiar tylko w razie konieczności po wstawieniu. (Rozmiar nigdy nie zmniejsza się automatycznie). Służy do dostosowywania rozmiaru tabeli skrótów.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_rehash.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect current parameters
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // change max_load_factor and redisplay
    c1.max_load_factor(0.25f);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    System::Console::WriteLine();

    // rehash and redisplay
    c1.rehash(100);
    System::Console::WriteLine("bucket_count() = {0}", c1.bucket_count());
    System::Console::WriteLine("load_factor() = {0}", c1.load_factor());
    System::Console::WriteLine("max_load_factor() = {0}",
        c1.max_load_factor());
    return (0);
    }
```

```Output
a b c
bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 4

bucket_count() = 16
load_factor() = 0.1875
max_load_factor() = 0.25

bucket_count() = 128
load_factor() = 0.0234375
max_load_factor() = 0.25
```

## <a name="hash_setrend-stlclr"></a><a name="rend"></a> hash_set:: rend (STL/CLR)

Określa koniec odwróconej kontrolowanej sekwencji.

### <a name="syntax"></a>Składnia

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca iterator odwrotny, który wskazuje tuż poza początkiem kontrolowanej sekwencji. W związku z tym określa `end` odwrotną sekwencję. Służy do uzyskania iteratora, który wyznacza `current` koniec kontrolowanej sekwencji widoczny w odwrotnej kolejności, ale jego stan może ulec zmianie w przypadku zmiany długości kontrolowanej sekwencji.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_rend.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Myhash_set::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
```

## <a name="hash_setreverse_iterator-stlclr"></a><a name="reverse_iterator"></a> hash_set:: reverse_iterator (STL/CLR)

Typ iteratora odwrotnego dla kontrolowanej sekwencji.

### <a name="syntax"></a>Składnia

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>Uwagi

Typ opisuje obiekt nieokreślonego typu `T3` , który może być używany jako iterator odwrotny dla kontrolowanej sekwencji.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_reverse_iterator.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Myhash_set::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="hash_setsize-stlclr"></a><a name="size"></a> hash_set:: size (STL/CLR)

Liczy liczbę elementów.

### <a name="syntax"></a>Składnia

```cpp
size_type size();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca długość kontrolowanej sekwencji. Służy do określania liczby elementów aktualnie w kontrolowanej sekwencji. Jeśli dowiesz się, czy sekwencja ma rozmiar różny od zera, zobacz [hash_set:: empty (STL/CLR)](#empty) `()` .

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_size.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 3 starting with 3
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="hash_setsize_type-stlclr"></a><a name="size_type"></a> hash_set:: size_type (STL/CLR)

Typ podpisanej odległości między dwoma elementami.

### <a name="syntax"></a>Składnia

```cpp
typedef int size_type;
```

### <a name="remarks"></a>Uwagi

Typ opisuje nieujemną liczbę elementów.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_size_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Myhash_set::size_type diff = 0;
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="hash_setswap-stlclr"></a><a name="swap"></a> hash_set:: swap (STL/CLR)

Zamienia zawartości dwóch kontenerów.

### <a name="syntax"></a>Składnia

```cpp
void swap(hash_set<Key>% right);
```

#### <a name="parameters"></a>Parametry

*Kliknij*<br/>
Kontener, za pomocą którego ma zostać zamieniony zawartość.

### <a name="remarks"></a>Uwagi

Funkcja członkowska zamienia kontrolowane sekwencje między **`this`** i *po prawej*. Robi to w stałym czasie i nie zgłasza wyjątków. Jest ona używana jako Szybka metoda wymiany zawartości dwóch kontenerów.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_swap.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Myhash_set c2;
    c2.insert(L'd');
    c2.insert(L'e');
    c2.insert(L'f');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
d e f
d e f
a b c
```

## <a name="hash_setto_array-stlclr"></a><a name="to_array"></a> hash_set:: to_array (STL/CLR)

Kopiuje przekontrolowaną sekwencję do nowej tablicy.

### <a name="syntax"></a>Składnia

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca tablicę zawierającą kontrolowaną sekwencję. Służy do uzyskania kopii kontrolowanej sekwencji w formularzu tablicowym.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_to_array.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c d
a b c
```

## <a name="hash_setupper_bound-stlclr"></a><a name="upper_bound"></a> hash_set:: upper_bound (STL/CLR)

Znajduje koniec zakresu, który odpowiada określonemu kluczowi.

### <a name="syntax"></a>Składnia

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>Parametry

*głównych*<br/>
Wartość klucza do wyszukania.

### <a name="remarks"></a>Uwagi

Funkcja członkowska określa ostatni element `X` w kontrolowanej sekwencji, który miesza się do tego samego zasobnika co *klucz* i ma równoważne porządkowanie do *klucza*. Jeśli taki element nie istnieje lub `X` jest ostatnim elementem w kontrolowanej sekwencji, zwraca [hash_set:: end (STL/CLR)](#end) `()` ; w przeciwnym razie zwraca iterator, który wyznacza pierwszy element poza `X` . Służy do lokalizowania końca sekwencji elementów aktualnie w kontrolowanej sekwencji, która pasuje do określonego klucza.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_upper_bound.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    System::Console::WriteLine("*upper_bound(L'a') = {0}",
        *c1.upper_bound(L'a'));
    System::Console::WriteLine("*upper_bound(L'b') = {0}",
        *c1.upper_bound(L'b'));
    return (0);
    }
```

```Output
a b c
upper_bound(L'x')==end() = True
*upper_bound(L'a') = b
*upper_bound(L'b') = c
```

## <a name="hash_setvalue_comp-stlclr"></a><a name="value_comp"></a> hash_set:: value_comp (STL/CLR)

Kopiuje delegata porządkowania dla dwóch wartości elementów.

### <a name="syntax"></a>Składnia

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca delegat porządkowania używany do uporządkowania kontrolowanej sekwencji. Służy do porównywania dwóch wartości elementów.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_value_comp.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="hash_setvalue_compare-stlclr"></a><a name="value_compare"></a> hash_set:: value_compare (STL/CLR)

Delegat porządkowania dla dwóch wartości elementów.

### <a name="syntax"></a>Składnia

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla delegata, który określa kolejność argumentów wartości.

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_value_compare.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    Myhash_set::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = True
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="hash_setvalue_type-stlclr"></a><a name="value_type"></a> hash_set:: value_type (STL/CLR)

Typ elementu.

### <a name="syntax"></a>Składnia

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla `generic_value` .

### <a name="example"></a>Przykład

```cpp
// cliext_hash_set_value_type.cpp
// compile with: /clr
#include <cliext/hash_set>

typedef cliext::hash_set<wchar_t> Myhash_set;
int main()
    {
    Myhash_set c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using value_type
    for (Myhash_set::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myhash_set::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

---
title: tuple_element — Klasa
ms.date: 11/04/2016
f1_keywords:
- utility/std::tuple_element
helpviewer_keywords:
- std::tuple_element
ms.assetid: 4c51a6c1-ce81-462f-8c6c-291d69f2b77c
ms.openlocfilehash: be9d9fe56d35e96e4179eb511edccd475a369f32
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008286"
---
# <a name="tuple_element-class"></a>tuple_element — Klasa

Zawija `tuple` element. Specjalizacje zawijają `array` elementy i `pair` elementy.

## <a name="syntax"></a>Składnia

```cpp
// CLASS tuple_element (find element by index)
template <size_t Index, class Tuple>
   struct tuple_element;

// tuple_element for const
template <size_t Index, class Tuple>
   struct tuple_element<Index, const Tuple>;

// tuple_element for volatile
template <size_t Index, class Tuple>
   struct tuple_element<Index, volatile Tuple>;

// tuple_element for const volatile
template <size_t Index, class Tuple>
   struct tuple_element<Index, const volatile Tuple>;

// Helper typedef
template <size_t Index, class Tuple>
   using tuple_element_t = typename tuple_element<Index, Tuple>::type;

// Specialization for arrays
template <size_t Index, class Elem, size_t Size>
   struct tuple_element<Index, array<Elem, Size>>;

// Specializations for pairs
// struct to determine type of element 0 in pair
template <class T1, class T2>
   struct tuple_element<0, pair<T1, T2>>;

// struct to determine type of element 1 in pair
template <class T1, class T2>
   struct tuple_element<1, pair<T1, T2>>;
```

### <a name="parameters"></a>Parametry

*Indeks*\
Indeks wyoznaczonego elementu.

*Spoin*\
Typ krotki.

*Elem*\
Typ elementu tablicy.

*Zmienia*\
Rozmiar tablicy.

*Połączeń*\
Typ pierwszego elementu w parze.

*T2*\
Typ drugiego elementu w parze.

## <a name="remarks"></a>Uwagi

Szablon klasy `tuple_element` zawiera zagnieżdżony element typedef `type` , który jest synonimem dla typu w *indeksie* indeksu *krotki*typu krotki.

Element typedef `tuple_element_t` jest wygodnym aliasem dla `tuple_element<Index, Tuple>::type` .

Specjalizacja szablonu klasy dla tablic zawiera interfejs do `array` postaci spójnej kolekcji `Size` elementów, z których każdy ma ten sam typ. Każda specjalizacja ma zagnieżdżony element typedef `type` , który jest synonimem dla typu elementu *indeksu* `array` , z wszelkimi nietrwałymi zastrzeżeniami const.

Specjalizacje szablonu dla `pair` typów każdy zapewniają pojedynczy element członkowski typedef, `type` , który jest synonimem dla typu elementu w określonej pozycji w parze, z dowolnymi nieprawidłowymi zastrzeżeniami const i/lub volatile. Element typedef `tuple_element_t` jest wygodnym aliasem dla `tuple_element<N, pair<T1, T2>>::type` .

Użyj [ &lt; narzędzia &gt; Get Function](../standard-library/utility-functions.md#get) , aby zwrócić element w określonej pozycji lub o określonym typie.

## <a name="example-get-an-element-from-a-tuple"></a>Przykład: pobieranie elementu z krotki

```cpp
#include <tuple>
#include <string>
#include <iostream>

using namespace std;
typedef tuple<int, double, string> MyTuple;

int main() {
    MyTuple c0{ 0, 1.5, "Tail" };

    tuple_element_t<0, MyTuple> val = get<0>(c0); //get by index
    tuple_element_t<1, MyTuple> val2 = get<1>(c0);
    tuple_element_t<2, MyTuple> val3 = get<string>(c0); // get by type

    cout << val << " " << val2 << " " << val3 << endl;
}
```

```Output
0 1.5 Tail
```

## <a name="example-get-an-element-from-an-array"></a>Przykład: pobieranie elementu z tablicy

```cpp
#include <array>
#include <iostream>

using namespace std;
typedef array<int, 4> MyArray;

int main()
{
    MyArray c0 { 0, 1, 2, 3 };

    for (const auto& e : c0)
    {
        cout << e << " ";
    }
    cout << endl;

    // display first element "0"
    tuple_element<0, MyArray>::type val = c0.front();
    cout << val << endl;
}
```

```Output
0 1 2 3
0
```

## <a name="example-get-an-element-from-a-pair"></a>Przykład: pobieranie elementu z pary

```cpp
#include <utility>
#include <iostream>

using namespace std;

typedef pair<int, double> MyPair;
int main() {
    MyPair c0(0, 1.333);

    // display contents "0 1"
    cout << get<0>(c0) << " ";
    cout << get<1>(c0) << endl;

    // display first element "0 " by index
    tuple_element<0, MyPair>::type val = get<0>(c0);
    cout << val << " ";

    // display second element by type
    tuple_element<1, MyPair>::type val2 = get<double>(c0);
    cout << val2 << endl;
}
```

```Output
0 1.333
0 1.333
```

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<tuple>

**Nagłówek:** \<array> (dla specjalizacji macierzy)

**Nagłówek:** \<utility> (dla specjalizacji par)

**Przestrzeń nazw:** std

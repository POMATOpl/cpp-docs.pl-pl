---
description: Dowiedz się więcej na temat klasy seed_seq
title: seed_seq — Klasa
ms.date: 11/04/2016
f1_keywords:
- random/std::seed_seq
- random/std::seed_seq::result_type
- random/std::seed_seq::generate
- random/std::seed_seq::size
- random/std::seed_seq::param
helpviewer_keywords:
- std::seed_seq [C++]
- std::seed_seq [C++], result_type
- std::seed_seq [C++], generate
- std::seed_seq [C++], size
- std::seed_seq [C++], param
ms.assetid: cba114f7-9ac6-4f2f-b773-9c84805401d6
ms.openlocfilehash: c92bda66b37162bcaaf9c614185f2c31f29d22c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197039"
---
# <a name="seed_seq-class"></a>seed_seq — Klasa

Przechowuje wektor niepodpisanych wartości całkowitych, które mogą dostarczyć losowy inicjator dla silnika liczb losowych.

## <a name="syntax"></a>Składnia

```cpp
class seed_seq
   {
public:
   // types
   typedef unsigned int result_type;

   // constructors
   seed_seq();
   template <class T>
      seed_seq(initializer_list<T> initlist);
   template <class InputIterator>
      seed_seq(InputIterator begin, InputIterator end);

   // generating functions
   template <class RandomAccessIterator>
      void generate(RandomAccessIterator begin, RandomAccessIterator end);

   // property functions
   size_t size() const;
   template <class OutputIterator>
      void param(OutputIterator dest) const;

   // no copy functions
   seed_seq(const seed_seq&) = delete;
   void operator=(const seed_seq&) = delete;
   };
```

## <a name="types"></a>Typy

```cpp
typedef unsigned int result_type;
```

Typ elementów sekwencji inicjatora. 32-bitowy typ liczby całkowitej bez znaku.

## <a name="constructors"></a>Konstruktory

```cpp
seed_seq();
```

Konstruktor domyślny inicjuje, że ma pustą sekwencję wewnętrzną.

```cpp
template<class T>
seed_seq(initializer_list<T> initlist);
```

Używa `initlist` do ustawiania sekwencji wewnętrznej.
`T` musi być typem liczbą całkowitą.

```cpp
template<class InputIterator>
seed_seq(InputIterator begin, InputIterator end);
```

Inicjuje wewnętrzną sekwencję przy użyciu wszystkich elementów w podanym zakresie iteratora wejściowego.
`iterator_traits<InputIterator>::value_type` musi być typem liczbą całkowitą.

## <a name="members"></a>Elementy członkowskie

### <a name="generating-functions"></a>Generowanie funkcji

```cpp
template<class RandomAccessIterator>
void generate(RandomAccessIterator begin,
          RandomAccessIterator end);
```

Wypełnia elementy podanej sekwencji przy użyciu wewnętrznego algorytmu. Ten algorytm ma wpływ na sekwencję wewnętrzną, która `seed_seq` została zainicjowana.
Nic nie robi `begin == end` .

### <a name="property-functions"></a>Funkcje właściwości

```cpp
size_t size() const;
```

Zwraca liczbę elementów w `seed_seq` .

```cpp
template<class OutputIterator>
void param(OutputIterator dest) const;
```

Kopiuje sekwencję wewnętrzną do iteratora danych wyjściowych `dest` .

## <a name="example"></a>Przykład

Poniższy przykład kodu wykonuje trzy konstruktory i generuje dane wyjściowe z wynikowych `seed_seq` wystąpień po przypisaniu do tablicy. Przykład, który używa `seed_seq` z generatorem liczb losowych, znajduje się w temacie [\<random>](../standard-library/random.md) .

```cpp
#include <iostream>
#include <random>
#include <string>
#include <array>

using namespace std;

void test(const seed_seq& sseq) {
    cout << endl << "seed_seq::size(): " << sseq.size() << endl;

    cout << "seed_seq::param(): ";
    ostream_iterator<unsigned int> out(cout, " ");
    sseq.param(out);
    cout << endl;

    cout << "Generating a sequence of 5 elements into an array: " << endl;
    array<unsigned int, 5> seq;
    sseq.generate(seq.begin(), seq.end());
    for (unsigned x : seq) { cout << x << endl; }
}

int main()
{
    seed_seq seed1;
    test(seed1);

    seed_seq seed2 = { 1701, 1729, 1791 };
    test(seed2);

    string sstr = "A B C D"; // seed string
    seed_seq seed3(sstr.begin(), sstr.end());
    test(seed3);
}
```

```Output
seed_seq::size(): 0
seed_seq::param():
Generating a sequence of 5 elements into an array:
505382999
163489202
3932644188
763126080
73937346

seed_seq::size(): 3
seed_seq::param(): 1701 1729 1791
Generating a sequence of 5 elements into an array:
1730669648
1954224479
2809786021
1172893117
2393473414

seed_seq::size(): 7
seed_seq::param(): 65 32 66 32 67 32 68
Generating a sequence of 5 elements into an array:
3139879222
3775111734
1084804564
2485037668
1985355432
```

## <a name="remarks"></a>Uwagi

Funkcje członkowskie tej klasy nie generują wyjątków.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<random>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[\<random>](../standard-library/random.md)

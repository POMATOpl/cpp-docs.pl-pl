---
description: Dowiedz się więcej na temat &lt; &gt; funkcji krotki
title: '&lt;&gt;funkcje krotki'
ms.date: 11/04/2016
f1_keywords:
- tuple/std::get
- tuple/std::make_tuple
- tuple/std::tie
ms.assetid: bc6be38f-5258-4c14-b81b-63caa335fd44
helpviewer_keywords:
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
ms.openlocfilehash: cf58cab5f222594a935156cf7e7f2e886639da2b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168959"
---
# <a name="lttuplegt-functions"></a>&lt;&gt;funkcje krotki

## <a name="apply"></a><a name="apply"></a> stosowa

```cpp
template <class F, class Tuple> constexpr decltype(auto) apply(F&& f, Tuple&& t);
```

### <a name="remarks"></a>Uwagi

Wywołuje funkcję *F* z krotką *t*.

## <a name="forward_as_tuple"></a><a name="forward"></a> forward_as_tuple

```cpp
template <class... TTypes>
    constexpr tuple<TTypes&&...> forward_as_tuple(TTypes&&...) noexcept;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość `tuple<TTypes&&...>(std::forward<TTypes>(t)...)`.

### <a name="remarks"></a>Uwagi

Konstruuje krotkę odwołań do argumentów w *t* odpowiednie do przesyłania dalej jako argumenty do funkcji.

## <a name="get"></a><a name="get"></a> Pobierz

Pobiera element z `tuple` obiektu, według indeksu lub (w języku c++ 14) według typu.

```cpp
// by index:
// get reference to Index element of tuple
template <size_t Index, class... Types>
   constexpr tuple_element_t<Index, tuple<Types...>>& get(tuple<Types...>& Tuple) noexcept;

// get const reference to Index element of tuple
template <size_t Index, class... Types>
   constexpr const tuple_element_t<Index, tuple<Types...>>& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to Index element of tuple
template <size_t Index, class... Types>
   constexpr tuple_element_t<Index, tuple<Types...>>&& get(tuple<Types...>&& Tuple) noexcept;

// (C++14) by type:
// get reference to T element of tuple
template <class T, class... Types>
   constexpr T& get(tuple<Types...>& Tuple) noexcept;

// get const reference to T element of tuple
template <class T, class... Types>
   constexpr const T& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to T element of tuple
template <class T, class... Types>
   constexpr T&& get(tuple<Types...>&& Tuple) noexcept;
```

### <a name="parameters"></a>Parametry

*Indeks*\
Indeks elementu, który ma zostać pobrany.

*Typ*\
Sekwencja typów zadeklarowanych w spójnej kolekcji w kolejności deklaracji.

*&*\
Typ elementu, który ma zostać pobrany.

*Spoin*\
A `std::tuple` , która zawiera dowolną liczbę elementów.

### <a name="remarks"></a>Uwagi

Funkcje szablonu zwracają odwołanie do wartości w *indeksie* indeksu lub typu *T* w `tuple` obiekcie.

Wywołanie `get<T>(Tuple)` spowoduje wygenerowanie błędu kompilatora, jeśli krotka zawiera więcej lub mniej niż jeden element typu T.

### <a name="example"></a>Przykład

```cpp
#include <tuple>
#include <iostream>
#include <string>

using namespace std;

int main() {
    tuple<int, double, string> tup(0, 1.42, "Call me Tuple");

    // get elements by index
    cout << " " << get<0>(tup);
    cout << " " << get<1>(tup);
    cout << " " << get<2>(tup) << endl;

    // get elements by type
    cout << " " << get<int>(tup);
    cout << " " << get<double>(tup);
    cout << " " << get<string>(tup) << endl;
}
```

```Output
0 1.42 Call me Tuple
0 1.42 Call me Tuple
```

## <a name="make_from_tuple"></a><a name="make_from_tuple"></a> make_from_tuple

```cpp
template <class T, class Tuple> constexpr T make_from_tuple(Tuple&& t);
```

### <a name="remarks"></a>Uwagi

Analogicznie jak `return make_from_tuple_impl<T>(forward<Tuple>(t), make_index_sequence<tuple_size_v<decay_t<Tuple>>>{})` .

## <a name="make_tuple"></a><a name="make_tuple"></a> make_tuple

Tworzy `tuple` wartości elementu z.

```cpp
template <class T1, class T2, ..., class TN>
   tuple<V1, V2, ..., VN> make_tuple(const T1& t1, const T2& t2, ..., const TN& tN);
```

### <a name="parameters"></a>Parametry

*TN*\
Typ parametru n funkcji.

*tN*\
Wartość parametru n funkcji.

### <a name="remarks"></a>Uwagi

Funkcja szablonu zwraca `tuple<V1, V2, ..., VN>(t1, t2, ..., tN)` , gdzie każdy typ `Vi` jest, `X&` gdy odpowiedni typ to `Ti` `cv` `reference_wrapper<X>` ; w przeciwnym razie jest `Ti` .

Jedną z zalet tego `make_tuple` jest to, że typy obiektów, które są przechowywane, są określane automatycznie przez kompilator i nie muszą być jawnie określone. Nie używaj jawnych argumentów szablonu, takich jak `make_tuple<int, int>(1, 2)` użycie, `make_tuple` ponieważ nie jest to niepotrzebna pełna i dodaje złożone problemy referencyjne rvalue, które mogą spowodować błąd kompilacji.

### <a name="example"></a>Przykład

```cpp
// std__tuple__make_tuple.cpp
// compile by using: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << std::get<0>(c0) << " ";
    std::cout << std::get<1>(c0) << " ";
    std::cout << std::get<2>(c0) << " ";
    std::cout << std::get<3>(c0) << std::endl;

    c0 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << std::get<0>(c0) << " ";
    std::cout << std::get<1>(c0) << " ";
    std::cout << std::get<2>(c0) << " ";
    std::cout << std::get<3>(c0) << std::endl;

    return (0);
}
```

```Output
0 1 2 3
4 5 6 7
```

## <a name="swap"></a><a name="swap"></a> wymiany

```cpp
template <class... Types>
    void swap(tuple<Types...>& x, tuple<Types...>& y) noexcept(see below );
```

## <a name="tie"></a><a name="tie"></a> równe

Tworzy `tuple` odwołania do elementu z.

```cpp
template <class T1, class T2, ..., class TN>
tuple<T1&, T2&, ..., TN&> tie(T1& t1, T2& t2, ..., TN& tN);
```

### <a name="parameters"></a>Parametry

*TN*\
Typ podstawowy wielonowego elementu krotki.

### <a name="remarks"></a>Uwagi

Funkcja szablonu zwraca wartość `tuple<T1&, T2&, ..., TN&>(t1, t2, ..., tN)` .

### <a name="example"></a>Przykład

```cpp
// std__tuple__tie.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    int v4 = 4;
    double v5 = 5;
    int v6 = 6;
    double v7 = 7;
    std::tie(v4, v5, v6, v7) = c0;

// display contents " 0 1 2 3"
    std::cout << " " << v4;
    std::cout << " " << v5;
    std::cout << " " << v6;
    std::cout << " " << v7;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
```

## <a name="tuple_cat"></a><a name="tuple_cat"></a> tuple_cat

```cpp
template <class... Tuples> constexpr tuple<CTypes...> tuple_cat(Tuples&&...);
```

### <a name="return-value"></a>Wartość zwracana

Obiekt krotki skonstruowany przez zainicjowanie każdego elementu typu.

## <a name="tuple_element_t"></a><a name="tuple_element_t"></a> tuple_element_t

```cpp
template <size_t I, class T>
    using tuple_element_t = typename tuple_element<I, T>::type;
```

## <a name="tuple_size_v"></a><a name="tuple_size_v"></a> tuple_size_v

```cpp
template <class T>
    inline constexpr size_t tuple_size_v = tuple_size<T>::value;
```

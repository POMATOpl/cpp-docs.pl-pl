---
title: '&lt;Krotka&gt; funkcje | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- tuple/std::get
- tuple/std::make_tuple
- tuple/std::tie
dev_langs:
- C++
ms.assetid: bc6be38f-5258-4c14-b81b-63caa335fd44
helpviewer_keywords:
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
ms.openlocfilehash: f0b995c4a966481e02ebd96748b247fd8844f19f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966410"
---
# <a name="lttuplegt-functions"></a>&lt;Krotka&gt; funkcji

||||
|-|-|-|
|[get](#get)|[make_tuple](#make_tuple)|[Powiązanie](#tie)|

## <a name="get"></a>  Pobierz

Pobiera element z `tuple` obiektu za pomocą indeksu lub (w języku C ++ 14) według typu.

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

*Index*  
 Indeks elementu do pobrania.

*Typy*  
 Sekwencja typów zadeklarowane w spójnej kolekcji, w kolejności deklaracji.

*T*  
 Typ elementu do pobrania.

*Krotki*  
 Std::tuple, który zawiera dowolną liczbę elementów.

### <a name="remarks"></a>Uwagi

Funkcje szablonów zwracają odwołanie do wartości w indeksie *indeksu*, lub typu *T* w `tuple` obiektu.

Wywoływanie `get<T>(Tuple)` generuje błąd kompilatora, jeśli krotka zawiera więcej lub mniej niż jeden element typu T.

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

## <a name="make_tuple"></a>  make_tuple —

Sprawia, że `tuple` z wartości elementu.

```cpp
template <class T1, class T2, ..., class TN>
   tuple<V1, V2, ..., VN> make_tuple(const T1& t1, const T2& t2, ..., const TN& tN);
```

### <a name="parameters"></a>Parametry

*TN*  
 Typ parametru funkcji n-ty.

*TN*  
 Wartość parametru funkcji n-ty.

### <a name="remarks"></a>Uwagi

Funkcja szablonu zwraca `tuple<V1, V2, ..., VN>(t1, t2, ..., tN)`, gdzie każdy typ `Vi` jest `X&` podczas wpisywania odpowiednich `Ti` jest `cv` `reference_wrapper<X>`; w przeciwnym razie jest `Ti`.

Jedną z zalet `make_tuple` są określane automatycznie przez kompilator i nie muszą być jawnie określone typy obiektów, które są przechowywane. Nie używaj jawnych argumentów szablonów takich jak `make_tuple<int, int>(1, 2)` zastosowania `make_tuple` ponieważ jest to niepotrzebne powielenie informacji i dodaje problemy z odwołaniami rvalue złożonych, które mogą spowodować błąd kompilacji.

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

## <a name="tie"></a>  Powiązanie

Sprawia, że `tuple` z odwołań elementu.

```cpp
template <class T1, class T2, ..., class TN>
tuple<T1&, T2&, ..., TN&> tie(T1& t1, T2& t2, ..., TN& tN);
```

### <a name="parameters"></a>Parametry

*TN*  
 Podstawowy typ krotki n-ty element.

### <a name="remarks"></a>Uwagi

Funkcja szablonu zwraca `tuple<T1&, T2&, ..., TN&>(t1, t2, ..., tN)`.

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

## <a name="see-also"></a>Zobacz także

[\<tuple>](../standard-library/tuple.md)<br/>

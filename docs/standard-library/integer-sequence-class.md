---
description: Dowiedz się więcej na temat klasy integer_sequence
title: integer_sequence — klasa
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::index_sequence
- type_traits/std::make_index_sequence
- type_traits/std::integer_sequence
- type_traits/std::make_integer_sequence
- type_traits/std::index_sequence_for
helpviewer_keywords:
- std::index_sequence
- std::make_index_sequence
- std::integer_sequence
- std::make_integer_sequence
- std::index_sequence_for
ms.assetid: 2cfdddee-819d-478e-bb78-c8a9c2696803
ms.openlocfilehash: 321e41c2c3bfaa1f89c05f799dedc4f4250f0a2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323978"
---
# <a name="integer_sequence-class"></a>integer_sequence — klasa

Reprezentuje sekwencję całkowitą. Może służyć do wywnioskowania i powiększania pakietów parametrów w typach wariadyczne, takich jak std:: krotka \<T...> , które są przekazane jako argumenty do funkcji.

## <a name="syntax"></a>Składnia

```cpp
template <class T, T... Vals>
struct integer_sequence
```

### <a name="parameters"></a>Parametry

*&*\
Typ wartości; musi być typem całkowitym: bool, char, char16_t, char32_t, wchar_t lub typów całkowitych bez znaku.

*Vals*\
Pakiet parametrów bez typu, który reprezentuje sekwencję wartości typu całkowitego T.

## <a name="members"></a>Elementy członkowskie

|Nazwa|Opis|
|-|-|
|`static size_t size() noexcept`|Liczba elementów w sekwencji.|
|`typedef T value_type`|Typ każdego elementu w sekwencji. Musi być typem całkowitym.|

## <a name="remarks"></a>Uwagi

Pakiet parametrów, który jest przesyłany bezpośrednio do funkcji można rozpakować bez żadnych specjalnych pomocników biblioteki. Gdy pakiet parametrów jest częścią typu, który jest przesyłany do funkcji i potrzebne są indeksy, aby uzyskać dostęp do elementów, najprostszym sposobem rozpakowania jest użycie `integer_sequence` i powiązane z nim aliasy typu,, `make_integer_sequence` `index_sequence` `make_index_sequence` , i `index_sequence_for` .

## <a name="example"></a>Przykład

Poniższy przykład jest oparty na oryginalnej propozycji [N3658](https://wg21.link/n3658). Pokazuje, jak użyć elementu `integer_sequence` do utworzenia `std::tuple` z `std::array<T,N>` i, jak używać elementu, `integer_sequence` Aby uzyskać dostęp do kolekcji elementów członkowskich.

W `a2t` funkcji `index_sequence` jest alias `integer_sequence` oparty na `size_t` typie całkowitym. `make_index_sequence` jest aliasem, który w czasie kompilacji tworzy zero na podstawie `index_sequence` tej samej liczby elementów co tablica, która jest przenoszona przez obiekt wywołujący. `a2t` przekazuje `index_sequence` przez wartość do `a2t_` , gdzie wyrażenie `a[I]...` rozpakuje `I` , a następnie elementy, do których są używane, `make_tuple` jako pojedyncze argumenty. Na przykład, jeśli sekwencja zawiera trzy elementy, `make_tuple` to jest wywoływana jako make_tuple (a [0], [1], [2]). Elementy tablicy mogą być oczywiście dowolnego typu.

Funkcja Apply akceptuje funkcję [std:: krotkę](../standard-library/tuple-class.md)i tworzy `integer_sequence` przy użyciu `tuple_size` klasy pomocnika. Należy zauważyć, że [ecay_t std::d](../standard-library/decay-class.md) jest konieczne, ponieważ [tuple_size](../standard-library/tuple-size-class-tuple.md) nie działa z typami referencyjnymi. `apply_`Funkcja rozpakuje składowe krotek i przekazuje je jako osobne argumenty do wywołania funkcji. W tym przykładzie funkcja jest prostym wyrażeniem lambda, które drukuje wartości.

```cpp
#include <stddef.h>
#include <iostream>
#include <tuple>
#include <utility>
#include <array>
#include <string>

using namespace std;

// Create a tuple from the array and the index_sequence
template<typename Array, size_t... I>
auto a2t_(const Array& a, index_sequence<I...>)
{
    return make_tuple(a[I]...);
}

// Create an index sequence for the array, and pass it to the
// implementation function a2t_
template<typename T, size_t N>
auto a2t(const array<T, N>& a)
{
    return a2t_(a, make_index_sequence<N>());
}

// Call function F with the tuple members as separate arguments.
template<typename F, typename Tuple = tuple<T...>, size_t... I>
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)
{
    return forward<F>(f)(get<I>(forward<Tuple>(args))...);
}

// Create an index_sequence for the tuple, and pass it with the
// function object and the tuple to the implementation function apply_
template<typename F, typename Tuple = tuple<T...>>
decltype(auto) apply(F&& f, Tuple&& args)
{
    using Indices = make_index_sequence<tuple_size<decay_t<Tuple>>::value >;
    return apply_(forward<F>(f), forward<Tuple>(args), Indices());
}

int main()
{
    const array<string, 3> arr { "Hello", "from", "C++14" };

    //Create a tuple given a array
    auto tup = a2t(arr);

    // Extract the tuple elements
    apply([](const string& a, const string& b, const string& c) {cout << a << " " << b << " " << c << endl; }, tup);

    char c;
    cin >> c;
}
```

Aby utworzyć `index_sequence` pakiet parametrów, użyj `index_sequence_for` \<T...> który jest aliasem dla`make_index_sequence`\<sizeof...(T)>

## <a name="requirements"></a>Wymagania

Nagłówki \<type_traits\>

Statements: std

## <a name="see-also"></a>Zobacz też

[Wielokropek i szablony wariadyczne](../cpp/ellipses-and-variadic-templates.md)

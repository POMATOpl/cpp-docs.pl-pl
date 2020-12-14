---
description: Dowiedz się więcej o strukturze modulo
title: modulus — Struktura
ms.date: 11/04/2016
f1_keywords:
- functional/std::modulus
helpviewer_keywords:
- modulus class
- modulus struct
ms.assetid: 86d342f7-b7b1-46a4-b0bb-6b7ae827369b
ms.openlocfilehash: f14edbcdb73a09fb9d44ff8d3dbd29bc0cdd2cdc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230487"
---
# <a name="modulus-struct"></a>modulus — Struktura

Wstępnie zdefiniowany obiekt funkcji, który wykonuje operację dzielenia modulo ( `operator%` ) na jej argumenty.

## <a name="syntax"></a>Składnia

```
template <class Type = void>
struct modulus : public binary_function <Type, Type, Type>
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator%
template <>
struct modulus<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) % std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parametry

*Typ*, *T*, *U*\
Dowolny typ, który obsługuje element `operator%` , który pobiera operandy określonego lub wywnioskowanego typu.

*Lewym*\
Lewy operand operacji modułu. Niewyspecjalizowany szablon przyjmuje argument odwołania lvalue *typu.* Szablon wyspecjalizowany jest idealnym przekazywaniem argumentów odwołania lvalue i rvalue dla typu wywnioskowanego *T*.

*Kliknij*\
Prawy operand operacji modułu. Niewyspecjalizowany szablon przyjmuje argument odwołania lvalue *typu.* Szablon wyspecjalizowany jest idealnym przekazywaniem argumentów odwołania lvalue i rvalue dla typu wywnioskowanego *U*.

## <a name="return-value"></a>Wartość zwracana

Wynik `Left % Right` . Wyspecjalizowany szablon robi doskonałe przekazywanie wyniku, który ma typ zwracany przez `operator%` .

## <a name="remarks"></a>Uwagi

`modulus`Funktor jest ograniczone do typów całkowitych dla podstawowych typów danych lub do typów zdefiniowanych przez użytkownika, które implementują `operator%` .

## <a name="example"></a>Przykład

```cpp
// functional_modulus.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <int> v1, v2, v3 ( 6 );
   vector <int>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 1 ; i <= 6 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   int j;
   for ( j = 1 ; j <= 6 ; j++ )
   {
      v2.push_back( 3 * j );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise remainders of the elements of v1 & v2
   transform (v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      modulus<int>() );

   cout << "The element-wise remainders of the modular division\n are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 5 10 15 20 25 30 )
The vector v2 = ( 3 6 9 12 15 18 )
The element-wise remainders of the modular division
are: ( 2 4 6 8 10 12 )
```

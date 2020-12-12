---
description: Dowiedz się więcej na temat struktury equal_to
title: equal_to — Struktura
ms.date: 11/04/2016
f1_keywords:
- functional/std::equal_to
helpviewer_keywords:
- equal_to function
- equal_to struct
ms.assetid: 8e4f2b50-b2db-48e3-b4cc-6cc03362c2a6
ms.openlocfilehash: cae0531c31396d16d447e3b0123dc679bbfd5aa6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324439"
---
# <a name="equal_to-struct"></a>equal_to — Struktura

Predykat binarny, który wykonuje operację równości ( `operator==` ) na jego argumentach.

## <a name="syntax"></a>Składnia

```cpp
template <class Type = void>
struct equal_to : public binary_function<Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator==
template <>
struct equal_to<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
      ->  decltype(std::forward<T>(Left) == std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parametry

*Typ*, *T*, *U*\
Dowolny typ, który obsługuje element `operator==` , który pobiera operandy określonego lub wywnioskowanego typu.

*Lewym*\
Lewy operand operacji równości. Niewyspecjalizowany szablon przyjmuje argument odwołania lvalue *typu.* Szablon wyspecjalizowany jest idealnym przekazywaniem argumentów odwołania lvalue i rvalue dla typu wywnioskowanego *T*.

*Kliknij*\
Prawy operand operacji równości. Niewyspecjalizowany szablon przyjmuje argument odwołania lvalue *typu.* Szablon wyspecjalizowany jest idealnym przekazywaniem argumentów odwołania lvalue i rvalue dla typu wywnioskowanego *U*.

## <a name="return-value"></a>Wartość zwracana

Wynik `Left == Right` . Wyspecjalizowany szablon robi doskonałe przekazywanie wyniku, który ma typ zwracany przez `operator==` .

## <a name="remarks"></a>Uwagi

Obiekty *typu Type muszą być* porównywalne ze równośćmi. Wymaga to, aby `operator==` zdefiniowane na zestawie obiektów spełniały właściwości matematyczne relacji równoważności. Wszystkie wbudowane typy liczbowe i wskaźniki spełniają to wymaganie.

## <a name="example"></a>Przykład

```cpp
// functional_equal_to.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <double> v1, v2, v3 ( 6 );
   vector <double>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 0 ; i <= 5 ; i+=2 )
   {
      v1.push_back( 2.0 *i );
      v1.push_back( 2.0 * i + 1.0 );
   }

   int j;
   for ( j = 0 ; j <= 5 ; j+=2 )
   {
      v2.push_back( - 2.0 * j );
      v2.push_back( 2.0 * j + 1.0 );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Testing for the element-wise equality between v1 & v2
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      equal_to<double>( ) );

   cout << "The result of the element-wise equal_to comparison\n"
      << "between v1 & v2 is: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 0 1 4 5 8 9 )
The vector v2 = ( -0 1 -4 5 -8 9 )
The result of the element-wise equal_to comparison
between v1 & v2 is: ( 1 1 0 1 0 1 )
```

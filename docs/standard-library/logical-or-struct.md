---
description: Dowiedz się więcej na temat struktury logical_or
title: logical_or — Struktura
ms.date: 11/04/2016
f1_keywords:
- functional/std::logical_or
helpviewer_keywords:
- logical_or class
- logical_or struct
ms.assetid: ec8143f8-5755-4e7b-8025-507fb6bf6911
ms.openlocfilehash: 7b6578bb3405b2428724554d520ffe784b885a40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277677"
---
# <a name="logical_or-struct"></a>logical_or — Struktura

Wstępnie zdefiniowany obiekt funkcji, który wykonuje logiczną operację rozłączenia ( `operator||` ) w argumentach.

## <a name="syntax"></a>Składnia

```
template <class Type = void>
struct logical_or : public binary_function<Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator||
template <>
struct logical_or<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) || std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parametry

*Typ*, *T*, *U*\
Dowolny typ, który obsługuje element `operator||` , który pobiera operandy określonego lub wywnioskowanego typu.

*Lewym*\
Lewy operand logicznej operacji rozłączenia. Niewyspecjalizowany szablon przyjmuje argument odwołania lvalue *typu.* Szablon wyspecjalizowany jest idealnym przekazywaniem argumentów odwołania lvalue i rvalue dla typu wywnioskowanego *T*.

*Kliknij*\
Prawy operand logicznej operacji rozłączenia. Niewyspecjalizowany szablon przyjmuje argument odwołania lvalue *typu.* Szablon wyspecjalizowany jest idealnym przekazywaniem argumentów odwołania lvalue i rvalue dla typu wywnioskowanego *U*.

## <a name="return-value"></a>Wartość zwracana

Wynik `Left || Right` . Wyspecjalizowany szablon robi doskonałe przekazywanie wyniku, który ma typ zwracany przez `operator||` .

## <a name="remarks"></a>Uwagi

W przypadku typów zdefiniowanych przez użytkownika nie istnieje krótkie obwody oceny operandów. Oba argumenty są oceniane przez `operator||` .

## <a name="example"></a>Przykład

```cpp
// functional_logical_or.cpp
// compile with: /EHsc
#include <deque>
#include <algorithm>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   deque <bool> d1, d2, d3( 7 );
   deque <bool>::iterator iter1, iter2, iter3;

   int i;
   for ( i = 0 ; i < 7 ; i++ )
   {
      d1.push_back((bool)((rand() % 2) != 0));
   }

   int j;
   for ( j = 0 ; j < 7 ; j++ )
   {
      d2.push_back((bool)((rand() % 2) != 0));
   }

   cout << boolalpha;    // boolalpha I/O flag on

   cout << "Original deque:\n d1 = ( " ;
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )
      cout << *iter1 << " ";
   cout << ")" << endl;

   cout << "Original deque:\n d2 = ( " ;
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )
      cout << *iter2 << " ";
   cout << ")" << endl;

   // To find element-wise disjunction of the truth values
   // of d1 & d2, use the logical_or function object
   transform( d1.begin( ), d1.end( ), d2.begin( ),
      d3.begin( ), logical_or<bool>( ) );
   cout << "The deque which is the disjuction of d1 & d2 is:\n d3 = ( " ;
   for ( iter3 = d3.begin( ) ; iter3 != d3.end( ) ; iter3++ )
      cout << *iter3 << " ";
   cout << ")" << endl;
}
```

```Output
Original deque:
d1 = ( true true false false true false false )
Original deque:
d2 = ( false false false true true true true )
The deque which is the disjuction of d1 & d2 is:
d3 = ( true true false true true true true )
```

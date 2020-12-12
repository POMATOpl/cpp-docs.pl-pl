---
description: Dowiedz się więcej o strukturze Negate
title: negate — Struktura
ms.date: 11/04/2016
f1_keywords:
- functional/std::negate
helpviewer_keywords:
- negate struct
- negate class
ms.assetid: 8a372686-786e-4262-b37c-ca13dc11e62f
ms.openlocfilehash: fccc583d38b797a856ed4e0915e5e0255bb9eaee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338242"
---
# <a name="negate-struct"></a>negate — Struktura

Wstępnie zdefiniowany obiekt funkcji, który wykonuje arytmetyczną operację negacji (Jednoargumentowa `operator-` ) w argumencie.

## <a name="syntax"></a>Składnia

```
template <class Type = void>
struct negate : public unary_function<Type, Type>
{
    Type operator()(const Type& Left) const;
};

// specialized transparent functor for unary operator-
template <>
struct negate<void>
{
  template <class Type>
  auto operator()(Type&& Left) const`
    -> decltype(-std::forward<Type>(Left));
};
```

### <a name="parameters"></a>Parametry

*Wprowadź*\
Dowolny typ, który obsługuje element `operator-` , który przyjmuje operand typu określonego lub wywnioskowanego.

*Lewym*\
Operand, który ma być negacją. Wyspecjalizowany szablon robi doskonałe przekazywanie argumentów odwołania lvalue i rvalue *typu* wywnioskowanego.

## <a name="return-value"></a>Wartość zwracana

Wynik `-Left` . Wyspecjalizowany szablon robi doskonałe przekazywanie wyniku, który ma typ zwracany przez jednoargumentowy `operator-` .

## <a name="example"></a>Przykład

```cpp
// functional_negate.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <int> v1, v2 ( 8 );
   vector <int>::iterator Iter1, Iter2;

   int i;
   for ( i = -2 ; i <= 5 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // Finding the element-wise negatives of the vector v1
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), negate<int>( ) );

   cout << "The negated elements of the vector = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( -10 -5 0 5 10 15 20 25 )
The negated elements of the vector = ( 10 5 0 -5 -10 -15 -20 -25 )
```

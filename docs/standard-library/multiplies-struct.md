---
title: "multiplies — struktura | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::multiplies
dev_langs: C++
helpviewer_keywords:
- multiplies class
- multiplies struct
ms.assetid: ec85e8af-70ad-44ad-90f0-d961a5847864
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 41eab9f2c172df43a15a05e6dc10127714417af5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="multiplies-struct"></a>multiplies — Struktura
Obiekt wstępnie zdefiniowanych funkcji, który wykonuje operację mnożenia (binarne `operator*`) na jego argumenty.  
  
## <a name="syntax"></a>Składnia  
  
```
template <class Type = void>
struct multiplies : public binary_function <Type, Type, Type>  
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator*
template <>
struct multiplies<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) * std::forward<U>(Right));
 };
```  
  
#### <a name="parameters"></a>Parametry  
 `Type`, `T`, `U`  
 Typ, który obsługuje dane binarne `operator*` pobierającej argumentów operacji typu określonego lub wywnioskowany.  
  
 `Left`  
 Lewy operand operacji mnożenia. Szablon klasy niespecjalizowanej przyjmuje argument odwołania l-wartością typu `Type`. Specjalne szablonu doskonała przekazującej lewostronnie i argumenty odwołanie do r-wartości wywnioskować typu `T`.  
  
 `Right`  
 Prawy argument operacji mnożenia. Szablon klasy niespecjalizowanej przyjmuje argument odwołania l-wartością typu `Type`. Specjalne szablonu doskonała przekazującej lewostronnie i argumenty odwołanie do r-wartości wywnioskować typu `U`.  
  
## <a name="return-value"></a>Wartość zwracana  
 Wynik `Left * Right`. Specjalne szablonu doskonała przekazywanie wynik, który ma typ zwracany przez `operator*`.  
  
## <a name="example"></a>Przykład  
  
```cpp  
// functional_multiplies.cpp  
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
      v1.push_back( 2 * i );  
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
  
   // Finding the element-wise products of the elements of v1 & v2  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),   
      multiplies<int>( ) );  
  
   cout << "The element-wise products of vectors V1 & v2\n are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
\* Output:   
The vector v1 = ( 2 4 6 8 10 12 )  
The vector v2 = ( 3 6 9 12 15 18 )  
The element-wise products of vectors V1 & v2  
 are: ( 6 24 54 96 150 216 )  
*\  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<funkcjonalności >  
  
 **Namespace:** Standard  
  
## <a name="see-also"></a>Zobacz też  
 [Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Dokumentacja standardowej biblioteki C++](../standard-library/cpp-standard-library-reference.md)




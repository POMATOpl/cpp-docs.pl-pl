---
title: "plus — struktura | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::plus
dev_langs:
- C++
helpviewer_keywords:
- plus class
- plus struct
ms.assetid: 4594abd5-b2f2-4fac-9b6b-fc9a2723f8cf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e40ad97ac315e368d05b62424da2f094da4beaf5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/23/2018
---
# <a name="plus-struct"></a>plus — Struktura
Obiekt funkcji wstępnie zdefiniowanej, który wykonuje operacje dodawania (binarne `operator+`) na jego argumentów.  
  
## <a name="syntax"></a>Składnia  
  
```
template <class Type = void>
struct plus : public binary_function <Type, Type, Type>  
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator+
template <>  
struct plus<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) + std::forward<U>(Right));
 };
```  
  
#### <a name="parameters"></a>Parametry  
 `Type`, `T`, `U`  
 Typ, który obsługuje dane binarne `operator+` pobierającej argumentów operacji typu określonego lub wywnioskowany.  
  
 `Left`  
 Lewy operand operacji dodawania. Szablon klasy niespecjalizowanej przyjmuje argument odwołania l-wartością typu `Type`. Specjalne szablonu doskonała przekazującej lewostronnie i argumenty odwołanie do r-wartości wywnioskować typu `T`.  
  
 `Right`  
 Prawy argument operacji dodawania. Szablon klasy niespecjalizowanej przyjmuje argument odwołania l-wartością typu `Type`. Specjalne szablonu doskonała przekazującej lewostronnie i argumenty odwołanie do r-wartości wywnioskować typu `U`.  
  
## <a name="return-value"></a>Wartość zwracana  
 Wynik `Left + Right`. Specjalne szablonu doskonała przekazywanie wynik, który ma typ zwracany przez dane binarne `operator+`.  
  
## <a name="example"></a>Przykład  
  
```cpp  
// functional_plus.cpp  
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
   for ( i = 0 ; i <= 5 ; i++ )  
      v1.push_back( 4 * i );  
  
   int j;  
   for ( j = 0 ; j <= 5 ; j++ )  
      v2.push_back( -2.0 * j - 4 );  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise sums of the elements of v1 & v2  
   transform (v1.begin( ), v1.end( ), v2.begin( ), v3.begin ( ), plus<double>( ) );  
  
   cout << "The element-wise sums are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
\* Output:   
The vector v1 = ( 0 4 8 12 16 20 )  
The vector v2 = ( -4 -6 -8 -10 -12 -14 )  
The element-wise sums are: ( -4 -2 0 2 4 6 )  
*\  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<funkcjonalności >  
  
 **Namespace:** Standard  
  
## <a name="see-also"></a>Zobacz też  
 [Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Dokumentacja standardowej biblioteki C++](../standard-library/cpp-standard-library-reference.md)




---
title: "logical_not — struktura | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::logical_not
dev_langs: C++
helpviewer_keywords:
- logical_not class
- logical_not struct
ms.assetid: 892db678-31da-4540-974b-17b05efc0849
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8d37a928bf385a0c3a836c294d838237e5142be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="logicalnot-struct"></a>logical_not — Struktura
Obiekt wstępnie zdefiniowanych funkcji, który wykonuje logicznym nie operacji ( `operator!`) na jej argument.  
  
## <a name="syntax"></a>Składnia  
  
```
template <class Type = void>
struct logical_not : public unary_function<Type, bool>  
{
    bool operator()(const Type& Left) const;
};

// specialized transparent functor for operator!
template <>
struct logical_not<void>  
{
  template <class Type>
  auto operator()(Type&& Left) const`
     -> decltype(!std::forward<Type>(Left));
 };
```  
  
#### <a name="parameters"></a>Parametry  
 `Type`  
 Dowolnego typu, który obsługuje `operator!` który przyjmuje argument typu określonego lub wykrywany.  
  
 `Left`  
 Operand operatora logicznego nie operacji. Szablon klasy niespecjalizowanej przyjmuje argument odwołania l-wartością typu `Type`. Specjalne szablonu doskonała przekazującej lewostronnie i argumenty odwołanie do r-wartości wywnioskować typu `Type`.  
  
## <a name="return-value"></a>Wartość zwracana  
 Wynik `!Left`. Specjalne szablonu doskonała przekazywanie wynik, który ma typ zwracany przez `operator!`.  
  
## <a name="example"></a>Przykład  
  
```cpp  
// functional_logical_not.cpp  
// compile with: /EHsc  
#include <deque>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   deque<bool> d1, d2 ( 7 );  
   deque<bool>::iterator iter1, iter2;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )  
   {  
      d1.push_back((bool)((i % 2) != 0));  
   }  
  
   cout << boolalpha;    // boolalpha I/O flag on  
  
   cout << "Original deque:\n d1 = ( " ;  
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )  
      cout << *iter1 << " ";  
   cout << ")" << endl;  
  
   // To flip all the truth values of the elements,  
   // use the logical_not function object  
   transform( d1.begin( ), d1.end( ), d2.begin( ),logical_not<bool>( ) );  
   cout << "The deque with its values negated is:\n d2 = ( " ;  
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )  
      cout << *iter2 << " ";  
   cout << ")" << endl;  
}  
/* Output:  
Original deque:  
 d1 = ( false true false true false true false )  
The deque with its values negated is:  
 d2 = ( true false true false true false true )  
 */  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<funkcjonalności >  
  
 **Namespace:** Standard  
  
## <a name="see-also"></a>Zobacz też  
 [Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Dokumentacja standardowej biblioteki C++](../standard-library/cpp-standard-library-reference.md)




---
title: "złożone&lt;podwójnej długości&gt; | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
dev_langs: C++
helpviewer_keywords: complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83a8ed2aa2bfe77a791d33961abde7f1df3f7fbe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="complexltlong-doublegt"></a>złożone&lt;podwójnej długości&gt;
Opisuje obiekt, który przechowuje uporządkowanej parę obiektów zarówno typu `long double`, najpierw reprezentujący część liczby złożonej, a drugi rzeczywista reprezentujący urojony części.  
  
## <a name="syntax"></a>Składnia  
  
```
template <>
class complex<long double> {
public:
    constexpr complex(
    long double _RealVal = 0,
    long double _ImagVal = 0);

complex(
    constexpr complex<long double>& complexNum);
// rest same as template class complex
};
```  
  
#### <a name="parameters"></a>Parametry  
 `_RealVal`  
 Wartość typu **podwójnej długości** rzeczywistych część liczby złożonej tworzona.  
  
 `_ImagVal`  
 Wartość typu `long double` urojony część liczby złożonej tworzona.  
  
 `complexNum`  
 Liczby złożonej typu **podwójne** lub typu **float** których części rzeczywistą i urojony są używane do zainicjowania liczbą typu `long double` tworzona.  
  
## <a name="return-value"></a>Wartość zwracana  
 Liczba złożonych typu `long double`.  
  
## <a name="remarks"></a>Uwagi  
 Jawna specjalizacja szablonu klasy złożone, aby złożonych klasy typu `long double` różni się od klasy szablonu tylko w przypadku konstruktorów definiuje. Konwersja z `long double` do **float** może być pośrednie, ale konwersja z **podwójne** do `long double` musi być **jawne**. Korzystanie z **jawne** wyklucza rozpoczęciu konwersji typu przy użyciu składni przypisania.  
  
 Aby uzyskać więcej informacji na klasy szablonu `complex`, zobacz [klasy złożone](../standard-library/complex-class.md). Aby uzyskać listę elementów członkowskich klasy szablonu `complex`, zobacz.  
  
## <a name="example"></a>Przykład  
  
```cpp  
// complex_comp_ld.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // The first constructor specifies real & imaginary parts  
   complex <long double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,\n"  
        << " as type float gives c1 = " << c1 << endl;  
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of complex number of type float  
   complex <float> c2float ( 1.0 , 3.0 );  
   complex <long double> c2longdouble ( c2float );  
   cout << "Implicit conversion from type float to type long double,"  
        << "\n gives c2longdouble = " << c2longdouble << endl;  
  
   // The third constructor initializes values of the real &  
   // imaginary parts using those of a complex number  
   // of type double  
   complex <double> c3double ( 3.0 , 4.0 );  
   complex <long double> c3longdouble ( c3double );  
   cout << "Implicit conversion from type long double to type float,"  
        << "\n gives c3longdouble = " << c3longdouble << endl;  
  
   // The modulus and argument of a complex number can be recovered  
   double absc3 = abs ( c3longdouble );  
   double argc3 = arg ( c3longdouble );  
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "  
        << absc3 << endl;  
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "  
        << argc3 << " radians, which is " << argc3 * 180 / pi  
        << " degrees." << endl;  
}  
\* Output:   
Specifying initial real & imaginary parts,  
 as type float gives c1 = (4,5)  
Implicit conversion from type float to type long double,  
 gives c2longdouble = (1,3)  
Implicit conversion from type long double to type float,  
 gives c3longdouble = (3,4)  
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5  
Argument of c3 is recovered from c3 using:  
 arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.  
*\  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek**: \<złożonych >  
  
 **Namespace:** Standard  
  
## <a name="see-also"></a>Zobacz też  
 [COMPLEX — klasa](../standard-library/complex-class.md)   
 [Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




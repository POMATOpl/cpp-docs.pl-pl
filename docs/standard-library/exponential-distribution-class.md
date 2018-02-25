---
title: "exponential_distribution — klasa | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- random/std::exponential_distribution
- random/std::exponential_distribution::reset
- random/std::exponential_distribution::lambda
- random/std::exponential_distribution::param
- random/std::exponential_distribution::min
- random/std::exponential_distribution::max
- random/std::exponential_distribution::operator()
- random/std::exponential_distribution::param_type
- random/std::exponential_distribution::param_type::lambda
- random/std::exponential_distribution::param_type::operator==
- random/std::exponential_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::exponential_distribution [C++]
- std::exponential_distribution [C++], reset
- std::exponential_distribution [C++], lambda
- std::exponential_distribution [C++], param
- std::exponential_distribution [C++], min
- std::exponential_distribution [C++], max
- std::exponential_distribution [C++], param_type
- std::exponential_distribution [C++], param_type
ms.assetid: d54f3126-a09b-45f9-a30b-0d94d03bcdc9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ac960d219535746e34d51ce778c1464be2f6c43
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/23/2018
---
# <a name="exponentialdistribution-class"></a>exponential_distribution — Klasa
Generuje rozkład wykładniczy.  
  
## <a name="syntax"></a>Składnia  
  
```  
template<class RealType = double>
class exponential_distribution  
   {  
public:  
   // types  
   typedef RealType result_type;  
   struct param_type;  
   
   // constructors and reset functions  
   explicit exponential_distribution(result_type lambda = 1.0);
   explicit exponential_distribution(const param_type& parm);
   void reset();
   
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions  
   result_type lambda() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
``` 
### <a name="parameters"></a>Parametry  
*RealType*  
Wartość domyślna typu wynik zmiennoprzecinkowy to `double`. Dla typów możliwych [ \<losowe >](../standard-library/random.md).  
  
*URNG* aparat losowe generatora liczb. Dla typów możliwych [ \<losowe >](../standard-library/random.md).
  
  
## <a name="remarks"></a>Uwagi  
 Klasa szablonu opisuje dystrybucji, który spowoduje utworzenie wartości typu całkowitego określone przez użytkownika typu lub typu `double` Jeśli nie zostanie podana, rozdzielonych rozkład wykładniczy. Poniższe łącza tabeli do artykułów na temat poszczególnych członków.  
  
||||  
|-|-|-|  
|[exponential_distribution](#exponential_distribution)|`exponential_distribution::lambda`|`exponential_distribution::param`|  
|`exponential_distribution::operator()`||[param_type](#param_type)|  
  
Funkcja członkowska właściwości `lambda()` zwraca wartość parametru przechowywanych dystrybucji `lambda`.  
  
Funkcja członkowska właściwości `param()` Ustawia lub zwraca `param_type` dystrybucji składowanych parametr pakietu.  
  
Aby uzyskać więcej informacji o dystrybucji klasy i ich elementy członkowskie, zobacz [ \<losowe >](../standard-library/random.md).  
  
Aby uzyskać szczegółowe informacje na temat rozkład wykładniczy, zobacz artykuł Wolfram MathWorld [rozkład wykładniczy](http://go.microsoft.com/fwlink/p/?linkid=401098).  
  
## <a name="example"></a>Przykład  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double l, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::exponential_distribution<> distr(l);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "lambda() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.lambda() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<double, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        std::cout << std::fixed << std::setw(11) << ++counter << ": "  
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double l_dist = 0.5;  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'lambda' distribution parameter (must be greater than zero): ";  
    std::cin >> l_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(l_dist, samples);  
}  
  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'lambda' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == 0  
max() == 1.79769e+308  
lambda() == 1.0000000000  
Distribution for 10 samples:  
    1: 0.0936880533  
    2: 0.1225944894  
    3: 0.6443593183  
    4: 0.6551171649  
    5: 0.7313457551  
    6: 0.7313557977  
    7: 0.7590097389  
    8: 1.4466885214  
    9: 1.6434088411  
    10: 2.1201210996  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<losowe >  
  
 **Namespace:** Standard  
  
##  <a name="exponential_distribution"></a>  exponential_distribution::exponential_distribution  
 Tworzy dystrybucji.  
  
```  
explicit exponential_distribution(result_type lambda = 1.0);
explicit exponential_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Parametry  
*lambda*  
 `lambda` Parametr dystrybucji.  
  
*parm*  
 Pakiet parametrów użyta do skonstruowania dystrybucji.  
  
### <a name="remarks"></a>Uwagi  
**Warunek wstępny:** `0.0 < lambda`  
  
Pierwszy Konstruktor konstrukcji obiektu których przechowywane `lambda` wartość przechowuje wartość *lambda*.  
  
Drugi Konstruktor konstrukcji obiektu, którego parametry przechowywane są inicjowane z *parametr*. Możesz uzyskać i ustawić bieżących parametrów istniejącego dystrybucji przez wywołanie metody `param()` funkcję elementu członkowskiego.  
  
##  <a name="param_type"></a>  exponential_distribution::param_type  
Przechowuje parametry dystrybucji.  
  
```
struct param_type {  
   typedef exponential_distribution<result_type> distribution_type;  
   param_type(result_type lambda = 1.0);
   result_type lambda() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```  
  
### <a name="parameters"></a>Parametry  
*lambda*  
`lambda` Parametr dystrybucji.  
  
*right*  
`param_type` Obiekt do porównania z tym.  
  
### <a name="remarks"></a>Uwagi  
**Warunek wstępny:** `0.0 < lambda`  
  
Ta struktura może być przekazany do konstruktora klasy dystrybucji przy tworzeniu wystąpienia, do `param()` funkcji członkowskiej, aby ustawić parametry przechowywane istniejących dystrybucji oraz do `operator()` do użycia zamiast przechowywane parametry.  
  
## <a name="see-also"></a>Zobacz też  
[\<losowe >](../standard-library/random.md)


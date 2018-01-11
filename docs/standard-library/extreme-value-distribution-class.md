---
title: "extreme_value_distribution — klasa | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::extreme_value_distribution
- random/std::extreme_value_distribution::reset
- random/std::extreme_value_distribution::a
- random/std::extreme_value_distribution::b
- random/std::extreme_value_distribution::param
- random/std::extreme_value_distribution::min
- random/std::extreme_value_distribution::max
- random/std::extreme_value_distribution::operator()
- random/std::extreme_value_distribution::param_type
- random/std::extreme_value_distribution::param_type::a
- random/std::extreme_value_distribution::param_type::b
- random/std::extreme_value_distribution::param_type::operator==
- random/std::extreme_value_distribution::param_type::operator!=
dev_langs: C++
helpviewer_keywords:
- std::extreme_value_distribution [C++]
- std::extreme_value_distribution [C++], reset
- std::extreme_value_distribution [C++], a
- std::extreme_value_distribution [C++], b
- std::extreme_value_distribution [C++], param
- std::extreme_value_distribution [C++], min
- std::extreme_value_distribution [C++], max
- std::extreme_value_distribution [C++], param_type
- std::extreme_value_distribution [C++], param_type
ms.assetid: a0cd8370-0a54-4e26-9388-8b9678fb57da
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b0825641039828073da4520c2f0704f50e0e6f21
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/03/2018
---
# <a name="extremevaluedistribution-class"></a>extreme_value_distribution — Klasa
Generuje dystrybucji najwyższą wartość.  
  
## <a name="syntax"></a>Składnia  
```  
template<class RealType = double>
class extreme_value_distribution  
   {  
public:  
   // types  
   typedef RealType result_type;  
   struct param_type;  
   
   // constructor and reset functions  
   explicit extreme_value_distribution(result_type a = 0.0, result_type b = 1.0);
   explicit extreme_value_distribution(const param_type& parm);
   void reset();
   
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions  
   result_type a() const;
   result_type b() const;
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
 Klasa szablonu opisuje dystrybucji tworzącego wartości określony użytkownik liczb zmiennoprzecinkowych typu lub typu `double` Jeśli nie zostanie podana, dystrybuowane zgodnie z najwyższą dystrybucji wartość. Poniższe łącza tabeli do artykułów na temat poszczególnych członków.  
  
||||  
|-|-|-|  
|[extreme_value_distribution —](#extreme_value_distribution)|`extreme_value_distribution::a`|`extreme_value_distribution::param`|  
|`extreme_value_distribution::operator()`|`extreme_value_distribution::b`|[param_type](#param_type)|  
  
 Funkcje właściwości `a()` i `b()` zwracać odpowiadających im wartości dla parametrów przechowywanych dystrybucji `a` i `b`.  
  
 Aby uzyskać więcej informacji o dystrybucji klasy i ich elementy członkowskie, zobacz [ \<losowe >](../standard-library/random.md).  
  
 Aby uzyskać szczegółowe informacje na temat dystrybucji najwyższą wartość, zobacz artykuł Wolfram MathWorld [najwyższą wartość dystrybucji](http://go.microsoft.com/fwlink/p/?linkid=401110).  
  
## <a name="example"></a>Przykład  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
  
    std::mt19937 gen(1701);  
  
    std::extreme_value_distribution<> distr(a, b);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "a() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.a() << std::endl;  
    std::cout << "b() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.b() << std::endl;  
  
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
    double a_dist = 0.0;  
    double b_dist = 1;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the \'a\' distribution parameter: ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the \'b\' distribution parameter (must be greater than zero): ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter: 0  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == -1.79769e+308  
max() == 1.79769e+308  
a() == 0.0000000000  
b() == 1.0000000000  
Distribution for 10 samples:  
    1: -0.8813940331  
    2: -0.7698972281  
    3: 0.2951258007  
    4: 0.3110450734  
    5: 0.4210546820  
    6: 0.4210688771  
    7: 0.4598857960  
    8: 1.3155194200  
    9: 1.5379170046  
    10: 2.0568757061  
```  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** \<losowe >  
  
 **Namespace:** Standard  
  
##  <a name="extreme_value_distribution"></a>extreme_value_distribution::extreme_value_distribution  
 Tworzy dystrybucji.  
  
```  
explicit extreme_value_distribution(result_type a_value = 0.0, result_type b_value = 1.0);
explicit extreme_value_distribution(const param_type& parm);  
```  
  
### <a name="parameters"></a>Parametry  
*a_value*  
 `a` Parametr dystrybucji.  
  
*b_value*  
 `b` Parametr dystrybucji.  
  
*Parametr*  
 `param_type` Struktury użyta do skonstruowania dystrybucji.  
  
### <a name="remarks"></a>Uwagi  
 **Warunek wstępny:**`0.0 < b`  
  
 Pierwszy Konstruktor konstrukcji obiektu których przechowywane `a` wartość zawiera wartość *a_value* i których przechowywane `b` wartość przechowuje wartość *b_value*.  
  
 Drugi Konstruktor konstrukcji obiektu, którego parametry przechowywane są inicjowane z *parametr*. Możesz uzyskać i ustawić bieżących parametrów istniejącego dystrybucji przez wywołanie metody `param()` funkcję elementu członkowskiego.  
  
##  <a name="param_type"></a>extreme_value_distribution::param_type  
Przechowuje parametry dystrybucji.  
  
```cpp  
struct param_type {  
   typedef extreme_value_distribution<result_type> distribution_type;  
   param_type(result_type a_value = 0.0, result_type b_value = 1.0);
   result_type a() const;
   result_type b() const;
    
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
  
### <a name="parameters"></a>Parametry  
*a_value*  
 `a` Parametr dystrybucji.  
  
*b_value*  
 `b` Parametr dystrybucji.  
  
*prawo*  
 `param_type` Obiekt do porównania z tym.  
  
### <a name="remarks"></a>Uwagi  
 **Warunek wstępny:**`0.0 < b`  
  
 Ta struktura może być przekazany do konstruktora klasy dystrybucji przy tworzeniu wystąpienia, do `param()` funkcji członkowskiej, aby ustawić parametry przechowywane istniejących dystrybucji oraz do `operator()` do użycia zamiast przechowywane parametry.  
  
## <a name="see-also"></a>Zobacz też  
 [\<losowe >](../standard-library/random.md)




---
title: "&lt;współczynnik&gt; | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ratio/std::mega
- ratio/std::peta
- ratio/std::ratio_greater
- ratio/std::micro
- ratio/std::ratio_add
- ratio/std::ratio_not_equal
- ratio/std::hecto
- ratio/std::nano
- ratio/std::ratio_less_equal
- ratio/std::ratio_less
- ratio/std::centi
- ratio/std::ratio_greater_equal
- ratio/std::ratio_subtract
- <ratio>
- ratio/std::atto
- ratio/std::tera
- ratio/std::milli
- ratio/std::ratio_multiply
- ratio/std::kilo
- ratio/std::ratio_divide
- ratio/std::giga
- ratio/std::pico
- ratio/std::femto
- ratio/std::ratio_equal
- ratio/std::ratio
- ratio/std::exa
- ratio/std::deci
- ratio/std::deca
dev_langs: C++
ms.assetid: 8543e912-2d84-45ea-b3c0-bd7bfacee405
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 13bcb39bd1bdcc24dc6f14d2cecf887c5213c450
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="ltratiogt"></a>&lt;współczynnik&gt;

Dołącz nagłówek standardowy \<stosunek > Aby zdefiniować stałe i szablony, które są używane do przechowywania i manipulowania liczby wymierne w czasie kompilacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
#include <ratio>  
```  
  
### <a name="ratio-template"></a>współczynnik szablonu  

```cpp
template<std::intmax_t Numerator, std::intmax_t Denominator = 1>
   struct ratio // holds the ratio of Numerator to Denominator
{
   static constexpr std::intmax_t num;
   static constexpr std::intmax_t den;
   typedef ratio<num, den> type;
}
```  

Szablon `ratio` definiuje stałe statyczne `num` i `den` tak, aby `num`  /  `den` == licznik / Denominator i `num` i `den` mieć nie typowych czynników. `num` / `den`to wartość, która jest reprezentowana przez klasy szablonu. W związku z tym `type` wyznacza wystąpienia `ratio<num, den>`.  
  
### <a name="specializations"></a>Specjalizacje

\<współczynnik > definiuje również specjalizacjach `ratio` mają następującą postać.  
  
`template <class R1, class R2> struct ratio_specialization`  
  
Każdy specjalizacji przyjmuje dwa parametry szablonu, które muszą być również specjalizacjach `ratio`. Wartość `type` jest określany przez skojarzony operacji logicznej.  
  
|Nazwa|`type`Wartość|  
|----------|------------------|  
|`ratio_add`|`R1 + R2`|  
|`ratio_divide`|`R1 / R2`|  
|`ratio_equal`|`R1 == R2`|  
|`ratio_greater`|`R1 > R2`|  
|`ratio_greater_equal`|`R1 >= R2`|  
|`ratio_less`|`R1 < R2`|  
|`ratio_less_equal`|`R1 <= R2`|  
|`ratio_multiply`|`R1 * R2`|  
|`ratio_not_equal`|`!(R1 == R2)`|  
|`ratio_subtract`|`R1 - R2`|  
  
### <a name="typedefs"></a>definicje typów  

Dla wygody nagłówka definiuje stosunek dla standardowych prefiksów SI:
  
```cpp
typedef ratio<1, 1000000000000000000> atto;
typedef ratio<1, 1000000000000000> femto;
typedef ratio<1, 1000000000000> pico;
typedef ratio<1, 1000000000> nano;
typedef ratio<1, 1000000> micro;
typedef ratio<1, 1000> milli;
typedef ratio<1, 100> centi;
typedef ratio<1, 10> deci;
typedef ratio<10, 1> deca;
typedef ratio<100, 1> hecto;
typedef ratio<1000, 1> kilo;
typedef ratio<1000000, 1> mega;
typedef ratio<1000000000, 1> giga;
typedef ratio<1000000000000, 1> tera;
typedef ratio<1000000000000000, 1> peta;
typedef ratio<1000000000000000000, 1> exa;
```  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)




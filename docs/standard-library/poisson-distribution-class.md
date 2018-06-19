---
title: poisson_distribution — klasa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::poisson_distribution
- random/std::poisson_distribution::reset
- random/std::poisson_distribution::mean
- random/std::poisson_distribution::param
- random/std::poisson_distribution::min
- random/std::poisson_distribution::max
- random/std::poisson_distribution::operator()
- random/std::poisson_distribution::param_type
- random/std::poisson_distribution::param_type::mean
- random/std::poisson_distribution::param_type::operator==
- random/std::poisson_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::poisson_distribution [C++]
- std::poisson_distribution [C++], reset
- std::poisson_distribution [C++], mean
- std::poisson_distribution [C++], param
- std::poisson_distribution [C++], min
- std::poisson_distribution [C++], max
- std::poisson_distribution [C++], param_type
- std::poisson_distribution [C++], param_type
ms.assetid: 09614281-349a-45f7-8e95-c0196be0a937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d88359bbf1521ad9fa464f22149c82497101ecb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857288"
---
# <a name="poissondistribution-class"></a>poisson_distribution — Klasa

Generuje rozkład Poissona.

## <a name="syntax"></a>Składnia

```cpp
template<class IntType = int>
class poisson_distribution
   {
public:
   // types
   typedef IntType result_type;
   struct param_type;

   // constructors and reset functions
   explicit poisson_distribution(double mean = 1.0);
   explicit poisson_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   double mean() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Parametry

*IntType* domyślnie integer — typ wyniku `int`. Dla typów możliwych [ \<losowe >](../standard-library/random.md).

## <a name="remarks"></a>Uwagi

Klasa szablonu opisuje dystrybucji, który spowoduje utworzenie wartości określonych przez użytkownika typu całkowitego z rozkład Poissona. Poniższe łącza tabeli do artykułów na temat poszczególnych członków.

||||
|-|-|-|
|[poisson_distribution](#poisson_distribution)|`poisson_distribution::mean`|`poisson_distribution::param`|
|`poisson_distribution::operator()`||[param_type](#param_type)|

Funkcja właściwości `mean()` zwraca wartość parametru dystrybucji przechowywanych *oznacza*.

Element członkowski właściwości `param()` Ustawia lub zwraca `param_type` dystrybucji składowanych parametr pakietu.

`min()` i `max()` funkcje Członkowskie zwracają najmniejsza możliwa wynik i największa możliwa wynik, odpowiednio.

`reset()` Funkcji członkowskiej odrzuca wszystkie buforowane wartości, tak aby wynik następne wywołanie `operator()` nie zależy od wartości uzyskane z aparatu przed wywołaniem.

`operator()` Elementu członkowskiego zwracają wartość następnego wygenerowanego oparty na aparacie URNG, z bieżącego pakietu parametrów lub pakiet określony parametr.

Aby uzyskać więcej informacji o dystrybucji klasy i ich elementy członkowskie, zobacz [ \<losowe >](../standard-library/random.md).

Aby uzyskać szczegółowe informacje na temat rozkład Poissona, zobacz artykuł Wolfram MathWorld [rozkład Poissona](http://go.microsoft.com/fwlink/p/?linkid=401112).

## <a name="example"></a>Przykład

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double p, const int s) {

    // uncomment to use a non-deterministic generator
    //    std::random_device gen;
    std::mt19937 gen(1701);

    std::poisson_distribution<> distr(p);

    std::cout << std::endl;
    std::cout << "min() == " << distr.min() << std::endl;
    std::cout << "max() == " << distr.max() << std::endl;
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.mean() << std::endl;

    // generate the distribution as a histogram
    std::map<int, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Distribution for " << s << " samples:" << std::endl;
    for (const auto& elem : histogram) {
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    double p_dist = 1.0;

    int samples = 100;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): ";
    std::cin >> p_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(p_dist, samples);
}

```

Pierwszego testu:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 100
min() == 0
max() == 2147483647
p() == 1.0000000000
Distribution for 100 samples:
    0 ::::::::::::::::::::::::::::::
    1 ::::::::::::::::::::::::::::::::::::::
    2 :::::::::::::::::::::::
    3 ::::::::
    5 :
```

Drugi test:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): 10
Enter an integer value for the sample count: 100
min() == 0
max() == 2147483647
p() == 10.0000000000
Distribution for 100 samples:
    3 :
    4 ::
    5 ::
    6 ::::::::
    7 ::::
    8 ::::::::
    9 ::::::::::::::
   10 ::::::::::::
   11 ::::::::::::::::
   12 :::::::::::::::
   13 ::::::::
   14 ::::::
   15 :
   16 ::
   17 :
```

## <a name="requirements"></a>Wymagania

**Nagłówek:** \<losowe >

**Namespace:** Standard

## <a name="poisson_distribution"></a>  poisson_distribution::poisson_distribution

Tworzy dystrybucji.

```cpp
explicit poisson_distribution(RealType mean = 1.0);
explicit binomial_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametry

*oznacza* `mean` parametru dystrybucji.

*Parametr* struktury parametr używany do budowy dystrybucji.

### <a name="remarks"></a>Uwagi

**Warunek wstępny:** `0.0 < mean`

Pierwszy Konstruktor konstrukcji obiektu których przechowywane `mean` wartość przechowuje wartość *oznacza*.

Drugi Konstruktor konstrukcji obiektu, którego parametry przechowywane są inicjowane z *parametr*. Możesz uzyskać i ustawić bieżących parametrów istniejącego dystrybucji przez wywołanie metody `param()` funkcję elementu członkowskiego.

## <a name="param_type"></a>  poisson_distribution::param_type

Przechowuje parametry dystrybucji.

```cpp
struct param_type {
   typedef poisson_distribution<IntType> distribution_type;
   param_type(double mean = 1.0);
   double mean() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametry

Zobacz parametrów konstruktora [poisson_distribution —](#poisson_distribution).

### <a name="remarks"></a>Uwagi

**Warunek wstępny:** `0.0 < mean`

Ta struktura może być przekazany do konstruktora klasy dystrybucji przy tworzeniu wystąpienia, do `param()` funkcji członkowskiej, aby ustawić parametry przechowywane istniejących dystrybucji oraz do `operator()` do użycia zamiast przechowywane parametry.

## <a name="see-also"></a>Zobacz także

[\<losowe >](../standard-library/random.md)<br/>

---
description: Dowiedz się więcej na temat klasy poisson_distribution
title: poisson_distribution — Klasa
ms.date: 11/04/2016
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
ms.openlocfilehash: b640517a63665ebec4573da8aff9e537412de589
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340674"
---
# <a name="poisson_distribution-class"></a>poisson_distribution — Klasa

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

*IntType*\
Typ wyniku liczby całkowitej, wartość domyślna to **`int`** . Aby zapoznać się z możliwymi typami, zobacz [\<random>](../standard-library/random.md) .

## <a name="remarks"></a>Uwagi

Szablon klasy zawiera opis dystrybucji, która tworzy wartości typu całkowitego określonego przez użytkownika z rozkładem Poissona. Poniższa tabela zawiera linki do artykułów na temat poszczególnych członków.

[poisson_distribution](#poisson_distribution)\
[param_type](#param_type)

Funkcja Property `mean()` zwraca wartość dla wartości przechowywanych parametrów rozkładu .

Element członkowski właściwości `param()` Ustawia lub zwraca `param_type` przechowywany pakiet parametrów dystrybucji.

`min()`I `max()` funkcje członkowskie zwracają najmniejszy możliwy wynik i największy możliwy wynik.

`reset()`Funkcja członkowska odrzuca wszystkie wartości pamięci podręcznej, dzięki czemu wynik następnego wywołania do `operator()` nie zależy od wartości uzyskanych z aparatu przed wywołaniem.

`operator()`Funkcje członkowskie zwracają następną wygenerowaną wartość opartą na aparacie URNG, z bieżącego pakietu parametrów lub z określonym pakietem parametrów.

Aby uzyskać więcej informacji na temat klas dystrybucji i ich członków, zobacz [\<random>](../standard-library/random.md) .

Aby uzyskać szczegółowe informacje na temat rozkładu Poissona, zobacz [rozkład Poissona](https://go.microsoft.com/fwlink/p/?linkid=401112)w artykule Wolfram MathWorld.

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

Pierwszy test:

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

**Nagłówek:**\<random>

**Przestrzeń nazw:** std

## <a name="poisson_distributionpoisson_distribution"></a><a name="poisson_distribution"></a> poisson_distribution::p oisson_distribution

Konstruuje dystrybucję.

```cpp
explicit poisson_distribution(RealType mean = 1.0);
explicit binomial_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametry

*zależność*\
`mean`Parametr rozkładu.

*parametr*\
Struktura parametru używana do konstruowania rozkładu.

### <a name="remarks"></a>Uwagi

**Warunek wstępny:**`0.0 < mean`

Pierwszy Konstruktor konstruuje obiekt, którego przechowywana `mean` wartość przechowuje wartość *średnia*.

Drugi Konstruktor konstruuje obiekt, którego przechowywane parametry są inicjowane z *parametr*. Możesz uzyskać i ustawić bieżące parametry istniejącej dystrybucji, wywołując `param()` funkcję członkowską.

## <a name="poisson_distributionparam_type"></a><a name="param_type"></a> poisson_distribution::p aram_type

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

Zobacz parametry konstruktora dla [poisson_distribution](#poisson_distribution).

### <a name="remarks"></a>Uwagi

**Warunek wstępny:**`0.0 < mean`

Tę strukturę można przesłać do konstruktora klasy dystrybucji podczas tworzenia wystąpienia, do `param()` funkcji składowej, aby ustawić przechowywane parametry istniejącej dystrybucji, a także `operator()` użyć zamiast przechowywanych parametrów.

## <a name="see-also"></a>Zobacz też

[\<random>](../standard-library/random.md)

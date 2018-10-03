---
title: złożone&lt;float&gt; | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- complex/std::complex<float>
dev_langs:
- C++
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 832bf638a123a24b901509d66989738f15ad44f0
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2018
ms.locfileid: "48233822"
---
# <a name="complexltfloatgt"></a>złożone&lt;float&gt;

Opisuje obiekt, który przechowuje uporządkowana para obiektów zarówno typu **float**, najpierw reprezentujących część liczby zespolonej, a druga rzeczywista reprezentujący urojone części.

## <a name="syntax"></a>Składnia

```cpp
template <>
class complex<float> {
public:
    constexpr complex(
    float _RealVal = 0,
    float _ImagVal = 0);

constexpr complex(
    const complex<float>& complexNum);

constexpr complex(
    const complex<double>& complexNum);

constexpr complex(
    const complex<long double>& complexNum);
// rest same as template class complex
};
```

### <a name="parameters"></a>Parametry

*_RealVal*<br/>
Wartość typu **float** rzeczywistych część liczby zespolonej budowany.

*_ImagVal*<br/>
Wartość typu **float** dla urojone części liczb zespolonych budowany.

*complexNum*<br/>
Liczby zespolonej typu **double** lub typu **typu long double** którego rzeczywiste i urojone części są stosowane do inicjalizacji liczby zespolonej typu **float** budowany.

## <a name="return-value"></a>Wartość zwracana

Liczby zespolonej typu **float**.

## <a name="remarks"></a>Uwagi

Jawna specjalizacja szablonu klasy złożone i klasy złożone typu **float** różni się od klasy szablonu, tylko w konstruktorach definiuje. Konwersja z **float** do **double** może być niejawne, jednak mniej bezpieczne konwersja **float** do **typu long double** jest musi być **jawne**. Korzystanie z **jawne** wyklucza rozpoczęcia z konwersję typu przy użyciu składni przypisania.

Aby uzyskać więcej informacji na temat klasy szablonu `complex`, zobacz [complex — klasa](../standard-library/complex-class.md). Aby uzyskać listę elementów członkowskich klasy szablonu `complex`, zobacz.

## <a name="example"></a>Przykład

```cpp
// complex_comp_flt.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <float> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type double
   complex <double> c2double ( 1.0 , 3.0 );
   complex <float> c2float ( c2double );
   cout << "Implicit conversion from type double to type float,"
        << endl << "gives c2float = " << c2float << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 3.0 , 4.0 );
   complex <float> c3float ( c3longdouble );
   cout << "Explicit conversion from type long double to type float,"
        << endl << "gives c3float = " << c3float << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3float);
   double argc3 = arg ( c3float);
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:"
        << endl << "arg ( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type double to type float,
gives c2float = (1,3)
Explicit conversion from type long double to type float,
gives c3float = (3,4)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.
*/
```

## <a name="requirements"></a>Wymagania

**Nagłówek**: \<złożonych >

**Namespace:** standardowe

## <a name="see-also"></a>Zobacz także

[complex, klasa](../standard-library/complex-class.md)<br/>
[Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

---
description: 'Dowiedz się więcej na temat: Klasa binder2nd —'
title: binder2nd — Klasa
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder2nd
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
ms.openlocfilehash: a3c76fcea22045ee7e723ad3ad51390c39f602ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325495"
---
# <a name="binder2nd-class"></a>binder2nd — Klasa

Szablon klasy dostarczający Konstruktor, który konwertuje obiekt funkcji binarnej na jednoargumentowy obiekt funkcji przez powiązanie drugiego argumentu funkcji Binary z określoną wartością. Przestarzałe w języku C++ 11, usunięte w języku C++ 17.

## <a name="syntax"></a>Składnia

```cpp
template <class Operation>
class binder2nd
    : public unaryFunction <typename Operation::first_argument_type,
    typename Operation::result_type>
{
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder2nd(
        const Operation& func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;
};
```

### <a name="parameters"></a>Parametry

*Func*\
Obiekt funkcji binarnej do przekonwertowania na jednoargumentowy obiekt funkcji.

*Kliknij*\
Wartość, do której należy powiązać drugi argument obiektu funkcji binarnej.

*lewym*\
Wartość argumentu, który dostosowany obiekt binarny porównuje do ustalonej wartości drugiego argumentu.

## <a name="return-value"></a>Wartość zwracana

Jednoargumentowy obiekt funkcji, który jest wynikiem powiązania drugiego argumentu obiektu funkcji binarnej z *prawą* wartością.

## <a name="remarks"></a>Uwagi

Szablon klasy przechowuje kopię obiektu funkcji binarnej *Func* w `op` i kopię z *prawej strony* `value` . Definiuje swoją funkcję członkowską `operator()` jako zwracaną `op(left, value)` .

Jeśli *Func* jest obiektem typu, `Operation` a c jest stałą, [bind2nd —](../standard-library/functional-functions.md#bind2nd) `(func, c)` jest odpowiednikiem `binder2nd` konstruktora klasy `binder2nd<Operation>(func, c)` i wygodniejsze.

## <a name="example"></a>Przykład

```cpp
// functional_binder2nd.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(),
        binder2nd<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare using binder1st fixing 1st argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder1st<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
```

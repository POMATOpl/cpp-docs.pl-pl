---
description: 'Dowiedz się więcej o: &lt; &gt; operatorzy narzędzi'
title: '&lt;&gt;Operatory narzędzi'
ms.date: 11/04/2016
f1_keywords:
- utility/std::operator!=
- utility/std::operator&gt;
- utility/std::operator&gt;=
- utility/std::operator&lt;
- utility/std::operator&lt;=
- utility/std::operator==
ms.assetid: a6617109-2cec-4a69-948f-6c87116eda5f
helpviewer_keywords:
- std::operator!= (utility)
- std::operator&gt; (utility)
- std::operator&gt;= (utility)
- std::operator&lt; (utility)
- std::operator&lt;= (utility)
- std::operator== (utility)
ms.openlocfilehash: 0db6f5b18708052964353687190295084886c928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153463"
---
# <a name="ltutilitygt-operators"></a>&lt;&gt;Operatory narzędzi

> [!NOTE]
> Operatory using `Type&` są zawarte w `namespace rel_ops` .

## <a name="operator"></a><a name="op_neq"></a> operator! =

Testuje, czy obiekt pary po lewej stronie operatora nie jest równy obiektowi pary po prawej stronie.

```cpp
template <class Type>
    constexpr bool operator!=(const Type& left, const Type& right);

template <class T, class U>
    constexpr bool operator!=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Obiekt typu `pair`.

*Kliknij*\
Obiekt typu `pair`.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli pary nie są równe; **`false`** Jeśli pary są równe.

### <a name="remarks"></a>Uwagi

Jedna para jest równa innej parze, jeśli każdy z jej elementów jest równy. Dwie pary nie są równe, jeśli pierwszy lub drugi element jednego z nich nie jest równy odpowiedniemu elementowi drugiej pary.

### <a name="example"></a>Przykład

```cpp
// utility_op_ne.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 1.11e-1 );
   p2 = make_pair ( 1000, 1.11e-3 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 != p2 )
      cout << "The pairs p1 and p2 are not equal." << endl;
   else
      cout << "The pairs p1 and p2 are equal." << endl;

   if ( p1 != p3 )
      cout << "The pairs p1 and p3 are not equal." << endl;
   else
      cout << "The pairs p1 and p3 are equal." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.111 ).
The pair p2 is: ( 1000, 0.00111 ).
The pair p3 is: ( 10, 0.111 ).

The pairs p1 and p2 are not equal.
The pairs p1 and p3 are equal.
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

Testuje, czy obiekt pary po lewej stronie operatora jest równy obiektowi pary po prawej stronie.

```cpp
template <class T, class U>
constexpr bool operator==(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Obiekt typu `pair`.

*Kliknij*\
Obiekt typu `pair`.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli pary są równe; **`false`** Jeśli wartość `pair` s nie jest równa.

### <a name="remarks"></a>Uwagi

Jedna para jest równa innej parze, jeśli każdy z jej elementów jest równy. Funkcja zwraca wartość `left` . **najpierw**  ==  `right` . **najpierw**  &&  `left` . **sekunda**  ==  `right` . **sekunda**. Dwie pary nie są równe, jeśli pierwszy lub drugi element jednego z nich nie jest równy odpowiedniemu elementowi drugiej pary.

### <a name="example"></a>Przykład

```cpp
// utility_op_eq.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 1.11e-1 );
   p2 = make_pair ( 1000, 1.11e-3 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 == p2 )
      cout << "The pairs p1 and p2 are equal." << endl;
   else
      cout << "The pairs p1 and p2 are not equal." << endl;

   if ( p1 == p3 )
      cout << "The pairs p1 and p3 are equal." << endl;
   else
      cout << "The pairs p1 and p3 are not equal." << endl;
}
```

## <a name="operatorlt"></a><a name="op_lt"></a> zakład&lt;

Testuje, czy obiekt pary po lewej stronie operatora jest mniejszy od obiektu pary po prawej stronie.

```cpp
template <class T, class U>
constexpr bool operator<(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Obiekt typu `pair` po lewej stronie operatora.

*Kliknij*\
Obiekt typu `pair` po prawej stronie operatora.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli po `pair` lewej stronie operatora jest ściśle mniej niż po `pair` prawej stronie operatora; w przeciwnym razie **`false`** .

### <a name="remarks"></a>Uwagi

`left` `pair` Obiekt ma być ściśle mniejszy niż `right` `pair` obiekt, jeśli wartość *Left* jest mniejsza niż lub równa *prawej*.

W porównaniu par wartości pierwszego elementu dwóch par mają najwyższy priorytet. Jeśli różnią się one, wynik porównania jest traktowany jako wynik porównania pary. Jeśli wartości pierwszego elementu nie są inne, wówczas wartości drugiego elementu są porównywane, a wynik porównania jest traktowany jako wynik porównania pary.

### <a name="example"></a>Przykład

```cpp
// utility_op_lt.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl << endl;

   if ( p1 < p2 )
      cout << "The pair p1 is less than the pair p2." << endl;
   else
      cout << "The pair p1 is not less than the pair p2." << endl;

   if ( p1 < p3 )
      cout << "The pair p1 is less than the pair p3." << endl;
   else
      cout << "The pair p1 is not less than the pair p3." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).

The pair p1 is less than the pair p2.
The pair p1 is not less than the pair p3.
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> zakład&lt;=

Testuje, czy obiekt pary po lewej stronie operatora jest mniejszy niż lub równy obiektowi pary po prawej stronie.

```cpp
template <class Type>
constexpr bool operator<=(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator<=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Obiekt typu `pair` po lewej stronie operatora.

*Kliknij*\
Obiekt typu `pair` po prawej stronie operatora.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli po `pair` lewej stronie operatora jest mniejszy lub równy po `pair` prawej stronie operatora; w przeciwnym razie **`false`** .

### <a name="remarks"></a>Uwagi

W porównaniu par wartości pierwszego elementu dwóch par mają najwyższy priorytet. Jeśli różnią się one, wynik porównania jest traktowany jako wynik porównania pary. Jeśli wartości pierwszego elementu nie są inne, wówczas wartości drugiego elementu są porównywane, a wynik porównania jest traktowany jako wynik porównania pary.

### <a name="example"></a>Przykład

```cpp
// utility_op_le.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 <= p2 )
      cout << "The pair p1 is less than or equal to the pair p2." << endl;
   else
      cout << "The pair p1 is greater than the pair p2." << endl;

   if ( p1 <= p3 )
      cout << "The pair p1 is less than or equal to the pair p3." << endl;
   else
      cout << "The pair p1 is greater than the pair p3." << endl;

   if ( p1 <= p4 )
      cout << "The pair p1 is less than or equal to the pair p4." << endl;
   else
      cout << "The pair p1 is greater than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is less than or equal to the pair p2.
The pair p1 is greater than the pair p3.
The pair p1 is less than or equal to the pair p4.
```

## <a name="operatorgt"></a><a name="op_gt"></a> zakład&gt;

Testuje, czy obiekt pary po lewej stronie operatora jest większy niż obiekt pary po prawej stronie.

```cpp
template <class Type>
constexpr bool operator>(const Type& left, const Type& right);

template <class T, class U>
constexpr bool operator>(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Obiekt typu `pair` po lewej stronie operatora.

*Kliknij*\
Obiekt typu `pair` po prawej stronie operatora.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli po `pair` lewej stronie operatora jest ściśle większa niż po `pair` prawej stronie operatora; w przeciwnym razie **`false`** .

### <a name="remarks"></a>Uwagi

`left` `pair` Obiekt ma być ściśle większy niż `right` `pair` obiekt, jeśli wartość *Left* jest większa od lub równa *prawej*.

W porównaniu par wartości pierwszego elementu dwóch par mają najwyższy priorytet. Jeśli różnią się one, wynik porównania jest traktowany jako wynik porównania pary. Jeśli wartości pierwszego elementu nie są inne, wówczas wartości drugiego elementu są porównywane, a wynik porównania jest traktowany jako wynik porównania pary.

### <a name="example"></a>Przykład

```cpp
// utility_op_gt.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 > p2 )
      cout << "The pair p1 is greater than the pair p2." << endl;
   else
      cout << "The pair p1 is not greater than the pair p2." << endl;

   if ( p1 > p3 )
      cout << "The pair p1 is greater than the pair p3." << endl;
   else
      cout << "The pair p1 is not greater than the pair p3." << endl;

   if ( p1 > p4 )
      cout << "The pair p1 is greater than the pair p4." << endl;
   else
      cout << "The pair p1 is not greater than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is not greater than the pair p2.
The pair p1 is greater than the pair p3.
The pair p1 is not greater than the pair p4.
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> zakład&gt;=

Testuje, czy obiekt pary po lewej stronie operatora jest większy niż lub równy obiektowi pary po prawej stronie.

```cpp
template <class Type>
    constexpr bool operator>=(const Type& left, const Type& right);

template <class T, class U>
    constexpr bool operator>=(const pair<T, U>& left, const pair<T, U>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Obiekt typu `pair` po lewej stronie operatora.

*Kliknij*\
Obiekt typu `pair` po prawej stronie operatora.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli po `pair` lewej stronie operatora jest większy lub równy po `pair` prawej stronie operatora; w przeciwnym razie **`false`** .

### <a name="remarks"></a>Uwagi

W porównaniu par wartości pierwszego elementu dwóch par mają najwyższy priorytet. Jeśli różnią się one, wynik porównania jest traktowany jako wynik porównania pary. Jeśli wartości pierwszego elementu nie są inne, wówczas wartości drugiego elementu są porównywane, a wynik porównania jest traktowany jako wynik porównania pary.

### <a name="example"></a>Przykład

```cpp
// utility_op_ge.cpp
// compile with: /EHsc
#include <utility>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;
   pair <int, double> p1, p2, p3, p4;

   p1 = make_pair ( 10, 2.22e-1 );
   p2 = make_pair ( 100, 1.11e-1 );
   p3 = make_pair ( 10, 1.11e-1 );
   p4 = make_pair ( 10, 2.22e-1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;
   cout << "The pair p4 is: ( " << p4.first << ", "
        << p4.second << " )." << endl << endl;

   if ( p1 >= p2 )
      cout << "Pair p1 is greater than or equal to pair p2." << endl;
   else
      cout << "The pair p1 is less than the pair p2." << endl;

   if ( p1 >= p3 )
      cout << "Pair p1 is greater than or equal to pair p3." << endl;
   else
      cout << "The pair p1 is less than the pair p3." << endl;

   if ( p1 >= p4 )
      cout << "Pair p1 is greater than or equal to pair p4." << endl;
   else
      cout << "The pair p1 is less than the pair p4." << endl;
}
```

```Output
The pair p1 is: ( 10, 0.222 ).
The pair p2 is: ( 100, 0.111 ).
The pair p3 is: ( 10, 0.111 ).
The pair p4 is: ( 10, 0.222 ).

The pair p1 is less than the pair p2.
Pair p1 is greater than or equal to pair p3.
Pair p1 is greater than or equal to pair p4.
```

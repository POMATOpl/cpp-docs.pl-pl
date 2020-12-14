---
description: 'Dowiedz się więcej o: &lt; &gt; Operatory pamięci'
title: '&lt;&gt;Operatory pamięci'
ms.date: 11/04/2016
f1_keywords:
- memory/std::operator!=
- memory/std::operator>
- memory/std::operator>=
- memory/std::operator<
- memory/std::operator<=
- memory/std::operator<<
- memory/std::operator==
ms.assetid: 257e3ba9-c4c2-4ae8-9b11-b156ba9c28de
ms.openlocfilehash: cbf52aa2af13a0eae241444d88e0eeabe7efe47b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183948"
---
# <a name="ltmemorygt-operators"></a>&lt;&gt;Operatory pamięci

## <a name="operator"></a><a name="op_neq"></a> operator! =

Testuje pod kątem nierówności między obiektami.

```cpp
template <class Type, class Other>
bool operator!=(
    const allocator<Type>& left,
    const allocator<Other>& right) throw();

template <class T, class Del1, class U, class Del2>
bool operator!=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator!=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Jeden z obiektów do przetestowania pod kątem nierówności.

*Kliknij*\
Jeden z obiektów do przetestowania pod kątem nierówności.

*Ty1*\
Typ kontrolowany przez lewy udostępniony wskaźnik.

*Ty2*\
Typ kontrolowany przez prawy udostępniony wskaźnik.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli obiekty nie są równe; **`false`** Jeśli obiekty są równe.

### <a name="remarks"></a>Uwagi

Pierwszy operator szablonu zwraca wartość false. (Wszystkie domyślne przydzielenie są równe).

Drugi i trzeci operator szablonu zwracają `!(left == right)` .

### <a name="example"></a>Przykład

```cpp
// memory_op_me.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<double> Alloc;
   vector <char>:: allocator_type v1Alloc;

   if ( Alloc != v1Alloc )
      cout << "The allocator objects Alloc & v1Alloc not are equal."
           << endl;
   else
      cout << "The allocator objects Alloc & v1Alloc are equal."
           << endl;
}
```

```Output
The allocator objects Alloc & v1Alloc are equal.
```

### <a name="example"></a>Przykład

```cpp
// std__memory__operator_ne.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(0));
    std::shared_ptr<int> sp1(new int(0));

    std::cout << "sp0 != sp0 == " << std::boolalpha
        << (sp0 != sp0) << std::endl;
    std::cout << "sp0 != sp1 == " << std::boolalpha
        << (sp0 != sp1) << std::endl;

    return (0);
    }
```

```Output
sp0 != sp0 == false
sp0 != sp1 == true
```

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

Testuje równość między obiektami.

```cpp
template <class Type, class Other>
bool operator==(
    const allocator<Type>& left,
    const allocator<Other>& right) throw();

template <class Ty1, class Del1, class Ty2, class Del2>
bool operator==(
    const unique_ptr<Ty1, Del1>& left,
    const unique_ptr<Ty2, Del2>& right);

template <class Ty1, class Ty2>
bool operator==(
    const shared_ptr<Ty1>& left;,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Jeden z obiektów do sprawdzenia pod kątem równości.

*Kliknij*\
Jeden z obiektów do sprawdzenia pod kątem równości.

*Ty1*\
Typ kontrolowany przez lewy udostępniony wskaźnik.

*Ty2*\
Typ kontrolowany przez prawy udostępniony wskaźnik.

### <a name="return-value"></a>Wartość zwracana

**`true`** Jeśli obiekty są równe, **`false`** Jeśli obiekty nie są równe.

### <a name="remarks"></a>Uwagi

Pierwszy operator szablonu zwraca wartość true. (Wszystkie domyślne przydzielenie są równe).

Drugi i trzeci operator szablonu zwracają `left.get() ==  right.get()` .

### <a name="example"></a>Przykład

```cpp
// memory_op_eq.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<char> Alloc;
   vector <int>:: allocator_type v1Alloc;

   allocator<char> cAlloc(Alloc);
   allocator<int> cv1Alloc(v1Alloc);

   if ( cv1Alloc == v1Alloc )
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."
           << endl;

   if ( cAlloc == Alloc )
      cout << "The allocator objects cAlloc & Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cAlloc & Alloc are not equal."
           << endl;
}
```

```Output
The allocator objects cv1Alloc & v1Alloc are equal.
The allocator objects cAlloc & Alloc are equal.
```

### <a name="example"></a>Przykład

```cpp
// std__memory__operator_eq.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(0));
    std::shared_ptr<int> sp1(new int(0));

    std::cout << "sp0 == sp0 == " << std::boolalpha
        << (sp0 == sp0) << std::endl;
    std::cout << "sp0 == sp1 == " << std::boolalpha
        << (sp0 == sp1) << std::endl;

    return (0);
    }
```

```Output
sp0 == sp0 == true
sp0 == sp1 == false
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> zakład&gt;=

Testy dla jednego obiektu, który jest większy niż lub równy drugiemu obiektowi.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator>=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U, Del2>& right);

template <class Ty1, class Ty2>
bool operator>=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Jeden z obiektów, które mają być porównane.

*Kliknij*\
Jeden z obiektów, które mają być porównane.

*Ty1*\
Typ kontrolowany przez lewy udostępniony wskaźnik.

*Ty2*\
Typ kontrolowany przez prawy udostępniony wskaźnik.

### <a name="remarks"></a>Uwagi

Operatory szablonu zwracają `left.get() >= right.get()` .

## <a name="operatorlt"></a><a name="op_lt"></a> zakład&lt;

Testy dla jednego obiektu, który jest mniejszy niż drugi obiekt.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator<(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator<(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Jeden z obiektów, które mają być porównane.

*Kliknij*\
Jeden z obiektów, które mają być porównane.

*Ty1*\
Typ kontrolowany przez lewy wskaźnik.

*Ty2*\
Typ kontrolowany przez prawy wskaźnik.

## <a name="operatorlt"></a><a name="op_lt_eq"></a> zakład&lt;=

Testy dla jednego obiektu, który jest mniejszy niż lub równy drugiemu obiektowi.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator<=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator<=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Jeden z obiektów, które mają być porównane.

*Kliknij*\
Jeden z obiektów, które mają być porównane.

*Ty1*\
Typ kontrolowany przez lewy udostępniony wskaźnik.

*Ty2*\
Typ kontrolowany przez prawy udostępniony wskaźnik.

### <a name="remarks"></a>Uwagi

Operatory szablonu zwracają `left.get() <= right.get()`

## <a name="operatorgt"></a><a name="op_gt"></a> zakład&gt;

Testy dla jednego obiektu, który jest większy niż drugi obiekt.

```cpp
template <class Ty1, class Del1, class Ty2, class Del2>
bool operator>(
    const unique_ptr<Ty1, Del1>& left,
    const unique_ptr<Ty2&, Del2gt;& right);

template <class Ty1, class Ty2>
bool operator>(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametry

*lewym*\
Jeden z obiektów, które mają być porównane.

*Kliknij*\
Jeden z obiektów, które mają być porównane.

*Ty1*\
Typ kontrolowany przez lewy udostępniony wskaźnik.

*Ty2*\
Typ kontrolowany przez prawy udostępniony wskaźnik.

## <a name="operatorltlt"></a><a name="op_lt_lt"></a> zakład&lt;&lt;

Zapisuje wspólny wskaźnik do strumienia.

```cpp
template <class Elem, class Tr, class Ty>
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,
    shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Parametry

*Elem*\
Typ elementu strumienia.

*Zdawczy*\
Typ cech elementu strumienia.

*Br*\
Typ kontrolowany przez wspólny wskaźnik.

*określoną*\
Strumień danych wyjściowych.

*requirement*\
Udostępniony wskaźnik.

### <a name="remarks"></a>Uwagi

Funkcja szablonu zwraca wartość `out << sp.get()` .

### <a name="example"></a>Przykład

```cpp
// std__memory__operator_sl.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(5));

    std::cout << "sp0 == " << sp0 << " (varies)" << std::endl;

    return (0);
    }
```

```Output
sp0 == 3f3040 (varies)
```

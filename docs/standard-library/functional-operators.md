---
description: 'Dowiedz się więcej o: &lt; &gt; Operatory funkcjonalne'
title: '&lt;&gt;Operatory funkcjonalne'
ms.date: 11/04/2016
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
ms.openlocfilehash: a22e9203e89c041d5ed1925d55d1cd3aa6d61ba3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324242"
---
# <a name="ltfunctionalgt-operators"></a>&lt;&gt;Operatory funkcjonalne

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

Testuje, czy możliwy do przeprowadzenia obiekt jest pusty.

```cpp
template <class Fty>
    bool operator==(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
    bool operator==(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>Parametry

*Fty*\
Typ funkcji do oblewania.

*n*\
Obiekt Function

*npc*\
Wskaźnik o wartości null.

### <a name="remarks"></a>Uwagi

Operatory przyjmują argument, który jest odwołaniem do `function` obiektu i argumentem, który jest stałą wskaźnika o wartości null. Oba zwracają wartość true tylko wtedy, gdy `function` obiekt jest pusty.

### <a name="example"></a>Przykład

```cpp
// std__functional__operator_eq.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
{
    return (-val);
}

int main()
{
    std::function<int(int)> fn0;
    std::cout << std::boolalpha << "empty == "
        << (fn0 == 0) << std::endl;

    std::function<int(int)> fn1(neg);
    std::cout << std::boolalpha << "empty == "
        << (fn1 == 0) << std::endl;

    return (0);
}
```

```Output
empty == true
empty == false
```

## <a name="operator"></a><a name="op_neq"></a> operator! =

Testuje, czy możliwy do przeprowadzenia obiekt nie jest pusty.

```cpp
template <class Fty>
    bool operator!=(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
    bool operator!=(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>Parametry

*Fty*\
Typ funkcji do oblewania.

*n*\
Obiekt Function

*npc*\
Wskaźnik o wartości null.

### <a name="remarks"></a>Uwagi

Operatory przyjmują argument, który jest odwołaniem do `function` obiektu i argumentem, który jest stałą wskaźnika o wartości null. Oba zwracają wartość true tylko wtedy, gdy `function` obiekt nie jest pusty.

### <a name="example"></a>Przykład

```cpp
// std__functional__operator_ne.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0;
    std::cout << std::boolalpha << "not empty == "
        << (fn0 != 0) << std::endl;

    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "not empty == "
        << (fn1 != 0) << std::endl;

    return (0);
    }
```

```Output
not empty == false
not empty == true
```

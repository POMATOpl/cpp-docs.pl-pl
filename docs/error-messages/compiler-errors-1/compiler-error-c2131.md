---
title: C2131 błąd kompilatora
ms.date: 02/28/2019
f1_keywords:
- C2131
helpviewer_keywords:
- C2131
ms.openlocfilehash: 19bdf73efa82e624382446c94642ceddac00bf2e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397591"
---
# <a name="compiler-error-c2131"></a>C2131 błąd kompilatora

> Wyrażenie nie zostało obliczone do stałej

Wyrażenie jest zadeklarowane jako **const** lub **constexpr** nie zostało oszacowane jako stała w czasie kompilacji. Kompilator musi mieć możliwość określenia wartości wyrażenia w punkcie, który jest używany.

## <a name="example"></a>Przykład

Ten przykład przedstawia sposób, aby spowodować błąd C2131 i jak go naprawić.

```cpp
// c2131.cpp
// compile by using: cl /EHsc /W4 /c c2131.cpp

struct test
{
    static const int array_size; // To fix, init array_size here.
    int size_array[array_size];  // C2131
};

const int test::array_size = 42;
```

```Output
c2131.cpp
c2131.cpp(7): error C2131: expression did not evaluate to a constant
c2131.cpp(7): note: failure was caused by non-constant arguments or reference to a non-constant symbol
c2131.cpp(7): note: see usage of 'array_size'
```

## <a name="see-also"></a>Zobacz także

[const](../../cpp/const-cpp.md)<br/>
[constexpr](../../cpp/constexpr-cpp.md)<br/>

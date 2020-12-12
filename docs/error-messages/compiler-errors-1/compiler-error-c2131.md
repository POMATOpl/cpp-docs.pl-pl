---
description: 'Dowiedz się więcej o: błąd kompilatora C2131'
title: Błąd kompilatora C2131
ms.date: 02/28/2019
f1_keywords:
- C2131
helpviewer_keywords:
- C2131
ms.openlocfilehash: 3c1f4e783c9341acf9e41fff99bba784acd8bbec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124179"
---
# <a name="compiler-error-c2131"></a>Błąd kompilatora C2131

> wyrażenie nie zostało obliczone do stałej

Wyrażenie zadeklarowane jako **`const`** lub **`constexpr`** nie zostało obliczone do stałej w czasie kompilacji. Kompilator musi być w stanie określić wartość wyrażenia w punkcie, w którym jest używana.

## <a name="example"></a>Przykład

Ten przykład pokazuje sposób, aby spowodować wystąpienie błędu C2131 i sposób jego naprawy.

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

## <a name="see-also"></a>Zobacz też

[const](../../cpp/const-cpp.md)<br/>
[constexpr](../../cpp/constexpr-cpp.md)<br/>

---
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: e12855127e417472eb88c951b71881240b808013
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214207"
---
# <a name="__noop"></a>__noop

**Specyficzne dla firmy Microsoft**

**`__noop`** Wewnętrzna określa, że funkcja powinna być ignorowana. Lista argumentów jest analizowana, ale dla argumentów nie jest generowany żaden kod. Jest ona przeznaczona do użycia w globalnych funkcjach debugowania, które przyjmują zmienną liczbę argumentów.

Kompilator konwertuje **`__noop`** wewnętrzną wartość na 0 w czasie kompilacji.

## <a name="example"></a>Przykład

Poniższy kod przedstawia sposób użycia **`__noop`** .

```cpp
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz także

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)

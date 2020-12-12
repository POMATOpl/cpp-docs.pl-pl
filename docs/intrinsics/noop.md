---
description: 'Dowiedz się więcej na temat: __noop'
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 4b140141e0f773f01cd666dd67f77244d7aef8a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222466"
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

## <a name="see-also"></a>Zobacz też

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)

---
description: 'Dowiedz się więcej o wewnętrznej firmie Microsoft C/C++: __noop'
title: __noop
ms.date: 12/16/2020
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 5fd300ca8d68305a12e6b5540be05aa60a042a44
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645088"
---
# `__noop`

Wewnętrznie **określony przez firmę Microsoft** **`__noop`** określa, że funkcja powinna być ignorowana. Lista argumentów jest analizowana, ale dla argumentów nie jest generowany żaden kod. Kompilator traktuje argumenty jako przywoływane do celów ostrzeżenia kompilatora C4100 i podobnej analizy. Element `__noop` wewnętrzny jest przeznaczony do użycia w globalnych funkcjach debugowania, które przyjmują zmienną liczbę argumentów.

Kompilator konwertuje **`__noop`** wewnętrzną wartość na 0 w czasie kompilacji.

## <a name="example"></a>Przykład

Poniższy kod przedstawia sposób użycia **`__noop`** .

```cpp
// compiler_intrinsics__noop.cpp
// compile using: cl /EHsc /W4 compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

#define IGNORE(x) { __noop(x); }

int main(int argv, char ** argc)
{
   IGNORE(argv);
   IGNORE(argc);
   PRINT("\nDEBUG is defined\n");
}
```

## <a name="see-also"></a>Zobacz także

[Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)\
[Słowa kluczowe](../cpp/keywords-cpp.md)

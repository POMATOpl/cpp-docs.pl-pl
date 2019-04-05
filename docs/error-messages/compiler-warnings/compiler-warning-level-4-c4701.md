---
title: Kompilator ostrzeżenie (poziom 4) C4701
ms.date: 11/04/2016
f1_keywords:
- C4701
helpviewer_keywords:
- C4701
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
ms.openlocfilehash: cbe70de39d2306edd50bb936ac5bbb4ad14af0e5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037266"
---
# <a name="compiler-warning-level-4-c4701"></a>Kompilator ostrzeżenie (poziom 4) C4701

Użycie potencjalnie niezainicjowanej zmiennej lokalnej "name" jest używany

Zmienna lokalna *nazwa* może być używana bez jest przypisywana wartość. Może to prowadzić do nieoczekiwanych rezultatów.

## <a name="example"></a>Przykład

Poniższy kod generuje C4701 i C4703.

```cpp
#include <malloc.h>

void func(int size)
{
    void* p;
    if (size < 256) {
        p = malloc(size);
    }

    if (p != nullptr) // C4701 and C4703
        free(p);
}

void main()
{
    func(9);
}
```

```Output
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used
```

Aby poprawić to ostrzeżenie, należy zainicjować zmienną, jak pokazano w poniższym przykładzie:

```cpp
#include <malloc.h>

void func(int size)
{
    void* p = nullptr;
    if (size < 256) {
        p = malloc(size);
    }

    if (p != nullptr)
        free(p);
}

void main()
{
    func(9);
}
```

## <a name="see-also"></a>Zobacz także

[Kompilator ostrzeżenie (poziom 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)<br/>
[Ostrzeżenia, / SDL i poprawy niezainicjowanej zmiennej wykrywania](https://www.microsoft.com/security/blog/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/)
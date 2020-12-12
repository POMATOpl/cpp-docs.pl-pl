---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4701'
title: Ostrzeżenie kompilatora (poziom 4) C4701
ms.date: 11/04/2016
f1_keywords:
- C4701
helpviewer_keywords:
- C4701
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
ms.openlocfilehash: e09b368d3477459cf6eea053e1be2a50a429298c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133817"
---
# <a name="compiler-warning-level-4-c4701"></a>Ostrzeżenie kompilatora (poziom 4) C4701

Użyto potencjalnie niezainicjowanej zmiennej lokalnej "name"

*Nazwa* zmiennej lokalnej mogła zostać użyta bez przypisywania wartości. Może to prowadzić do nieprzewidzianych wyników.

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

int main()
{
    func(9);
}
```

```Output
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used
```

Aby poprawić to ostrzeżenie, zainicjuj zmienną, jak pokazano w tym przykładzie:

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

int main()
{
    func(9);
}
```

## <a name="see-also"></a>Zobacz też

[Ostrzeżenie kompilatora (poziom 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)<br/>
[Ostrzeżenia,/SDL i ulepszanie wykrywania zmiennej niezainicjowanej](https://www.microsoft.com/security/blog/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/)

---
title: Kompilator ostrzeżenie (poziom 4) C4701 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4701
dev_langs:
- C++
helpviewer_keywords:
- C4701
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bea1c9eea9d3ef1ccc967ab5a563204ca850b889
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081068"
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

## <a name="see-also"></a>Zobacz też

[Ostrzeżenie kompilatora (poziom 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)<br/>
[Ostrzeżenia, / SDL i poprawy niezainicjowanej zmiennej wykrywania](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)
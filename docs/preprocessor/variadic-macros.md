---
description: 'Dowiedz się więcej o: makra wariadyczne'
title: Makra wariadyczne
ms.date: 10/17/2019
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: 74bf5b68696499ea8b1d88722d8a9e55f2ecab2d
ms.sourcegitcommit: 48b897797b3132ae934b1d191e3870c3c2466335
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2020
ms.locfileid: "97514592"
---
# <a name="variadic-macros"></a>Makra wariadyczne

Makra wariadyczne są makrami podobnymi do funkcji, które zawierają zmienną liczbę argumentów.

## <a name="remarks"></a>Uwagi

Aby można było używać makr wariadyczne, wielokropek może być określony jako ostatni argument formalny w definicji makra, a identyfikator zastępczy `__VA_ARGS__` może być używany w definicji w celu wstawienia dodatkowych argumentów.  `__VA_ARGS__` jest zastępowany przez wszystkie argumenty, które pasują do wielokropka, w tym przecinki między nimi.

Standard C określa, że co najmniej jeden argument musi być przekazywać do wielokropka, aby upewnić się, że makro nie jest rozpoznawane jako wyrażenie z końcowym przecinkiem. Tradycyjna implementacja języka Microsoft C++ pomija końcowy przecinek, jeśli żadne argumenty nie są przekazane do wielokropka. Gdy [`/Zc:preprocessor`](../build/reference/zc-preprocessor.md) Opcja kompilatora jest ustawiona, końcowy przecinek nie jest pomijany.

## <a name="example"></a>Przykład

```cpp
// variadic_macros.cpp
#include <stdio.h>
#define EMPTY

#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }
#define CHECK3(...) { printf(__VA_ARGS__); }
#define MACRO(s, ...) printf(s, __VA_ARGS__)

int main() {
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print

    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");

    // always invokes printf in the macro
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");

    MACRO("hello, world\n");

    MACRO("error\n", EMPTY); // would cause error C2059, except VC++
                             // suppresses the trailing comma
}
```

```Output
here are some varargs1(1)
here are some varargs2(4)
here are some varargs3(5)
hello, world
error
```

## <a name="see-also"></a>Zobacz także

[Makra (C/C++)](../preprocessor/macros-c-cpp.md)

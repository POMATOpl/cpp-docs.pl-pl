---
title: Kompilator ostrzeżenie (poziom 4) C4816
ms.date: 11/04/2016
f1_keywords:
- C4816
helpviewer_keywords:
- C4816
ms.assetid: 60f730ae-d942-4db9-ab97-41d4a874d8da
ms.openlocfilehash: 719a950f2cc15b51dcbbb7e8f4f476f92fe326c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626658"
---
# <a name="compiler-warning-level-4-c4816"></a>Kompilator ostrzeżenie (poziom 4) C4816

"param": parametr ma tablicę o rozmiarze zerowym, która zostanie obcięta (chyba że obiekt jest przekazywany przez odwołanie)

Parametr do obiektu z tablicy o rozmiarze zerowym nie został przekazany przez odwołanie. Gdy obiekt jest przekazywany tablicy nie spowoduje skopiowania.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C4816:

```
// C4816.cpp
// compile with: /W4
#include <stdio.h>

extern "C" int printf_s(const char *, ...);

#pragma warning(disable : 4200)

struct S1
{
    int i;
    char cArr[];
};

void TestErr(S1 s1)   // C4816 param with zero-array
                      // not passed by reference
{
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);
}

void TestOk(S1 &s1)
{
    printf_s("%d %c %c\n", s1.i, s1.cArr[0], s1.cArr[1]);
}

int main()
{
    S1 myS_1 = { 6, 'a', 'b', 'c' };
    TestErr(myS_1);
    TestOk(myS_1);
}
```
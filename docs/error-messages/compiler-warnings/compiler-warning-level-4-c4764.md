---
title: Kompilator ostrzeżenie (poziom 4) C4764
ms.date: 11/04/2016
f1_keywords:
- C4764
helpviewer_keywords:
- C4764
ms.assetid: 7bd4296f-966b-484c-bf73-8dbc8e85b4a9
ms.openlocfilehash: dd16b3f6e6591ec5b079f421fb199eb201c64483
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676333"
---
# <a name="compiler-warning-level-4-c4764"></a>Kompilator ostrzeżenie (poziom 4) C4764

Nie można wyrównać obiektów przechwytywania do więcej niż 16 bajtów

Wyrównanie, które są większe niż 16 został określony, ale na niektórych platformach, jeśli funkcja zgłosi wyjątek, stos spowoduje to wymuszenie wyrównanie nie więcej niż 16.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C4764:

```
// C4764.cpp
// compile with: /W4 /EHsc
// processor: x64 IPF
#include <stdio.h>

class A
{
public:
    int x;
};

typedef __declspec(align(32)) A ALIGNEDA;

int main()
{
    ALIGNEDA a;
    try
    {
        a.x = 15;
        throw a;
    }
    catch (ALIGNEDA b) // can’t align b to > 16 bytes
    {
        printf_s("%d\n", b.x);
    }
}   // C4764
```
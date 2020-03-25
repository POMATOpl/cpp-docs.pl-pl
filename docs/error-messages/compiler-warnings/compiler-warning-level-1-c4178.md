---
title: Ostrzeżenie kompilatora (poziom 1) C4178
ms.date: 11/04/2016
f1_keywords:
- C4178
helpviewer_keywords:
- C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
ms.openlocfilehash: 031f0f06c1ad7471aa7ca440b32de38de51a235a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176081"
---
# <a name="compiler-warning-level-1-c4178"></a>Ostrzeżenie kompilatora (poziom 1) C4178

stała przypadku "stała" jest zbyt duża dla typu wyrażenia Switch

Stała wielkości liter w wyrażeniu `switch` nie mieści się w typie, do którego jest przypisany.

## <a name="example"></a>Przykład

```cpp
// C4178.cpp
// compile with: /W1
int main()
{
    int i;  // maximum size of unsigned long int is 4294967295
    switch( i )
    {
        case 4294967295:   // OK
            break;
        case 4294967296:   // C4178
            break;
    }
}
```

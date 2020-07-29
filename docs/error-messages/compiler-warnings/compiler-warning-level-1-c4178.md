---
title: Ostrzeżenie kompilatora (poziom 1) C4178
ms.date: 11/04/2016
f1_keywords:
- C4178
helpviewer_keywords:
- C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
ms.openlocfilehash: e8d20da1ec8ca6ef4a06fdd1d8417d1cb9706947
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87196646"
---
# <a name="compiler-warning-level-1-c4178"></a>Ostrzeżenie kompilatora (poziom 1) C4178

stała przypadku "stała" jest zbyt duża dla typu wyrażenia Switch

Stała case w **`switch`** wyrażeniu nie mieści się w typie, do którego jest przypisany.

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

---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4178'
title: Ostrzeżenie kompilatora (poziom 1) C4178
ms.date: 11/04/2016
f1_keywords:
- C4178
helpviewer_keywords:
- C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
ms.openlocfilehash: 87876a70f638c3c8d98c20a3297482d317256d78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266757"
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

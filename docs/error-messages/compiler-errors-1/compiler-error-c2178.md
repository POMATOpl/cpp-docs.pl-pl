---
description: 'Dowiedz się więcej o: błąd kompilatora C2178'
title: Błąd kompilatora C2178
ms.date: 05/08/2017
f1_keywords:
- C2178
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
ms.openlocfilehash: 7a93293fdb87f30827b8b9c3c6d38066b0c76798
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322165"
---
# <a name="compiler-error-c2178"></a>Błąd kompilatora C2178

nie można zadeklarować *identyfikatora "identifier*" ze specyfikatorem "*specyfikatorer*"

**`mutable`** W deklaracji użyto specyfikatora, ale specyfikator jest niedozwolony w tym kontekście.

**`mutable`** Specyfikator może być stosowany tylko do nazw składowych danych klasy i nie może zostać zastosowany do nazw zadeklarowanych **`const`** lub **`static`** i nie może zostać zastosowany do elementów członkowskich odwołania.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak C2178 może wystąpić i jak rozwiązać ten problem.

```cpp
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C2888'
title: Błąd kompilatora C2888
ms.date: 11/04/2016
f1_keywords:
- C2888
helpviewer_keywords:
- C2888
ms.assetid: 244f593e-ff25-4dad-b31f-84dafa3bc84a
ms.openlocfilehash: f2440b628c2929b850664eb2f7c58148b0562c2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337456"
---
# <a name="compiler-error-c2888"></a>Błąd kompilatora C2888

"Identyfikator": symbol nie może być zdefiniowany w przestrzeni nazw "namespace"

Symbol należący do przestrzeni nazw A musi być zdefiniowany w przestrzeni nazw, która jest ujęta w.

Poniższy przykład generuje C2888:

```cpp
// C2888.cpp
// compile with: /c
namespace M {
   namespace N {
      void f1();
      void f2();
   }

   void N::f1() {}   // OK: namspace M encloses N
}

namespace O {
   void M::N::f2() {}   // C2888 namespace O does not enclose M
}
```

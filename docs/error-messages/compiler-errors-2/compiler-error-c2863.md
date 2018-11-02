---
title: Błąd kompilatora C2863
ms.date: 11/04/2016
f1_keywords:
- C2863
helpviewer_keywords:
- C2863
ms.assetid: 32561d67-a795-486b-b3b6-4b90a1acb176
ms.openlocfilehash: c0ee0e2932ef0ce739e14fd29ddde31f7d665f43
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530848"
---
# <a name="compiler-error-c2863"></a>Błąd kompilatora C2863

"interface": interfejs nie może mieć przyjaciół

Deklarowanie znajomych w interfejsie jest niedozwolone.

Poniższy przykład spowoduje wygenerowanie C2863:

```
// C2863.cpp
// compile with: /c
#include <unknwn.h>

class CMyClass {
   void *f();
};

__interface IMyInterface {
   void g();

   friend int h();   // 2863
   friend interface IMyInterface1;  // C2863
   friend void *CMyClass::f();  // C2863
};
```
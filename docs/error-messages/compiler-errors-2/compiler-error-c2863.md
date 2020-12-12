---
description: 'Dowiedz się więcej o: błąd kompilatora C2863'
title: Błąd kompilatora C2863
ms.date: 11/04/2016
f1_keywords:
- C2863
helpviewer_keywords:
- C2863
ms.assetid: 32561d67-a795-486b-b3b6-4b90a1acb176
ms.openlocfilehash: d4847d07bceda6fe1a34969cd290a59472135176
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305467"
---
# <a name="compiler-error-c2863"></a>Błąd kompilatora C2863

"Interface": interfejs nie może mieć znajomych

Deklarowanie znajomych w interfejsie jest niedozwolone.

Poniższy przykład generuje C2863:

```cpp
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

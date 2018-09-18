---
title: Błąd kompilatora C3723 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3723
dev_langs:
- C++
helpviewer_keywords:
- C3723
ms.assetid: ef0fb1ff-3f9a-4093-a6b6-894d1ab0c4b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c4a10ad3f6f4ff96c56cbed56662a42d8cc5bea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112268"
---
# <a name="compiler-error-c3723"></a>Błąd kompilatora C3723

'Funkcja': nie można rozpoznać zdarzenia

`function` Nie można rozpoznać zdarzenia do wywołania.

Poniższy przykład spowoduje wygenerowanie C3723:

```
// C3723.cpp
struct A {
   // To resolve, comment void f(int); and uncomment the __event function
   void f(int);
   // __event void f(int);
   void f(float);

};

struct B {
   void g(int);
   B(A* a) {
   __hook(&A::f, a, &B::g);   // C3723
   }
};

int main() {
}
```

`__hook` i `__unhook` nie są zgodne z/CLR programowania.  Zamiast tego użyj operatorów += i-=.

Poniższy przykład spowoduje wygenerowanie C3723:

```
// C3723b.cpp
// compile with: /clr
using namespace System;

public delegate void delegate1();

public ref class CPSource {
public:
   event delegate1^ event1;
};

public ref class CReceiver {
public:
   void Handler1() {
   }

   void UnhookAll(CPSource^ pSrc) {
      __unhook(&CPSource::event1, pSrc, &CReceiver::Handler1); // C3723
      // Try the following line instead.
      // pSrc->event1 -= gcnew delegate1(this, &CReceiver::Handler1);
   }
};

int main() {
}
```
---
title: Błąd kompilatora C2325
ms.date: 11/04/2016
f1_keywords:
- C2325
helpviewer_keywords:
- C2325
ms.assetid: e6b0a186-3f2a-4adf-beae-fadd75492bf7
ms.openlocfilehash: 28b291bd68971d7759589a75d8bafbf6e873dd39
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637674"
---
# <a name="compiler-error-c2325"></a>Błąd kompilatora C2325

"type": nieoczekiwany typ po prawej stronie "name"

Wykonano wywołanie dotyczące destruktora niepoprawnego typu.

Poniższy przykład spowoduje wygenerowanie C2325:

```
// C2325.cpp
// compile with: /c
class A {};
typedef A* pA_t;
void f() {
    A** ppa = new A *;
    ppa->~A*;   // C2325

   pA_t *ppa2 = new pA_t;
   ppa2->~pA_t();   // OK
}
```
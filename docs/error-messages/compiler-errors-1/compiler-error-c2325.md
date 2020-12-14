---
description: 'Dowiedz się więcej o: błąd kompilatora C2325'
title: Błąd kompilatora C2325
ms.date: 11/04/2016
f1_keywords:
- C2325
helpviewer_keywords:
- C2325
ms.assetid: e6b0a186-3f2a-4adf-beae-fadd75492bf7
ms.openlocfilehash: 899031fcd5bfe0e924232a05f3481f3bc65d0e63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312062"
---
# <a name="compiler-error-c2325"></a>Błąd kompilatora C2325

"Type": nieoczekiwany typ po prawej stronie "name"

Wywołanie jest nawiązywane w destruktorze o niepoprawnym typie.

Poniższy przykład generuje C2325:

```cpp
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

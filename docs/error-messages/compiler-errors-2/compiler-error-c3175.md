---
title: Błąd kompilatora C3175
ms.date: 11/04/2016
f1_keywords:
- C3175
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
ms.openlocfilehash: 368e5a9cb9bea04a7889c25c86a7245049677112
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642705"
---
# <a name="compiler-error-c3175"></a>Błąd kompilatora C3175

"function1": nie można wywołać metody typu zarządzanego z niezarządzanej funkcji "function2"

Funkcji niezarządzanych, nie można wywołać funkcji składowych klas zarządzanych.

Poniższy przykład spowoduje wygenerowanie C3175:

```
// C3175_2.cpp
// compile with: /clr

ref struct A {
   static void func() {
   }
};

#pragma unmanaged   // remove this line to resolve

void func2() {
   A::func();   // C3175
}

#pragma managed

int main() {
   A ^a = gcnew A;
   func2();
}
```

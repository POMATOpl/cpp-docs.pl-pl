---
title: Błąd kompilatora C3736
ms.date: 11/04/2016
f1_keywords:
- C3736
helpviewer_keywords:
- C3736
ms.assetid: 579b773c-41e7-40ea-8382-2e3ce2667f4c
ms.openlocfilehash: 9c4626164fe8fe3fb932fba3ae8e87c774f5aeec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752850"
---
# <a name="compiler-error-c3736"></a>Błąd kompilatora C3736

"Event": musi być metodą lub, w przypadku zarządzanych zdarzeń, opcjonalnie składową danych

Zdarzenia natywne i COM muszą być metodami. Zdarzenia platformy .NET mogą być również elementami członkowskimi danych.

Poniższy przykład generuje C3736:

```cpp
// C3736.cpp
struct A {
   __event int e();
};

struct B {
   int f;   // C3736
   // The following line resolves the error.
   // int f();
   B(A* a) {
      __hook(&A::e, a, &B::f);
   }
};

int main() {
}
```

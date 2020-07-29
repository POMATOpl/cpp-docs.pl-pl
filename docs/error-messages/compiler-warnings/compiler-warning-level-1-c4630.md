---
title: Ostrzeżenie kompilatora (poziom 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 3a533afe141a465fb034ba7d90b22a8206bf0910
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230626"
---
# <a name="compiler-warning-level-1-c4630"></a>Ostrzeżenie kompilatora (poziom 1) C4630

"symbol": specyfikator klasy magazynu "extern" jest niedozwolony w definicji składowej

Element członkowski danych lub funkcja członkowska jest definiowana jako **`extern`** . Elementy członkowskie nie mogą być zewnętrzne, chociaż mogą to być wszystkie obiekty. Kompilator ignoruje **`extern`** słowo kluczowe. Poniższy przykład generuje C4630:

```cpp
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```

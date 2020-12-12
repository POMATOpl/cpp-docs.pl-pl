---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4630'
title: Ostrzeżenie kompilatora (poziom 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 49a73dcd3ce11fefa1d4275e57ad98092c242d8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318913"
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

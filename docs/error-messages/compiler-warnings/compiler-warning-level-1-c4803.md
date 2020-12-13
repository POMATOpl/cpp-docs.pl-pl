---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4803'
title: Ostrzeżenie kompilatora (poziom 1) C4803
ms.date: 11/04/2016
f1_keywords:
- C4803
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
ms.openlocfilehash: 95646895133febbf03750d1b7a07d3a8141b6eff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334925"
---
# <a name="compiler-warning-level-1-c4803"></a>Ostrzeżenie kompilatora (poziom 1) C4803

"Metoda": Metoda podniesienia ma inną klasę magazynu od zdarzenia, "Event"

Metody zdarzeń muszą mieć tę samą klasę magazynu co deklaracja zdarzenia. Kompilator dostosowuje metody zdarzenia tak, aby klasy magazynu były takie same.

To ostrzeżenie może wystąpić, jeśli masz klasę, która implementuje zdarzenie z interfejsu. Kompilator nie generuje niejawnie metody podniesienia dla zdarzenia w interfejsie. Podczas implementowania tego interfejsu w klasie kompilator niejawnie generuje metodę podniesienia i ta metoda nie będzie wirtualna, a tym samym ostrzeżenie. Aby uzyskać więcej informacji na temat zdarzeń, zobacz [zdarzenie](../../extensions/event-cpp-component-extensions.md).

Aby uzyskać informacje na temat wyłączania ostrzeżenia, zobacz pragma [Warning](../../preprocessor/warning.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4803.

```cpp
// C4803.cpp
// compile with: /clr /W1
using namespace System;

public delegate void Del();

ref struct E {
   Del ^ _pd1;
   event Del ^ E1 {
      void add (Del ^ pd1) {
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));
      }

      void remove(Del^ pd1) {
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));
      }

      virtual void raise() {   // C4803 warning (remove virtual)
         if (_pd1)
            _pd1();
      }
   }

   void func() {
      Console::WriteLine("In E::func()");
   }
};

int main() {
   E ^ ep = gcnew E;
   ep->E1 += gcnew Del(ep, &E::func);
   ep->E1();
   ep->E1 -= gcnew Del(ep, &E::func);
   ep->E1();
}
```

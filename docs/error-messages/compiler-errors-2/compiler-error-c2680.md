---
title: Błąd kompilatora C2680
ms.date: 11/04/2016
f1_keywords:
- C2680
helpviewer_keywords:
- C2680
ms.assetid: d6f7129e-dd17-4661-b680-18d6b925b1cc
ms.openlocfilehash: 37535c9ffbafd0d312646d5f3cfdb0c4411bc790
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760312"
---
# <a name="compiler-error-c2680"></a>Błąd kompilatora C2680

"Type": nieprawidłowy typ docelowy dla nazwy

Operator rzutowania próbował skonwertować na typ, który nie jest wskaźnikiem ani odwołaniem. Operatora [dynamic_cast](../../cpp/dynamic-cast-operator.md) można używać tylko w przypadku wskaźników lub odwołań.

Poniższy przykład generuje C2680:

```cpp
// C2680.cpp
// compile with: /c
class A { virtual void f(); };
class B : public A {};

void g(B b) {
   A a;
   a = dynamic_cast<A>(b);   // C2680  target not a reference type
   a = dynamic_cast<A&>(b);   // OK
}
```

C2680 może również wystąpić, gdy element docelowy nie jest zdefiniowany:

```cpp
// C2680b.cpp
// compile with: /clr /c
// C2680 expected
using namespace System::Collections;

// Delete the following line to resolve.
ref class A;   // not defined

// Uncomment the following line to resolve.
// ref class A{};

public ref class B : ArrayList {
   property A^ C[int] {
      A^ get(int index) {
         return dynamic_cast<A^>(this->default::get(index));
      }
      void set(int index, A^ value) {
         this->default::set(index, value);
      }
   }
};
```

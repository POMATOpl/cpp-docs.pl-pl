---
description: 'Dowiedz się więcej o: błąd kompilatora C2662'
title: Błąd kompilatora C2662
ms.date: 11/04/2016
f1_keywords:
- C2662
helpviewer_keywords:
- C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
ms.openlocfilehash: 98a82773c5befe8a125031ab3aac355f582aa15a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170012"
---
# <a name="compiler-error-c2662"></a>Błąd kompilatora C2662

"Function": nie można skonwertować wskaźnika "This" z "type1" na "type2"

Kompilator nie może skonwertować **`this`** wskaźnika z `type1` do `type2` .

Ten błąd może być spowodowany wywoływaniem **`const`** funkcji nienależącej do elementu członkowskiego w **`const`** obiekcie.  Możliwe rozwiązania:

- Usuń **`const`** z deklaracji Object.

- Dodaj **`const`** do funkcji członkowskiej.

Poniższy przykład generuje C2662:

```cpp
// C2662.cpp
class C {
public:
   void func1();
   void func2() const{}
} const c;

int main() {
   c.func1();   // C2662
   c.func2();   // OK
}
```

Podczas kompilowania z **/CLR** nie można wywołać funkcji dla **`const`** lub **`volatile`** kwalifikowanego typu zarządzanego. Nie można zadeklarować stałej funkcji składowej klasy zarządzanej, więc nie można wywoływać metod w zarządzanych obiektach const.

```cpp
// C2662_b.cpp
// compile with: /c /clr
ref struct M {
   property M^ Type {
      M^ get() { return this; }
   }

   void operator=(const M %m) {
      M ^ prop = m.Type;   // C2662
   }
};

ref struct N {
   property N^ Type {
      N^ get() { return this; }
   }

   void operator=(N % n) {
      N ^ prop = n.Type;   // OK
   }
};
```

Poniższy przykład generuje C2662:

```cpp
// C2662_c.cpp
// compile with: /c
// C2662 expected
typedef int ISXVD;
typedef unsigned char BYTE;

class LXBASE {
protected:
    BYTE *m_rgb;
};

class LXISXVD:LXBASE {
public:
   // Delete the following line to resolve.
   ISXVD *PMin() { return (ISXVD *)m_rgb; }

   ISXVD *PMin2() const { return (ISXVD *)m_rgb; };   // OK
};

void F(const LXISXVD *plxisxvd, int iDim) {
   ISXVD isxvd;
   // Delete the following line to resolve.
   isxvd = plxisxvd->PMin()[iDim];

   isxvd = plxisxvd->PMin2()[iDim];
}
```

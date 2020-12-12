---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4927'
title: Ostrzeżenie kompilatora (poziom 1) C4927
ms.date: 11/04/2016
f1_keywords:
- C4927
helpviewer_keywords:
- C4927
ms.assetid: 7009e740-a2ef-4130-96ba-482e092f717a
ms.openlocfilehash: ddd131a5b87004fba56e80adbe5d9bea263f376a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301870"
---
# <a name="compiler-warning-level-1-c4927"></a>Ostrzeżenie kompilatora (poziom 1) C4927

niedozwolona konwersja; więcej niż jedna konwersja zdefiniowana przez użytkownika została zastosowana niejawnie

Więcej niż jedna konwersja zdefiniowana przez użytkownika została zastosowana niejawnie do pojedynczej wartości — kompilator nie znalazł jawnej konwersji, ale znalazł konwersję, która została użyta.

Poniższy przykład generuje C4927:

```cpp
// C4927.cpp
// compile with: /W1
struct B
{
   operator int ()
   {
      return 0;
   }
};

struct A
{
   A(int i)
   {
   }

   /*
   // uncomment this constructor to resolve
   A(B b)
   {
   }
   */
};

A f1( B& b)
{
   return A(b);
}

B& f2( B& b)
{
   return b;
}

A f()
{
   B b;
   return A(b);   // ok
   return f1(b);  // ok
   return b;      // C4927
   return B(b);   // C4927
   return f2(b);  // C4927
}

int main()
{
   B b;
   A a = b;
   A a2(b);
}
```

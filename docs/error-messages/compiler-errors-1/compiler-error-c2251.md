---
title: Błąd kompilatora C2251
ms.date: 11/04/2016
f1_keywords:
- C2251
helpviewer_keywords:
- C2251
ms.assetid: fefe050c-f8d3-4316-b237-8007dbcdd3bf
ms.openlocfilehash: d44ed7af3552f0a7c9cc9b5b2b0d14a468713254
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759701"
---
# <a name="compiler-error-c2251"></a>Błąd kompilatora C2251

Przestrzeń nazw "namespace" nie ma składowej "member" — Czy chodziło o "member"?

Kompilator nie może odnaleźć identyfikatora w określonej przestrzeni nazw.

Poniższy przykład generuje C2251:

```cpp
// C2251.cpp
// compile with: /c
namespace A {
   namespace B {
      void f1();
   }

   using namespace B;
}

void A::f1() {}   // C2251
void A::B::f1() {}   // OK
```

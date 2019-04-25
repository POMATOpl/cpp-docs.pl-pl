---
title: Błąd kompilatora C2819
ms.date: 11/04/2016
f1_keywords:
- C2819
helpviewer_keywords:
- C2819
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
ms.openlocfilehash: 17b863d24d43f0dc7afb0fc4776953dcb41929e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174942"
---
# <a name="compiler-error-c2819"></a>Błąd kompilatora C2819

Typ "type" nie ma przeciążonej składowej "operator ->"

Należy zdefiniować `operator->()` na tę operację wskaźnika.

Poniższy przykład spowoduje wygenerowanie C2819:

```
// C2819.cpp
// compile with: /c
class A {
   public:
      int i;
};

class B {};

void C(B j) {
   j->i;   // C2819
}

class D {
   A* pA;

   public:
      A* operator->() {
         return pA;
      }
};

void F(D j) {
   j->i;
}
```

C2819 może również wystąpić, gdy za pomocą [semantyka stosu C++ dla typów odwołań](../../dotnet/cpp-stack-semantics-for-reference-types.md). Poniższy przykład spowoduje wygenerowanie C2819:

```
// C2819_b.cpp
// compile with: /clr
ref struct R {
   void Test() {}
};

int main() {
   R r;
   r->Test();   // C2819
   r.Test();   // OK
}
```
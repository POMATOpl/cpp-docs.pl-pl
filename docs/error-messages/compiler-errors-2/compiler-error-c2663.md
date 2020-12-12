---
description: 'Dowiedz się więcej o: błąd kompilatora C2663'
title: Błąd kompilatora C2663
ms.date: 11/04/2016
f1_keywords:
- C2663
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
ms.openlocfilehash: 3e70e2d10b0a133769d92ce637bd9e5f4d44315a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169986"
---
# <a name="compiler-error-c2663"></a>Błąd kompilatora C2663

"Function": przeciążenia numerów nie mają żadnych dozwolonych konwersji dla wskaźnika "This"

Kompilator nie może wykonać konwersji **`this`** do żadnej ze przeciążonych wersji funkcji składowej.

Ten błąd może być spowodowany wywoływaniem **`const`** funkcji nienależącej do elementu członkowskiego w **`const`** obiekcie.  Możliwe rozwiązania:

1. Usuń **`const`** z deklaracji Object.

1. Dodaj **`const`** do jednego z przeciążeń funkcji składowych.

Poniższy przykład generuje C2663:

```cpp
// C2663.cpp
struct C {
   void f() volatile {}
   void f() {}
};

struct D {
   void f() volatile;
   void f() const {}
};

const C *pcc;
const D *pcd;

int main() {
   pcc->f();    // C2663
   pcd->f();    // OK
}
```

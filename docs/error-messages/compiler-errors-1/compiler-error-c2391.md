---
title: Błąd kompilatora C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: 7dd47ffbd9481f69f3799a94a17a53ccdffb2a84
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745021"
---
# <a name="compiler-error-c2391"></a>Błąd kompilatora C2391

"Identyfikator": "Friend" nie może zostać użyty podczas definicji typu

Deklaracja `friend` zawiera kompletną deklarację klasy. Deklaracja `friend` może określać funkcję członkowską lub wyrafinowany specyfikator typu, ale nie pełną deklarację klasy.

Poniższy przykład generuje C2326:

```cpp
// C2391.cpp
// compile with: /c
class D {
   void func( int );
};

class A {
   friend class B { int i; };   // C2391

   // OK
   friend class C;
   friend void D::func(int);
};
```

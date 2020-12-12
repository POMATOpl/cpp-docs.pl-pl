---
description: 'Dowiedz się więcej o: błąd kompilatora C2602'
title: Błąd kompilatora C2602
ms.date: 11/04/2016
f1_keywords:
- C2602
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
ms.openlocfilehash: 2922ee0d35dd5820e1df23d9bc812c0650501b35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312024"
---
# <a name="compiler-error-c2602"></a>Błąd kompilatora C2602

element "Class:: identifier" nie jest elementem członkowskim klasy bazowej elementu "Class"

`Identifier` nie można uzyskać dostępu, ponieważ nie jest on członkiem dziedziczonym z żadnej klasy bazowej.

Poniższy przykład generuje C2602:

```cpp
// C2602.cpp
// compile with: /c
struct X {
   int x;
};
struct A {
   int a;
};
struct B : public A {
   X::x;   // C2602 B is not derived from X
   A::a;   // OK
};
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C2698'
title: Błąd kompilatora C2698
ms.date: 11/04/2016
f1_keywords:
- C2698
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
ms.openlocfilehash: a787c43e7a885734f4c6a2d76aa16d51e19615c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326633"
---
# <a name="compiler-error-c2698"></a>Błąd kompilatora C2698

Deklaracja using dla elementu "Deklaracja 1" nie może współistnieć z istniejącą deklaracją using dla deklaracji 2

Gdy masz [deklarację using](../../cpp/using-declaration.md) dla elementu członkowskiego danych, wszelkie użycie deklaracji w tym samym zakresie, który używa tej samej nazwy, nie jest dozwolone, ponieważ tylko funkcje mogą być przeciążone.

Poniższy przykład generuje C2698:

```cpp
// C2698.cpp
struct A {
   int x;
};

struct B {
   int x;
};

struct C : A, B {
   using A::x;
   using B::x;   // C2698
}
```

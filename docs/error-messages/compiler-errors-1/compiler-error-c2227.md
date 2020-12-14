---
description: 'Dowiedz się więcej o: błąd kompilatora C2227'
title: Błąd kompilatora C2227
ms.date: 11/04/2016
f1_keywords:
- C2227
helpviewer_keywords:
- C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
ms.openlocfilehash: 75cab2269a254bc485a33396fb128aaa955651d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195076"
---
# <a name="compiler-error-c2227"></a>Błąd kompilatora C2227

po lewej stronie elementu "->member" musi wskazywać typ Class/struct/Union/Generic

Operand z lewej strony `->` nie jest wskaźnikiem do klasy, struktury lub Unii.

Poniższy przykład generuje C2227:

```cpp
// C2227.cpp
int *pInt;
struct S {
public:
    int member;
} s, *pS = &s;

int main() {
   pInt->member = 0;   // C2227 pInt points to an int
   pS->member = 0;   // OK
}
```

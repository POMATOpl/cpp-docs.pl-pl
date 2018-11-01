---
title: Błąd kompilatora C2227
ms.date: 11/04/2016
f1_keywords:
- C2227
helpviewer_keywords:
- C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
ms.openlocfilehash: 8f9fc435682eb400574eea61a6f90392fa679233
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452744"
---
# <a name="compiler-error-c2227"></a>Błąd kompilatora C2227

po lewej "-> elementu członkowskiego" musi wskazywać typ klasy/struct/union/generic

Argument operacji po lewej stronie `->` nie jest wskaźnik do klasy, struktury lub Unii.

Poniższy przykład spowoduje wygenerowanie C2227:

```
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
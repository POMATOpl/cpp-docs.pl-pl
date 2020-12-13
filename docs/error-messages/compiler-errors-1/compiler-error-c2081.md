---
description: 'Dowiedz się więcej o: błąd kompilatora C2081'
title: Błąd kompilatora C2081
ms.date: 11/04/2016
f1_keywords:
- C2081
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
ms.openlocfilehash: e6f75d6d478d9523d36a9671457cf2a5618e4f21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151180"
---
# <a name="compiler-error-c2081"></a>Błąd kompilatora C2081

"Identyfikator": nazwa w formalnej liście parametrów jest niedozwolona

Identyfikator spowodował błąd składniowy.

Ten błąd może być spowodowany użyciem starego stylu dla formalnej listy parametrów. Należy określić typ parametrów formalnych na liście parametrów formalnych.

Poniższy przykład generuje C2081:

```c
// C2081.c
void func( int i, j ) {}  // C2081, no type specified for j
```

Możliwe rozwiązanie:

```c
// C2081b.c
// compile with: /c
void func( int i, int j ) {}
```

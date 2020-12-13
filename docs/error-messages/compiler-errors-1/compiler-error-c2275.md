---
description: 'Dowiedz się więcej o: błąd kompilatora C2275'
title: Błąd kompilatora C2275
ms.date: 11/04/2016
f1_keywords:
- C2275
helpviewer_keywords:
- C2275
ms.assetid: c1eafa71-48de-46e0-82f3-b575538ef205
ms.openlocfilehash: c6bc03c630a859c2f0913fd482f463071a21758c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134553"
---
# <a name="compiler-error-c2275"></a>Błąd kompilatora C2275

"Identyfikator": niedozwolone użycie tego typu jako wyrażenia

Wyrażenie używa `->` operatora z **`typedef`** identyfikatorem.

Poniższy przykład generuje C2275:

```cpp
// C2275.cpp
typedef struct S {
    int mem;
} *S_t;
void func1( int *parm );
void func2() {
    func1( &S_t->mem );   // C2275, S_t is a typedef
}
```

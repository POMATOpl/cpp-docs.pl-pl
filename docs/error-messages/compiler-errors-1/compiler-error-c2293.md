---
title: Błąd kompilatora C2293
ms.date: 11/04/2016
f1_keywords:
- C2293
helpviewer_keywords:
- C2293
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
ms.openlocfilehash: 8073e952e8248367c444415cfb182743247dc6fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570641"
---
# <a name="compiler-error-c2293"></a>Błąd kompilatora C2293

'Identyfikator': niedozwolony zmiennej składowej jako specyfikatora __based

Specyfikatory dla `__based` modyfikator musi być niebędących wskaźników.

Poniższy przykład spowoduje wygenerowanie C2293:

```
// C2293.cpp
// compile with: /c
class A {
   static int *i;
   void __based(i) *bp;   // C2293
   void *bp2;   // OK
};
```
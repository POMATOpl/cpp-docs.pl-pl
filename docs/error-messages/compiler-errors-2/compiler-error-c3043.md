---
title: Błąd kompilatora C3043
ms.date: 11/04/2016
f1_keywords:
- C3043
helpviewer_keywords:
- C3043
ms.assetid: 0ef55e63-e82b-48eb-9d44-690950ac34c6
ms.openlocfilehash: 75ab43576a3b2135e174ba512ad8a46aa330f750
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386671"
---
# <a name="compiler-error-c3043"></a>Błąd kompilatora C3043

Dyrektywa "critical" OpenMP nie może być zagnieżdżona w dyrektywie "critical" o takiej samej nazwie

A [krytyczne](../../parallel/openmp/reference/critical.md) dyrektywy nie może być zagnieżdżona w `critical` dyrektywę, który używa tej samej nazwie.

Poniższy przykład spowoduje wygenerowanie C3043:

```
// C3043.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n1 = 1, n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp critical(MyTest)
      {
         ++n2;

         #pragma omp critical(MyTest)   // C3043
         // try the following line instead
         // #pragma omp critical(MyTest2)
         {
            ++n3;
         }
      }
   }
}
```
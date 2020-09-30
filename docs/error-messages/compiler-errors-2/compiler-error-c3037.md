---
title: Błąd kompilatora C3037
ms.date: 11/04/2016
f1_keywords:
- C3037
helpviewer_keywords:
- C3037
ms.assetid: 9ba8a890-d3c7-4cce-93c5-d358e2bfad28
ms.openlocfilehash: f7a2e4cfe40366db06e2418616825ef467a2271a
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508463"
---
# <a name="compiler-error-c3037"></a>Błąd kompilatora C3037

"var": zmienna w klauzuli "redukcyjn" musi być udostępniona w załączonym kontekście

Zmienna określona w klauzuli [redukcyjnej](../../parallel/openmp/reference/openmp-clauses.md#reduction) nie może być prywatna dla każdego wątku w kontekście.

Poniższy przykład generuje C3037:

```cpp
// C3037.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel private(g_i)
   // try the following line instead
   // #pragma omp parallel
   {
      #pragma omp for reduction(+:g_i)   // C3037
      for (i = 0 ; i < 10 ; ++i) {
         g_i += i;
      }
   }
}
```

---
title: Błąd kompilatora C3038
ms.date: 11/04/2016
f1_keywords:
- C3038
helpviewer_keywords:
- C3038
ms.assetid: 140ada3e-5636-43ef-a4ee-22a9f66a771f
ms.openlocfilehash: 7da7dcf1f03c05511ba4bb970e898bc06b9ae3bd
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508417"
---
# <a name="compiler-error-c3038"></a>Błąd kompilatora C3038

"var": zmienna w klauzuli "Private" nie może być zmienną redukcyjną w załączonym kontekście

Zmienne, które pojawiają się w klauzuli [redukcyjnej](../../parallel/openmp/reference/openmp-clauses.md#reduction) dyrektywy równoległej, nie mogą być określone w [prywatnej](../../parallel/openmp/reference/openmp-clauses.md#private-openmp) klauzuli w dyrektywie dotyczącej udostępniania pracy, która jest powiązana z konstrukcją równoległą.

Poniższy przykład generuje C3038:

```cpp
// C3038.cpp
// compile with: /openmp /c
int g_i, g_i2;

int main() {
   int i;

   #pragma omp parallel reduction(+: g_i)
   {
      #pragma omp for private(g_i)   // C3038
      // try the following line instead
      // #pragma omp for private(g_i2)
      for (i = 0; i < 10; ++i)
         g_i += i;
   }
}
```

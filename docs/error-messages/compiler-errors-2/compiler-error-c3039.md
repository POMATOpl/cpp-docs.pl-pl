---
description: 'Dowiedz się więcej o: błąd kompilatora C3039'
title: Błąd kompilatora C3039
ms.date: 11/04/2016
f1_keywords:
- C3039
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
ms.openlocfilehash: e84f769e49fa2b06eea2b1fe0b53ea2d935efb9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270020"
---
# <a name="compiler-error-c3039"></a>Błąd kompilatora C3039

"var": zmienna index w instrukcji "for" OpenMP nie może być zmienną redukcyjną

Zmienna indeksu jest niejawnie prywatna, więc zmienna nie może być używana w klauzuli [redukcyjnej](../../parallel/openmp/reference/openmp-clauses.md#reduction) w otaczającej dyrektywie [Parallel](../../parallel/openmp/reference/openmp-directives.md#parallel) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3039:

```cpp
// C3039.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel reduction(+: i)
   {
      #pragma omp for
      for (i = 0; i < 10; ++i)   // C3039
         g_i += i;
   }
}
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C3015'
title: Błąd kompilatora C3015
ms.date: 11/04/2016
f1_keywords:
- C3015
helpviewer_keywords:
- C3015
ms.assetid: d5e8e50b-7542-4b2d-8665-1b22072a5bc6
ms.openlocfilehash: 84d1431ef04b16631ba6f32aa9b41dc08cef8f2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285880"
---
# <a name="compiler-error-c3015"></a>Błąd kompilatora C3015

Inicjalizacja w instrukcji "for" OpenMP posiada niewłaściwy formularz

**`for`** Pętla w instrukcji OpenMP musi być w pełni i jawnie określona.

Poniższy przykład generuje C3015:

```cpp
// C3015.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (; i < 0; i += j)   // C3015
      // Try the following line instead:
      // for (i = 0; i < 0; i++)
         --j;
   }
}
```

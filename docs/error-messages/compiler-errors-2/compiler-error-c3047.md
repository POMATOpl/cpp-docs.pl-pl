---
description: 'Dowiedz się więcej o: błąd kompilatora C3047'
title: Błąd kompilatora C3047
ms.date: 11/04/2016
f1_keywords:
- C3047
helpviewer_keywords:
- C3047
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
ms.openlocfilehash: 471f85f6a73e911ea9c308a3de9d2afbe800f750
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269786"
---
# <a name="compiler-error-c3047"></a>Błąd kompilatora C3047

Blok strukturalny w regionie "sections" OpenMP musi być poprzedzony przez "#pragma sekcji OMP"

Każdy kod w bloku kodu wprowadzony [przez dyrektywę](../../parallel/openmp/reference/openmp-directives.md#sections-openmp) sections musi znajdować się w bloku kodu wprowadzonym przez `section` dyrektywę.

Poniższy przykład generuje C3047:

```cpp
// C3047.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {

         #pragma omp section
         {
            ++n3;
         }

         ++n2;   // C3047 not enclosed in #pragma omp section
      }
   }
}
```

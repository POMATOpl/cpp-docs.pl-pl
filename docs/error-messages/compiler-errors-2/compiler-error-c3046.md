---
description: 'Dowiedz się więcej o: błąd kompilatora C3046'
title: Błąd kompilatora C3046
ms.date: 11/04/2016
f1_keywords:
- C3046
helpviewer_keywords:
- C3046
ms.assetid: 2e53d835-faa1-4ec0-9807-41f3dc552635
ms.openlocfilehash: aee37f1f1921c62614dc5e40de4514403b92c91a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269812"
---
# <a name="compiler-error-c3046"></a>Błąd kompilatora C3046

Brak bloku strukturalnego w regionie "#pragma OMP sekcji" OpenMP

Dyrektywa [](../../parallel/openmp/reference/openmp-directives.md#sections-openmp) sections ma pusty blok kodu.

Poniższy przykład generuje C3046:

```cpp
// C3046.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {
/*
         ++n2;

         #pragma omp section
         {
            ++n3;
         }
*/
       }   // C3046 uncomment code to resolve this C3046
   }
}
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C3045'
title: Błąd kompilatora C3045
ms.date: 11/04/2016
f1_keywords:
- C3045
helpviewer_keywords:
- C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
ms.openlocfilehash: 0d39399d656a482d401eafb51f53c177c8c3bb2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269851"
---
# <a name="compiler-error-c3045"></a>Błąd kompilatora C3045

Oczekiwano złożonej instrukcji po dyrektywie "sections" OpenMP. Brak znaku "{"

Blok kodu rozdzielony przez nawiasy klamrowe musi być zgodny z [sekcją](../../parallel/openmp/reference/openmp-directives.md#sections-openmp) dyrektywy.

Poniższy przykład generuje C3045:

```cpp
// C3045.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
         ++n2;   // C3045

      #pragma omp sections   // OK
      {
         ++n3;
      }
   }
}
```

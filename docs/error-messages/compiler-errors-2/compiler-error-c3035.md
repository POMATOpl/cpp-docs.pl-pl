---
description: 'Dowiedz się więcej o: błąd kompilatora C3035'
title: Błąd kompilatora C3035
ms.date: 11/04/2016
f1_keywords:
- C3035
helpviewer_keywords:
- C3035
ms.assetid: af34fad2-2b45-42d0-a9ff-04eab3e91c37
ms.openlocfilehash: df5e167e662f856a7d156828962fe68680673207
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270137"
---
# <a name="compiler-error-c3035"></a>Błąd kompilatora C3035

Dyrektywa "ordered" OpenMP musi powiązać bezpośrednio z dyrektywą "for" lub "Parallel for" z klauzulą "ordered"

Klauzula uporządkowana jest źle sformułowana.

Poniższy przykład generuje C3035:

```cpp
// C3035.cpp
// compile with: /openmp /link vcomps.lib
int main() {
   int n = 0, x, i;

   #pragma omp parallel private(n)
   {
      #pragma omp ordered   // C3035
      // Try the following line instead:
      // #pragma omp for ordered
       for (i = 0 ; i < 10 ; ++i)
         ;
   }
}
```

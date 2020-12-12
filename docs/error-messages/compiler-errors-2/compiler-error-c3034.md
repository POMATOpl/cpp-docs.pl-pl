---
description: 'Dowiedz się więcej o: błąd kompilatora C3034'
title: Błąd kompilatora C3034
ms.date: 11/04/2016
f1_keywords:
- C3034
helpviewer_keywords:
- C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
ms.openlocfilehash: 379fedfe3af65b2def83d737daeccac670838c2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270176"
---
# <a name="compiler-error-c3034"></a>Błąd kompilatora C3034

Dyrektywa "directive1" OpenMP nie może być bezpośrednio zagnieżdżona w dyrektywie "directive2"

Niektóre dyrektywy nie mogą być zagnieżdżane. Aby naprawić ten błąd, można scalić instrukcje obu dyrektyw w bloku jednej dyrektywy lub można skonstruować kolejne dyrektywy.

Poniższy przykład generuje C3034:

```cpp
// C3034.cpp
// compile with: /openmp /link vcomps.lib
int main() {

   #pragma omp single
   {
      #pragma omp single   // C3034
      {
      ;
      }
   }

   // Two consecutive single clauses are OK.
   #pragma omp single
   {
   }

   #pragma omp single
   {
   }
}
```

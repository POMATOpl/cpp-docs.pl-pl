---
description: 'Dowiedz się więcej o: błąd kompilatora C3010'
title: Błąd kompilatora C3010
ms.date: 11/04/2016
f1_keywords:
- C3010
helpviewer_keywords:
- C3010
ms.assetid: e959d038-bba6-432a-9c0a-0470474de7d9
ms.openlocfilehash: 50467ad1cb03255cbb5ef008e2ac2897de4a6a5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305315"
---
# <a name="compiler-error-c3010"></a>Błąd kompilatora C3010

"label": Wyskocz z strukturalnego bloku OpenMP jest niedozwolony

Kod nie może przeskoczyć do lub z bloku OpenMP.

Poniższy przykład generuje C3010:

```c
// C3010.c
// compile with: /openmp
int main() {
   #pragma omp parallel
   {
      #pragma omp parallel
      {
         goto lbl3;
      }
   }
   lbl3:;   // C3010
}
```

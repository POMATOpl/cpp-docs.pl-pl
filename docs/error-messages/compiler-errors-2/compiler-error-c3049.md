---
title: Compiler Error C3049
ms.date: 11/04/2016
f1_keywords:
- C3049
helpviewer_keywords:
- C3049
ms.assetid: 6ddf54f6-2c30-4d04-b637-98c6c922c533
ms.openlocfilehash: ca8481eb06a7ec679b27a446bf738f2ad018f79d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187464"
---
# <a name="compiler-error-c3049"></a>Compiler Error C3049

"argument": nieprawidłowy argument w klauzuli "default" OpenMP

Nieprawidłowa wartość został przekazany do [domyślne](../../parallel/openmp/reference/default-openmp.md) klauzuli.

Poniższy przykład spowoduje wygenerowanie C3049:

```
// C3049.cpp
// compile with: /openmp /c
int main() {
   int n1 = 1;

   #pragma omp parallel default(private)   // C3049
   // try the following line instead
   // #pragma omp parallel default(shared)
   {
      ++n1;
   }
}
```
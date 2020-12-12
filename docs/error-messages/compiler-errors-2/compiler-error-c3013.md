---
description: 'Dowiedz się więcej o: błąd kompilatora C3013'
title: Błąd kompilatora C3013
ms.date: 11/04/2016
f1_keywords:
- C3013
helpviewer_keywords:
- C3013
ms.assetid: f896777d-27e6-4b6d-baab-1567317f3374
ms.openlocfilehash: 4c84cce635516ee62533c83716708b9075077eb8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285971"
---
# <a name="compiler-error-c3013"></a>Błąd kompilatora C3013

"klauzula": klauzula może występować tylko raz w dyrektywie OpenMP "dyrektywy"

Klauzula pojawiła się dwukrotnie w tej samej dyrektywie. Usuń jedno wystąpienie klauzuli.

Poniższy przykład generuje C3013:

```cpp
// C3013.cpp
// compile with: /openmp
int main() {
   int a, b, c, x, y, z;

   #pragma omp parallel shared(a,b,c) private(x)

   #pragma omp for nowait private(x) nowait   // C3013
   // The previous line generates C3013, with two nowait clauses
   // try the following line instead:
   // #pragma omp for nowait private(x)
   for (a = 0 ; a < 10 ; ++a) {
   }
}
```

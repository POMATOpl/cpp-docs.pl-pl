---
description: 'Dowiedz się więcej o: błąd kompilatora C3059'
title: Błąd kompilatora C3059
ms.date: 11/04/2016
f1_keywords:
- C3059
helpviewer_keywords:
- C3059
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
ms.openlocfilehash: 82629fb77a0cf589f4e311d951fcf1540e0b7c8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281759"
---
# <a name="compiler-error-c3059"></a>Błąd kompilatora C3059

"var": symbol "threadprivate" nie może być używany w klauzuli "klauzula"

W klauzuli użyto symbolu [threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) .

Poniższy przykład generuje C3059:

```cpp
// C3059.cpp
// compile with: /openmp
#include "omp.h"
int x, y;
#pragma omp threadprivate(x, y)

int main() {
   #pragma omp parallel private(x, y)   // C3059
   {
      x = y;
   }
}
```

Możliwe rozwiązanie:

```cpp
// C3059b.cpp
// compile with: /openmp
#include "omp.h"
int x = 0, y = 0;

int main() {
   #pragma omp parallel firstprivate(y) private(x)
   {
      x = y;
   }
}
```

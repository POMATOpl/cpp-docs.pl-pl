---
description: 'Dowiedz się więcej o: błąd kompilatora C3058'
title: Błąd kompilatora C3058
ms.date: 11/04/2016
f1_keywords:
- C3058
helpviewer_keywords:
- C3058
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
ms.openlocfilehash: 9a7c4c3fa4fd8186055985ff66caa3ffd0c4f081
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269461"
---
# <a name="compiler-error-c3058"></a>Błąd kompilatora C3058

"symbol": symbol nie został zadeklarowany jako "threadprivate" przed jego użyciem w klauzuli "Copy"

Symbol musi być zadeklarowany jako [threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) , zanim będzie można go użyć w klauzuli [copy](../../parallel/openmp/reference/openmp-clauses.md#copyin) .

Poniższy przykład generuje C3058:

```cpp
// C3058.cpp
// compile with: /openmp
int x, y, z;
#pragma omp threadprivate(x, z)

void test() {
   #pragma omp parallel copyin(x, y)   // C3058
   {
   }
}
```

Możliwe rozwiązanie:

```cpp
// C3058b.cpp
// compile with: /openmp /LD
int x, y, z;
#pragma omp threadprivate(x, y)

void test() {
   #pragma omp parallel copyin(x, y)
   {
   }
}
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C3026'
title: Błąd kompilatora C3026
ms.date: 11/04/2016
f1_keywords:
- C3026
helpviewer_keywords:
- C3026
ms.assetid: 3297060e-cc5b-4600-a2db-09bfc4ffa21f
ms.openlocfilehash: e388fbaca270ab889b7873677ab2b2e8252780a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335074"
---
# <a name="compiler-error-c3026"></a>Błąd kompilatora C3026

"klauzula": stałe wyrażenie musi być dodatnie

Klauzula została przeniesiona jako wartość całkowita, ale wartość nie jest liczbą dodatnią. Liczba musi być dodatnia.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3026:

```cpp
// C3026.cpp
// compile with: /openmp /link vcomps.lib
#include <stdio.h>
#include "omp.h"

int main()
{
    int i;
    const int i1 = 0;

    #pragma omp parallel for num_threads(i1)   // C3026
    for (i = 1; i <= 2; ++i)
        printf_s("Hello World - thread %d - iteration %d\n",
                 omp_get_thread_num(), i);

    #pragma omp parallel for num_threads(i1 + 1)   // OK
    for (i = 1; i <= 2; ++i)
        printf_s("Hello World - thread %d - iteration %d\n",
                 omp_get_thread_num(), i);
}
```

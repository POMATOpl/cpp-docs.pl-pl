---
description: 'Dowiedz się więcej o: błąd kompilatora C3057'
title: Błąd kompilatora C3057
ms.date: 11/04/2016
f1_keywords:
- C3057
helpviewer_keywords:
- C3057
ms.assetid: b0b2ba88-9c74-4bec-bf60-8fc72eade34c
ms.openlocfilehash: 786e2fa80967892200871f5d5fd4b6e64a70c626
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269474"
---
# <a name="compiler-error-c3057"></a>Błąd kompilatora C3057

"symbol": dynamiczna Inicjalizacja symboli "threadprivate" nie jest obecnie obsługiwana

Wartość inicjacji symbolu użytego w klauzuli [threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) musi być znana w czasie kompilacji.

Poniższy przykład generuje C3057:

```cpp
// C3057.cpp
// compile with: /openmp /c
extern int f();
int x, y = f();
int a, b;
#pragma omp threadprivate(x, y)   // C3057

#pragma omp threadprivate(a, b)

int main() {
   // Delete the following 4 lines to resolve.
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }

   #pragma omp parallel copyin(a, b)
   {
      a = b;
   }
}
```

Poniższy przykład generuje C3057:

```cpp
// C3057b.cpp
// compile with: /openmp /c
extern int Initialize();
int main() {
   #pragma omp parallel
   {
      static int var = Initialize();
      #pragma omp threadprivate(var)   // C3057
   }

   // OK
   #pragma omp parallel
   {
      static int var2;
      static bool initialized2;
      #pragma omp threadprivate(var2, initialized2)
      if (!initialized2) {
         var2 = Initialize();
         initialized2 = true;
      }
   }
}
```

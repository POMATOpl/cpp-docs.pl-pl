---
description: 'Dowiedz się więcej o: błąd kompilatora C3020'
title: Błąd kompilatora C3020
ms.date: 11/04/2016
f1_keywords:
- C3020
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
ms.openlocfilehash: b5518419b4b0d2e397ce13aad07ee030d62548bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285776"
---
# <a name="compiler-error-c3020"></a>Błąd kompilatora C3020

"var": zmienna index pętli "for" OpenMP nie może być modyfikowana w treści pętli

**`for`** Pętla OpenMP nie może modyfikować indeksu (licznik pętli) w treści **`for`** pętli.

Poniższy przykład generuje C3020:

```cpp
// C3020.cpp
// compile with: /openmp
int main() {
   int i = 0, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i += n)
         i *= 2;   // C3020
         // try the following line instead
         // n++;
   }
}
```

Zmienna zadeklarowana przy użyciu elementu [lastprivate](../../parallel/openmp/reference/openmp-clauses.md#lastprivate) nie może być używana jako indeks wewnątrz pętli równoległej.

Poniższy przykład daje C3020 dla drugiego lastprivateu, ponieważ ten lastprivate wywoła zapis do idx_a w obrębie zewnętrznej pętli for. Pierwszy lastprivate nie daje błędu, ponieważ lastprivate wyzwala zapis do idx_a poza najbardziej zewnętrznym pętlą for (technicznie, na końcu ostatniej iteracji). Poniższy przykład generuje C3020.

```cpp
// C3020b.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_a)   // C3020
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```

Poniższy przykład demonstruje możliwe rozwiązanie:

```cpp
// C3020c.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_b)
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```

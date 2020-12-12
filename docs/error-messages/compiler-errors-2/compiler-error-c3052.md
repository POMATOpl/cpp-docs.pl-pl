---
description: 'Dowiedz się więcej o: błąd kompilatora C3052'
title: Błąd kompilatora C3052
ms.date: 11/04/2016
f1_keywords:
- C3052
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
ms.openlocfilehash: d9d4ecf6082de02c3a4cec6486b2718a101b22d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269656"
---
# <a name="compiler-error-c3052"></a>Błąd kompilatora C3052

"var": zmienna nie pojawia się w klauzuli udostępniania danych pod klauzulą default (None)

Jeśli jest używana [wartość domyślna (brak)](../../parallel/openmp/reference/openmp-clauses.md#default-openmp) , Każda zmienna użyta w bloku strukturalnym musi być jawnie określona jako [udostępniona](../../parallel/openmp/reference/openmp-clauses.md#shared-openmp) lub [prywatna](../../parallel/openmp/reference/openmp-clauses.md#private-openmp).

Poniższy przykład generuje C3052:

```cpp
// C3052.cpp
// compile with: /openmp /c
int main() {
   int n1 = 1;

   #pragma omp parallel default(none) // shared(n1) private(n1)
   {
      n1 = 0;   // C3052 use either a shared or private clause
   }
}
```

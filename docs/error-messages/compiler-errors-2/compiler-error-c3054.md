---
title: Błąd kompilatora C3054
ms.date: 11/04/2016
f1_keywords:
- C3054
helpviewer_keywords:
- C3054
ms.assetid: 6f4b7ac5-0d12-474b-b611-76ff26ee41ac
ms.openlocfilehash: 7a35f72be07799f61587c77b511395223ae72939
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761192"
---
# <a name="compiler-error-c3054"></a>Błąd kompilatora C3054

element "#pragma OMP Parallel" nie jest obecnie obsługiwany w generycznej klasie lub funkcji

Aby uzyskać więcej informacji, zobacz [typy ogólne](../../extensions/generics-cpp-component-extensions.md) i [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3054.

```cpp
// C3054.cpp
// compile with: /openmp /clr /c
#include <omp.h>

ref struct MyBaseClass {
   // Delete the following 7 lines to resolve.
   generic <class ItemType>
   void Test(ItemType i) {   // C3054
      #pragma omp parallel num_threads(4)
      {
         int i = omp_get_thread_num();
      }
   }

   // OK
   void Test2() {
      #pragma omp parallel num_threads(4)
      {
         int i = omp_get_thread_num();
      }
   }
};
```

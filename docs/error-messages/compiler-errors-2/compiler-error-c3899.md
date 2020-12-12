---
description: 'Dowiedz się więcej o: błąd kompilatora C3899'
title: Błąd kompilatora C3899
ms.date: 11/04/2016
f1_keywords:
- C3899
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
ms.openlocfilehash: 04d8af9427d868b0890899d295f3aa6f678eafce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260049"
---
# <a name="compiler-error-c3899"></a>Błąd kompilatora C3899

"var": wykorzystanie wartości l składowej danych initonly nie jest dozwolone bezpośrednio w ramach równoległego regionu w klasie "Class"

Nie można zainicjować składowej danych [initonly (C++/CLI)](../../dotnet/initonly-cpp-cli.md) wewnątrz tej części konstruktora, która znajduje się w regionie [równoległym](../../parallel/openmp/reference/openmp-directives.md#parallel) .  Dzieje się tak, ponieważ kompilator wykonuje wewnętrzną relokację tego kodu, tak że nie jest już częścią konstruktora.

Aby rozwiązać ten problem, zainicjuj element członkowski danych initonly w konstruktorze, ale poza regionem równoległym.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3899.

```cpp
// C3899.cpp
// compile with: /clr /openmp
#include <omp.h>

public ref struct R {
   initonly int x;
   R() {
      x = omp_get_thread_num() + 1000;   // OK
      #pragma omp parallel num_threads(5)
      {
         // cannot assign to 'x' here
         x = omp_get_thread_num() + 1000;   // C3899
         System::Console::WriteLine("thread {0}", omp_get_thread_num());
      }
      x = omp_get_thread_num() + 1000;   // OK
   }
};

int main() {
   R^ r = gcnew R;
   System::Console::WriteLine(r->x);
}
```

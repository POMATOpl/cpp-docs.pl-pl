---
description: 'Dowiedz się więcej o: błąd kompilatora C3053'
title: Błąd kompilatora C3053
ms.date: 11/04/2016
f1_keywords:
- C3053
helpviewer_keywords:
- C3053
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
ms.openlocfilehash: 8f42d3301ae5980942d33cefc90c74a5a0d39b16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269630"
---
# <a name="compiler-error-c3053"></a>Błąd kompilatora C3053

"symbol": "threadprivate" jest prawidłowy tylko dla elementów danych globalnych lub statycznych

Symbole przesyłane do [threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) muszą być globalne lub statyczne.

Poniższy przykład generuje C3053:

```cpp
// C3053.cpp
// compile with: /openmp
void Test() {
   int x, y;
   #pragma omp threadprivate(x, y)   // C3053
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

Możliwe rozwiązanie:

```cpp
// C3053b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)

void Test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

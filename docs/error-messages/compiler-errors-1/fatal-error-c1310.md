---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1310'
title: Błąd krytyczny C1310
ms.date: 11/04/2016
f1_keywords:
- C1310
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
ms.openlocfilehash: edd4cb75c77ec272ddd3f985b4bfefac93e04e83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177760"
---
# <a name="fatal-error-c1310"></a>Błąd krytyczny C1310

Profilowana Optymalizacja nie jest dostępna w przypadku używania OpenMP

Nie będzie można połączyć się z [/LTCG: PGI](../../build/reference/ltcg-link-time-code-generation.md) żadnego modułu, który został skompilowany przy użyciu [/GL](../../build/reference/gl-whole-program-optimization.md).

Poniższy przykład generuje C1310:

```cpp
// C1310.cpp
// compile with: /openmp /GL /link /LTCG:PGI
// C1310 expected
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 0; i++)
         --j;
   }
}
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C3008'
title: Błąd kompilatora C3008
ms.date: 11/04/2016
f1_keywords:
- C3008
helpviewer_keywords:
- C3008
ms.assetid: 04d93201-28e5-4be0-945c-aad616376f4b
ms.openlocfilehash: 30ec8602ba9759eded7edc642931109216a68967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305341"
---
# <a name="compiler-error-c3008"></a>Błąd kompilatora C3008

"ARG": w argumencie brakuje zamykającego ")" dyrektywy "dyrektywy" OpenMP

Dyrektywa OpenMP, która przyjmuje argument, nie ma nawiasu zamykającego.

Poniższy przykład generuje C3008:

```c
// C3008.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x   // C3008
   // Try the following line instead:
   #pragma omp parallel shared(x)
   {
   }
}
```

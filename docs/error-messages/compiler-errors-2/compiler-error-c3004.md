---
description: 'Dowiedz się więcej o: błąd kompilatora C3004'
title: Błąd kompilatora C3004
ms.date: 11/04/2016
f1_keywords:
- C3004
helpviewer_keywords:
- C3004
ms.assetid: 819c2b57-8366-4ca7-9135-1f0c5e5b6bb6
ms.openlocfilehash: 30737aca11b52fb8eaecc376c38211772442abf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326031"
---
# <a name="compiler-error-c3004"></a>Błąd kompilatora C3004

klauzula "klauzula": nie jest prawidłowa w dyrektywie OpenMP "dyrektywy"

Klauzula OpenMP została użyta w dyrektywie, dla której nie jest włączona.

Poniższy przykład generuje C3004:

```c
// C3004.c
// compile with: /openmp
int main()
{
   int x, y, z;

   // Shared clause not allowed for 'single' directive.
   #pragma omp single shared(x, y)   // C3004

   x = y;
}
```

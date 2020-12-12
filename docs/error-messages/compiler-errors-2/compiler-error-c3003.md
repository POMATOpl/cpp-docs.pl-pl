---
description: 'Dowiedz się więcej o: błąd kompilatora C3003'
title: Błąd kompilatora C3003
ms.date: 11/04/2016
f1_keywords:
- C3003
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
ms.openlocfilehash: 1bed98ebd9e0a383700583e1e23e0a977cb6e3fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326046"
---
# <a name="compiler-error-c3003"></a>Błąd kompilatora C3003

"dyrektywa": Nazwa dyrektywy OpenMP nie jest dozwolona po klauzulach dyrektywy

Nazwa dyrektywy OpenMP nie może być zgodna z klauzulą dyrektywy OpenMP.

Poniższy przykład generuje C3003:

```c
// C3003.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x, y, z) for   // C3003
}
```

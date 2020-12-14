---
description: 'Dowiedz się więcej o: błąd kompilatora C3006'
title: Błąd kompilatora C3006
ms.date: 11/04/2016
f1_keywords:
- C3006
helpviewer_keywords:
- C3006
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
ms.openlocfilehash: e2c6372b86f7677f3beeaed5335798f10e01c82e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274557"
---
# <a name="compiler-error-c3006"></a>Błąd kompilatora C3006

Brak oczekiwanego argumentu klauzuli "klauzula": w dyrektywie OpenMP "dyrektywa"

Dyrektywa OpenMP nie ma oczekiwanego argumentu.

Poniższy przykład generuje C3006:

```c
// C3006.c
// compile with: /openmp
int main()
{
   #pragma omp parallel shared   // C3006
   // Try the following line instead:
   // #pragma omp parallel shared(x) {}

}
```

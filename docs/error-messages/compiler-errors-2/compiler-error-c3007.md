---
title: Błąd kompilatora C3007
ms.date: 11/04/2016
f1_keywords:
- C3007
helpviewer_keywords:
- C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
ms.openlocfilehash: 551fb458ee02e29ae54aeb3382b2016da731808a
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345577"
---
# <a name="compiler-error-c3007"></a>Błąd kompilatora C3007

"argument": klauzula w dyrektywie OpenMP "dyrektywa" nie przyjmuje argumentu

OpenMP — dyrektywa miał argumentu, ale dyrektywa nie przyjmuje argumentu.

Poniższy przykład spowoduje wygenerowanie C3007:

```
// C3007.c
// compile with: /openmp
int main()
{
   #pragma omp parallel for ordered(2)   // C3007
}
```
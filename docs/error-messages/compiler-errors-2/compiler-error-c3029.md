---
title: Błąd kompilatora C3029
ms.date: 11/04/2016
f1_keywords:
- C3029
helpviewer_keywords:
- C3029
ms.assetid: 655eb04d-504a-468d-8c0c-bda1e5f297b7
ms.openlocfilehash: a003a0b8fcba3609c355ae467a11b4024a0529d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658379"
---
# <a name="compiler-error-c3029"></a>Błąd kompilatora C3029

'symbol': może wystąpić tylko raz w udostępnianie danych klauzule OpenMP — dyrektywa

Symbol został użyty więcej niż jeden raz w jedną lub więcej klauzul w dyrektywie. Symbol należy używać tylko raz w dyrektywie.

Poniższy przykład spowoduje wygenerowanie C3029:

```
// C3029.cpp
// compile with: /openmp /link vcomps.lib
#include "omp.h"

int g_i;

int main() {
   int i, x;

   #pragma omp parallel reduction(+ : x, x)   // C3029
      ;

   #pragma omp parallel reduction(+ : x)   // OK
      ;

   #pragma omp parallel private(x) reduction(+ : x)   // C3029
      ;

   #pragma omp parallel reduction(+ : x)   // OK
      ;
}
```
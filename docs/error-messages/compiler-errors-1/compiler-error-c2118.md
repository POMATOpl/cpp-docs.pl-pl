---
title: Błąd kompilatora C2118
ms.date: 11/04/2016
f1_keywords:
- C2118
helpviewer_keywords:
- C2118
ms.assetid: bf4315d0-f085-4323-b813-96ee61a13bde
ms.openlocfilehash: 71b8273aaee52420f8a9c9c2dd2d015bea72ddf6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465939"
---
# <a name="compiler-error-c2118"></a>Błąd kompilatora C2118

ujemny indeks dolny

Wartość definiujący rozmiar tablicy jest większy niż maksymalny rozmiar tablicy lub mniejsza niż zero.

Poniższy przykład spowoduje wygenerowanie C2118:

```
// C2118.cpp
int main() {
   int array1[-1];   // C2118
   int array2[3];   // OK
}
```
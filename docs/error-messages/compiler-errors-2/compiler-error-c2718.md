---
title: Błąd kompilatora C2718
ms.date: 11/04/2016
f1_keywords:
- C2718
helpviewer_keywords:
- C2718
ms.assetid: 78cc71f8-c142-46fc-9aed-970635d74f0c
ms.openlocfilehash: 00ad8da46364cd4a48ebdfde8b4de960e4e015f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473011"
---
# <a name="compiler-error-c2718"></a>Błąd kompilatora C2718

"parametru": rzeczywisty parametr z __declspec(align('#')) nie zostanie wyrównany

[Wyrównać](../../cpp/align-cpp.md) `__declspec` modyfikator nie jest dozwolona w parametrów funkcji.

Poniższy przykład spowoduje wygenerowanie C2718:

```
// C2718.cpp
typedef struct __declspec(align(32)) AlignedStruct  {
   int i;
} AlignedStruct;

void f2(int i, ...);

void f4() {
   AlignedStruct as;

   f2(0, as);   // C2718, actual parameter is aligned
}
```
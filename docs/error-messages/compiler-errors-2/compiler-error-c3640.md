---
title: Błąd kompilatora C3640
ms.date: 11/04/2016
f1_keywords:
- C3640
helpviewer_keywords:
- C3640
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
ms.openlocfilehash: 5d9becbdfad2afc8940a9e1ded08a15842607e4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470190"
---
# <a name="compiler-error-c3640"></a>Błąd kompilatora C3640

"członek": odwołanie lub wirtualna składowa lokalnej klasy musi być zdefiniowany.

Kompilator wymaga pewnych funkcji, należy zdefiniować.

Poniższy przykład spowoduje wygenerowanie C3640:

```
// C3640.cpp
void f()
{
   struct S
   {
      virtual void f1();   // C3640
      // Try the following line instead:
      // virtual void f1(){}
   };
}
```
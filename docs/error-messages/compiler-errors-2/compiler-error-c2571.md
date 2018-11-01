---
title: Błąd kompilatora C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: d7d4898e5f0b55c50a4c18cef053cc150394d7e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485075"
---
# <a name="compiler-error-c2571"></a>Błąd kompilatora C2571

'Funkcja': funkcja wirtualna nie może być w Unii "union"

Unii jest zadeklarowana za pomocą funkcji wirtualnej. Można zadeklarować funkcję wirtualną tylko w klasie lub strukturze.  Możliwe rozwiązania:

1. Zmień Unii klasy lub struktury.

1. Ustaw funkcję niewirtualne.

Poniższy przykład spowoduje wygenerowanie C2571:

```
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```
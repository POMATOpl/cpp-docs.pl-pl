---
description: 'Dowiedz się więcej o: błąd kompilatora C2571'
title: Błąd kompilatora C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: 773cab05204e15a22a4412364bd8f89cddfd92ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208973"
---
# <a name="compiler-error-c2571"></a>Błąd kompilatora C2571

"Function": funkcja wirtualna nie może być w Unii "Union"

Unia jest zadeklarowana za pomocą funkcji wirtualnej. Funkcję wirtualną można zadeklarować tylko w klasie lub strukturze.  Możliwe rozwiązania:

1. Zmień Unię na klasę lub strukturę.

1. Ustaw niewirtualną funkcję.

Poniższy przykład generuje C2571:

```cpp
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```

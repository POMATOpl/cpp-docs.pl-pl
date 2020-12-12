---
description: 'Dowiedz się więcej o: błąd kompilatora C2583'
title: Błąd kompilatora C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: 067e65f6085d033ca8d7372ee5e4d169e1b411dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177695"
---
# <a name="compiler-error-c2583"></a>Błąd kompilatora C2583

"Identyfikator": "const/volatile" wskaźnik "This" jest niedozwolony dla konstruktorów/destruktorów

Konstruktor lub destruktor jest zadeklarowany **`const`** lub **`volatile`** . Jest to niedozwolone.

Poniższy przykład generuje C2583:

```cpp
// C2583.cpp
// compile with: /c
class A {
public:
   int i;
   A() const;   // C2583

   // try the following line instead
   // A();
};
```

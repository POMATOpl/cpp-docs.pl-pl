---
title: Błąd kompilatora C2351
ms.date: 11/04/2016
f1_keywords:
- C2351
helpviewer_keywords:
- C2351
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
ms.openlocfilehash: 6839d0c44efa10ba9507389fea35964fa748d646
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759974"
---
# <a name="compiler-error-c2351"></a>Błąd kompilatora C2351

przestarzała C++ składnia inicjalizacji konstruktora

Na liście inicjalizacji nowego stylu dla konstruktora należy jawnie nazwać każdą bezpośrednią klasę bazową, nawet jeśli jest jedyną klasą bazową.

Poniższy przykład generuje C2351:

```cpp
// C2351.cpp
// compile with: /c
class B {
public:
   B() : () {}   // C2351
   B() {}   // OK
};
```

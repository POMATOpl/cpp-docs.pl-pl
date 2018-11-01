---
title: Błąd kompilatora C2876
ms.date: 11/04/2016
f1_keywords:
- C2876
helpviewer_keywords:
- C2876
ms.assetid: 8b674bf1-f9f4-4a8e-8127-e884c1d1708f
ms.openlocfilehash: e7fcdeaf79728ee99498c69de0205619d16612d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664727"
---
# <a name="compiler-error-c2876"></a>Błąd kompilatora C2876

"class::symbol": nie wszystkie przeciążenia są dostępne

Wszystkie formularze przeciążonej funkcji w klasie podstawowej musi być dostępna dla klasy pochodnej.

Poniższy przykład spowoduje wygenerowanie C2876:

```
// C2876.cpp
// compile with: /c
class A {
public:
   double a(double);
private:
   int a(int);
};

class B : public A {
   using A::a;   // C2876 one overload is private in base class
};
```
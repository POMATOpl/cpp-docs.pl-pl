---
title: Błąd kompilatora C2877
ms.date: 11/04/2016
f1_keywords:
- C2877
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
ms.openlocfilehash: 093efbf0c329967983c1808ee46011425745515f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595810"
---
# <a name="compiler-error-c2877"></a>Błąd kompilatora C2877

'symbol' nie jest dostępny z "class"

Wszystkie elementy członkowskie pochodzi od klasy podstawowej musi być dostępny w klasie pochodnej.

Poniższy przykład spowoduje wygenerowanie C2877:

```
// C2877.cpp
// compile with: /c
class A {
private:
   int a;
};

class B : public A {
   using A::a;   // C2877
};
```
---
title: Błąd kompilatora C3903
ms.date: 11/04/2016
f1_keywords:
- C3903
helpviewer_keywords:
- C3903
ms.assetid: cf47d7ad-a3bd-4f75-a253-71586e7a3be6
ms.openlocfilehash: bed6561d1e8d4281cd57e78808744d018c3cc9b3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58774896"
---
# <a name="compiler-error-c3903"></a>Błąd kompilatora C3903

"właściwość": jest nie zostały ustawione lub get, metoda

Właściwość musi mieć co najmniej jeden `get` lub `set` metody. Aby uzyskać więcej informacji, zobacz [właściwość](../../extensions/property-cpp-component-extensions.md).

Poniższy przykład spowoduje wygenerowanie C3903:

```
// C3903.cpp
// compile with: /clr
ref class X {
   property int P {
      void f(int){}
      // Add one or both of the following lines.
      // void set(int){}
      // int get(){return 0;}
   };   // C3903

   property double Q[,,,,] {
      void f(){}
      // Add one or both of the following lines.
      // void set(int, char, int, char, double, double){}
      // double get(int, char, int, char, double){return 1.1;}
   }   // C3903
};
```
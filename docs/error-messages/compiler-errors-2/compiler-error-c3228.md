---
description: 'Dowiedz się więcej o: błąd kompilatora C3228'
title: Błąd kompilatora C3228
ms.date: 11/04/2016
f1_keywords:
- C3228
helpviewer_keywords:
- C3228
ms.assetid: 9015adf9-17b0-4312-b4a7-c1f33e4126f4
ms.openlocfilehash: f245555674d7ce9dcd48697d7ff1fd3016750f40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304132"
---
# <a name="compiler-error-c3228"></a>Błąd kompilatora C3228

"Function": argument typu generycznego dla elementu "param" nie może być typem "Type", musi być typem ValueType lub dojściem

Przekazano nieprawidłowy typ jako argument typu ogólnego.

Poniższy przykład generuje C3228:

```cpp
// C3228.cpp
// compile with: /clr
class A {};

value class B {};

generic <class T>
void Test() {}

ref class C {
public:
   generic <class T>
   static void f() {}
};

int main() {
   C::f<A>();   // C3228
   C::f<B>();   // OK

   Test<C>();   // C3228
   Test<C ^>();   // OK
}
```

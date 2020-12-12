---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 2) C4356'
title: Ostrzeżenie kompilatora (poziom 2) C4356
ms.date: 11/04/2016
f1_keywords:
- C4356
helpviewer_keywords:
- C4356
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
ms.openlocfilehash: 328f177c90b34f17f8f8c5ec480cb829a22f2f14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173574"
---
# <a name="compiler-warning-level-2-c4356"></a>Ostrzeżenie kompilatora (poziom 2) C4356

"member": statyczna składowa danych nie może zostać zainicjowana za pośrednictwem klasy pochodnej

Inicjalizacja statycznego elementu członkowskiego danych została nieprawidłowo sformułowana. Kompilator zaakceptował inicjalizację. Aby uniknąć ostrzeżenia, zainicjuj element członkowski za pomocą klasy bazowej.

Użyj [ostrzeżenia](../../preprocessor/warning.md) pragma, aby pominąć to ostrzeżenie.

Poniższy przykład generuje C4356:

```cpp
// C4356.cpp
// compile with: /W2 /EHsc
#include <iostream>

template <class T>
class C {
   static int n;
};

class D : C<int> {};

int D::n = 0; // C4356
// try the following line instead
// int C<int>::n = 0;

class A {
public:
   static int n;
};

class B : public A {};

int B::n = 10;   // C4356
// try the following line instead
// int A::n = 99;

int main() {
   using namespace std;
   cout << B::n << endl;
}
```

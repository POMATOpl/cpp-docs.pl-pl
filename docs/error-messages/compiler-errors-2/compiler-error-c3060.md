---
description: 'Dowiedz się więcej o: błąd kompilatora C3060'
title: Błąd kompilatora C3060
ms.date: 11/04/2016
f1_keywords:
- C3060
helpviewer_keywords:
- C3060
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
ms.openlocfilehash: a1efe037e75251ef452b0164a2b4e01ea4c38a1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281733"
---
# <a name="compiler-error-c3060"></a>Błąd kompilatora C3060

"member": funkcja zaprzyjaźniona nie może być zdefiniowana wewnątrz klasy przy użyciu kwalifikowanej nazwy (może być tylko zadeklarowana)

Funkcja zaprzyjaźniona została zdefiniowana przy użyciu kwalifikowanej nazwy, co jest niedozwolone.

Poniższy przykład generuje C3060:

```cpp
// C3060.cpp
class A {
public:
   void func();
};

class C {
public:
   friend void A::func() { }   // C3060
   // Try the following line and the out of class definition:
   // friend void A::func();
};

// void A::func(){}
```

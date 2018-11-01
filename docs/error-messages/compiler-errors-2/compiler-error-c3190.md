---
title: Błąd kompilatora C3190
ms.date: 11/04/2016
f1_keywords:
- C3190
helpviewer_keywords:
- C3190
ms.assetid: 7c701afa-85a7-4f7a-8881-0662436ac244
ms.openlocfilehash: 1f30026d8f853aedc863bef4ecfa32b0bd3262b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665325"
---
# <a name="compiler-error-c3190"></a>Błąd kompilatora C3190

"wystąpienia" z argumentami podanymi przez szablon nie jest jawnym utworzeniem wystąpienia jakiejkolwiek funkcji składowej "type"

Kompilator wykrył próby funkcja jawne Tworzenie wystąpienia; Jednakże argumenty podany typ pasuje do żadnego możliwych funkcji.

Poniższy przykład spowoduje wygenerowanie C3190:

```
// C3190.cpp
// compile with: /LD
template<class T>
struct A {
   A(int x = 0) {
   }
   A(int x, int y) {
   }
};

template A<float>::A();   // C3190
// try the following line instead
// template A<int>::A(int);

struct Y {
   template<class T> void f(T);
};

template<class T> void Y::f(T) { }

template void Y::f(int,int);   // C3190

template<class OT> class X {
   template<class T> void f2(T,OT);
};

template<class OT> template<class T> void X<OT>::f2(T,OT) {}

template void X<float>::f2<int>(int,char);   // C3190
// try one of the following lines instead
// template void X<char>::f2(int, char);
// template void X<char>::f2<int>(int,char);
// template void X<char>::f2<>(int,char);
```
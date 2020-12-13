---
description: 'Dowiedz się więcej o: błąd kompilatora C2247'
title: Błąd kompilatora C2247
ms.date: 11/04/2016
f1_keywords:
- C2247
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
ms.openlocfilehash: 480d3862a1f96517ecce11be5c695e106eb58d7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177942"
---
# <a name="compiler-error-c2247"></a>Błąd kompilatora C2247

element "identifier" jest niedostępny, ponieważ Klasa "Class" używa specyfikatora "do dziedziczenia" klasy "

`identifier` jest Dziedziczony z klasy zadeklarowanej z dostępem prywatnym lub chronionym.

Poniższy przykład generuje C2247:

```cpp
// C2247.cpp
class A {
public:
   int i;
};
class B : private A {};    // B inherits a private A
class C : public B {} c;   // so even though C's B is public
int j = c.i;               // C2247, i not accessible
```

Ten błąd może również zostać wygenerowany w wyniku działania kompilatora, który został wykonany dla programu Visual Studio .NET 2003: Kontrola dostępu z chronionymi elementami członkowskimi. Dostęp do chronionej składowej (n) można uzyskać tylko za pośrednictwem funkcji składowej klasy (B), która dziedziczy z klasy (A), z której jest członkiem.

W przypadku kodu, który jest prawidłowy zarówno w programie Visual Studio .NET 2003, jak i w Visual C++ wersji programu Visual Studio .NET, należy zadeklarować element członkowski jako znajomy typu. Można również użyć publicznego dziedziczenia.

```cpp
// C2247b.cpp
// compile with: /c
// C2247 expected
class A {
public:
   void f();
   int n;
};

class B: protected A {
   // Uncomment the following line to resolve.
   // friend void A::f();
};

void A::f() {
   B b;
   b.n;
}
```

C2247 można również wygenerować w wyniku zgodności kompilatora, który został wykonany dla programu Visual Studio .NET 2003: prywatne klasy bazowe są teraz niedostępne. Klasa (A), która jest prywatną klasą bazową do typu (B), nie powinna być dostępna dla typu (C), który używa B jako klasy bazowej.

W przypadku kodu, który jest prawidłowy zarówno w Visual C++ wersjach programu Visual Studio .NET 2003, jak i Visual Studio .NET, użyj operatora Scope.

```cpp
// C2247c.cpp
// compile with: /c
struct A {};

struct B: private A {};

struct C : B {
   void f() {
      A *p1 = (A*) this;   // C2247
      // try the following line instead
      // ::A *p2 = (::A*) this;
   }
};
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C2352'
title: Błąd kompilatora C2352
ms.date: 11/04/2016
f1_keywords:
- C2352
helpviewer_keywords:
- C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
ms.openlocfilehash: f8094261c4a0ad23b5603d1e16bbaa4f34e0038e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298308"
---
# <a name="compiler-error-c2352"></a>Błąd kompilatora C2352

"Class:: Function": niedozwolone wywołanie niestatycznej funkcji składowej

**`static`** Funkcja członkowska o nazwie niestatycznej funkcji członkowskiej. Lub niestatyczna funkcja członkowska została wywołana spoza klasy jako funkcji statycznej.

Poniższy przykład generuje C2352 i pokazuje, jak to naprawić:

```cpp
// C2352.cpp
// compile with: /c
class CMyClass {
public:
   static void func1();
   void func2();
   static void func3() {
      func2();   // C2352 calls nonstatic func2
      func1();   // OK calls static func1
   }
};
```

Poniższy przykład generuje C2352 i pokazuje, jak to naprawić:

```cpp
// C2352b.cpp
class MyClass {
public:
   void MyFunc() {}
   static void MyFunc2() {}
};

int main() {
   MyClass::MyFunc();   // C2352
   MyClass::MyFunc2();   // OK
}
```

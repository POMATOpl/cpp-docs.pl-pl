---
title: Błąd kompilatora C2352
ms.date: 11/04/2016
f1_keywords:
- C2352
helpviewer_keywords:
- C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
ms.openlocfilehash: 387738faa5b55e60cbb9df2185efcb94098011d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388803"
---
# <a name="compiler-error-c2352"></a>Błąd kompilatora C2352

"class::function": niedozwolone wywołanie niestatycznej składowej — funkcja

A `static` funkcji składowej wywołać funkcję niestatycznej składowej. Lub funkcja niestatycznej składowej została wywołana z poza klasy jako funkcję statyczną.

Poniższy przykład generuje C2352 i pokazuje, jak go naprawić:

```
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

Poniższy przykład generuje C2352 i pokazuje, jak go naprawić:

```
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
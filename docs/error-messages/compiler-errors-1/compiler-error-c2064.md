---
description: 'Dowiedz się więcej o: błąd kompilatora C2064'
title: Błąd kompilatora C2064
ms.date: 11/04/2016
f1_keywords:
- C2064
helpviewer_keywords:
- C2064
ms.assetid: 6cda05da-f437-4f50-9813-ae69538713a3
ms.openlocfilehash: dd9f0386267a81d4f92d6dd0474cd9a3292e7345
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328566"
---
# <a name="compiler-error-c2064"></a>Błąd kompilatora C2064

termin nie jest obliczany jako funkcja pobierająca N argumentów

Wykonano wywołanie funkcji za pomocą wyrażenia. Wyrażenie nie oblicza wskaźnika do funkcji, która przyjmuje określoną liczbę argumentów.

W tym przykładzie kod próbuje wywołać niedziałające jako funkcje. Poniższy przykład generuje C2064:

```cpp
// C2064.cpp
int i, j;
char* p;
void func() {
   j = i();    // C2064, i is not a function
   p();        // C2064, p doesn't point to a function
}
```

Należy wywołać wskaźniki do niestatycznych funkcji składowych z kontekstu wystąpienia obiektu. Poniższy przykład generuje C2064 i pokazuje, jak go naprawić:

```cpp
// C2064b.cpp
struct C {
   void func1(){}
   void func2(){}
};

typedef void (C::*pFunc)();

int main() {
   C c;
   pFunc funcArray[2] = {&C::func1, &C::func2};
   (funcArray[0])();    // C2064
   (c.*funcArray[0])(); // OK - function called in instance context
}
```

W obrębie klasy wskaźniki funkcji składowej muszą także wskazywać kontekst obiektu wywołującego. Poniższy przykład generuje C2064 i pokazuje, jak to naprawić:

```cpp
// C2064d.cpp
// Compile by using: cl /c /W4 C2064d.cpp
struct C {
   typedef void (C::*pFunc)();
   pFunc funcArray[2];
   void func1(){}
   void func2(){}
   C() {
      funcArray[0] = &C::func1;
      funcArray[1] = &C::func2;
   }
   void func3() {
      (funcArray[0])();   // C2064
      (this->*funcArray[0])(); // OK - called in this instance context
   }
};
```

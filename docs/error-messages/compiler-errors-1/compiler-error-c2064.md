---
title: Błąd kompilatora C2064 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2064
dev_langs:
- C++
helpviewer_keywords:
- C2064
ms.assetid: 6cda05da-f437-4f50-9813-ae69538713a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7099c8a8371d7a08c95693fffe0d8814303e783e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098113"
---
# <a name="compiler-error-c2064"></a>Błąd kompilatora C2064

termin nie może oszacować funkcja przyjmująca argumenty N

Wykonano wywołanie do funkcji przy użyciu wyrażenia. Wyrażenie nie zostało oszacowane jako wskaźnik do funkcji, która ma określoną liczbę argumentów.

W tym przykładzie kod próbuje wywołać innych funkcji jako funkcje. Poniższy przykład spowoduje wygenerowanie C2064:

```
// C2064.cpp
int i, j;
char* p;
void func() {
   j = i();    // C2064, i is not a function
   p();        // C2064, p doesn't point to a function
}
```

Z tego kontekstu wystąpienia obiektu, należy wywołać wskaźniki do niestatycznych elementów członkowskich. Poniższy przykład generuje C2064 i pokazuje, jak go naprawić:

```
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

W obrębie klasy wskaźniki funkcji elementu członkowskiego musi również wskazać kontekst obiektu wywołującego. Poniższy przykład generuje C2064 i pokazuje, jak go naprawić:

```
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
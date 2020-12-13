---
description: 'Dowiedz się więcej o: błąd kompilatora C2273'
title: Błąd kompilatora C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: 656b5477682ace779cd872b2233d911cfb67c0e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336268"
---
# <a name="compiler-error-c2273"></a>Błąd kompilatora C2273

"Type": niedozwolony po prawej stronie operatora "->"

Typ jest wyświetlany jako prawy operand `->` operatora.

Ten błąd może być spowodowany próbą uzyskania dostępu do konwersji typu zdefiniowanego przez użytkownika. Użyj słowa kluczowego **`operator`** między-> i `type` .

Poniższy przykład generuje C2273:

```cpp
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```

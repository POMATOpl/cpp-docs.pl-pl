---
description: 'Dowiedz się więcej o: błąd kompilatora C3160'
title: Błąd kompilatora C3160
ms.date: 11/04/2016
f1_keywords:
- C3160
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
ms.openlocfilehash: 863670f30a6a911977ead0d541dcba825e4f124a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242330"
---
# <a name="compiler-error-c3160"></a>Błąd kompilatora C3160

"wskaźnik": składowa danych klasy zarządzanej lub WinRT nie może mieć tego typu

Wewnętrzne wskaźniki wyrzucania elementów bezużytecznych mogą wskazywać na wnętrze klasy zarządzanej lub WinRT. Ponieważ są one wolniejsze niż wskaźniki całkowite obiektów i wymagają specjalnej obsługi przez moduł wyrzucania elementów bezużytecznych, nie można zadeklarować wewnętrznych wskaźników zarządzanych jako elementów członkowskich klasy.

Poniższy przykład generuje C3160:

```cpp
// C3160.cpp
// compile with: /clr
ref struct A {
   // cannot create interior pointers inside a class
   interior_ptr<int> pg;   // C3160
   int g;   // OK
   int* pg2;   // OK
};

int main() {
   interior_ptr<int> pg2;   // OK
}
```

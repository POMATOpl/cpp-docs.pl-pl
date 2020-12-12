---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4534'
title: Ostrzeżenie kompilatora (poziom 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 6a13b27716488fa04f6342da76fdcd32c5635f2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257891"
---
# <a name="compiler-warning-level-3-c4534"></a>Ostrzeżenie kompilatora (poziom 3) C4534

Konstruktor nie będzie konstruktorem domyślnym klasy "Class" z powodu argumentu domyślnego

Klasa niezarządzana może mieć Konstruktor z parametrami, które mają wartości domyślne, a kompilator użyje go jako domyślnego konstruktora. Klasa oznaczona przy użyciu `value` słowa kluczowego nie będzie używać konstruktora z wartościami domyślnymi dla jego parametrów jako konstruktora domyślnego.

Aby uzyskać więcej informacji, zobacz [klasy i struktury](../../extensions/classes-and-structs-cpp-component-extensions.md).

Poniższy przykład generuje C4534:

```cpp
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```

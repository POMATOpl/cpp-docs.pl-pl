---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4487'
title: Ostrzeżenie kompilatora (poziom 4) C4487
ms.date: 11/04/2016
f1_keywords:
- C4487
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
ms.openlocfilehash: a750152e6920f9e012f3a1b7d093b68749e6fe8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203474"
---
# <a name="compiler-warning-level-4-c4487"></a>Ostrzeżenie kompilatora (poziom 4) C4487

"derived_class_function": pasuje do dziedziczonej metody niewirtualnej "base_class_function", ale nie jest jawnie oznaczona modyfikatorem "New"

Funkcja w klasie pochodnej ma ten sam podpis co niewirtualna funkcja klasy bazowej. C4487 przypomina o tym, że funkcja klasy pochodnej nie przesłania funkcji klasy bazowej. Jawnie Oznacz funkcję klasy pochodnej jako, **`new`** Aby rozwiązać to ostrzeżenie.

Aby uzyskać więcej informacji, zobacz [Nowość (nowe miejsce w tabeli tablic wirtualnych)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4487.

```cpp
// C4487.cpp
// compile with: /W4 /clr
using namespace System;
public ref struct B {
   void f() { Console::WriteLine("in B::f"); }
   void g() { Console::WriteLine("in B::g"); }
};

public ref struct D : B {
   void f() { Console::WriteLine("in D::f"); }   // C4487
   void g() new { Console::WriteLine("in D::g"); }   // OK
};

int main() {
   B ^ a = gcnew D;
   // will call base class functions
   a->f();
   a->g();
}
```

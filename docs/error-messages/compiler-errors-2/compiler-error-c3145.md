---
description: 'Dowiedz się więcej o: błąd kompilatora C3145'
title: Błąd kompilatora C3145
ms.date: 11/04/2016
f1_keywords:
- C3145
helpviewer_keywords:
- C3145
ms.assetid: f165c874-0f51-45c7-85e8-ebe321cbc168
ms.openlocfilehash: 5410273dd1ceff38c8a234ba1d76ca1bf5283287
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204007"
---
# <a name="compiler-error-c3145"></a>Błąd kompilatora C3145

"Object": globalna lub statyczna zmienna może nie mieć typu zarządzanego lub WinRT "Type"

W zakresie funkcji można definiować tylko obiekty CLR lub WinRT.

Poniższy przykład generuje C3145 i pokazuje, jak to naprawić:

```cpp
// C3145.cpp
// compile with: /clr
using namespace System;
ref class G {};

G ^ ptr;   // C3145
G ^ ptr2 = gcnew G;   // C3145

ref class GlobalObjects {
public:
   static G ^ ptr;   // OK
   static G ^ ptr2 = gcnew G;   // OK
};

int main() {
   G ^ ptr;   // OK
   G ^ ptr2 = gcnew G;   // OK
}
```

Poniższy przykład generuje C3145:

```cpp
// C3145b.cpp
// compile with: /clr
ref class MyClass {
public:
   static int data;
};

interior_ptr<int> p = &(MyClass::data);   // C3145

void Test(interior_ptr<int> x) {}

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;
   interior_ptr<int> p = &(h_MyClass->data);
}
```

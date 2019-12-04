---
title: Błąd kompilatora C3673
ms.date: 11/04/2016
f1_keywords:
- C3673
helpviewer_keywords:
- C3673
ms.assetid: bb6d2079-05af-4e2c-be0e-75c892e6c590
ms.openlocfilehash: 50585904f125dcb572043b568978d65eb1c61e80
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758089"
---
# <a name="compiler-error-c3673"></a>Błąd kompilatora C3673

"Type": Klasa nie posiada konstruktora kopiującego

Konstruktor zdefiniowany przez użytkownika jest wymagany do kopiowania obiektów typów ref CLR. Aby uzyskać więcej informacji, zobacz [ C++ semantyka stosu dla typów referencyjnych](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3673.

```cpp
// C3673.cpp
// compile with: /clr
public ref struct R {
public:
   R() {}
   // Uncomment the following line to resolve.
   // R(R% p) {}
};

int main() {
   R r;
   R s = r;   // C3673
}
```

## <a name="example"></a>Przykład

Poniższy przykład generuje C3673.

```cpp
// C3673_b.cpp
// compile with: /clr /c
// C3673 expected
using namespace System;
[AttributeUsage(AttributeTargets::Class)]
ref class MyAttr : public Attribute {
public:
   MyAttr() {}
   // Uncomment the following line to resolve.
   // MyAttr(int i) {}
   property int Priority;
   property int Version;
};

[MyAttr]
ref class ClassA {};   // OK, no arguments

[MyAttr(Priority = 1)]
ref class ClassB {};   // OK, named argument

[MyAttr(123)]
ref class ClassC {};   // Positional argument

[MyAttr(123, Version = 1)]
ref class ClassD {};   // Positional and named
```

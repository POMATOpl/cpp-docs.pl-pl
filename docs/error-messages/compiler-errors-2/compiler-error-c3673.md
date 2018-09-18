---
title: Błąd kompilatora C3673 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3673
dev_langs:
- C++
helpviewer_keywords:
- C3673
ms.assetid: bb6d2079-05af-4e2c-be0e-75c892e6c590
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0dbc811c948091b68f07ddf732c425b63be5cba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066942"
---
# <a name="compiler-error-c3673"></a>Błąd kompilatora C3673

"type": klasa nie ma konstruktora kopiującego

Konstruktor zdefiniowany przez użytkownika jest potrzebny do skopiowania obiektów typach ref środowiska CLR. Aby uzyskać więcej informacji, zobacz [semantyka stosu C++ dla typów odwołań](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3673.

```
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

Poniższy przykład spowoduje wygenerowanie C3673.

```
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
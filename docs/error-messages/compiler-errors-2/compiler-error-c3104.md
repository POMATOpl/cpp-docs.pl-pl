---
title: Błąd kompilatora C3104
ms.date: 11/04/2016
f1_keywords:
- C3104
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
ms.openlocfilehash: fee023809246634f2f3da266a718e45861eae76e
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447835"
---
# <a name="compiler-error-c3104"></a>Błąd kompilatora C3104

Niedozwolony argument atrybutu

Określono nieprawidłowy argument do atrybutu.

Zobacz [typy parametrów atrybutu](../../extensions/attribute-parameter-types-cpp-component-extensions.md) Aby uzyskać więcej informacji.

Ten błąd można wygenerować w wyniku pracy zgodności kompilatora, która została wykonana dla programu Visual Studio 2005: podczas przekazywania tablic do atrybutów niestandardowych, typ tablicy nie jest już jest wyprowadzony z listy inicjowania agregacji. Kompilator teraz wymaga określenia typu tablicy, jak również lista inicjatora.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3104.

```
// C3104a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104
// try the following line instead
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3104.

```
// C3104b.cpp
// compile with: /clr /c
// C3104 expected
using namespace System;

int func() {
   return 0;
}

[attribute(All)]
ref class A {
public:
   A(int) {}
};

// Delete the following 2 lines to resolve.
[A(func())]
ref class B {};

// OK
[A(0)]
ref class B {};
```

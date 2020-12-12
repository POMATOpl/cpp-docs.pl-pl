---
description: 'Dowiedz się więcej o: błąd kompilatora C3764'
title: Błąd kompilatora C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: d4bd2db494acbcdbbec2e40c72aff300cae1a38e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291743"
---
# <a name="compiler-error-c3764"></a>Błąd kompilatora C3764

"override_function": nie można przesłonić metody klasy bazowej "base_class_function"

Kompilator wykrył źle sformułowane przesłonięcie. Na przykład funkcja klasy bazowej nie została **`virtual`** . Aby uzyskać więcej informacji, zobacz [override](../../extensions/override-cpp-component-extensions.md).

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3764.

```cpp
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

C3764 może również wystąpić, gdy metoda klasy bazowej jest zarówno jawnie, jak i nazwą przesłoniętą. Poniższy przykład generuje C3764.

```cpp
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```

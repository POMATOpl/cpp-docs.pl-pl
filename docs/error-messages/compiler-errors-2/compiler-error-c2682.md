---
description: 'Dowiedz się więcej o: błąd kompilatora C2682'
title: Błąd kompilatora C2682
ms.date: 11/04/2016
f1_keywords:
- C2682
helpviewer_keywords:
- C2682
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
ms.openlocfilehash: 962debb0227347abe97e290db724fdb227212914
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177435"
---
# <a name="compiler-error-c2682"></a>Błąd kompilatora C2682

nie można użyć casting_operator do konwersji z "type1" na "type2"

Operator rzutowania próbował wykonać konwersję między niezgodnymi typami. Na przykład nie można użyć operatora [dynamic_cast](../../cpp/dynamic-cast-operator.md) , aby skonwertować wskaźnik na odwołanie. **`dynamic_cast`** Nie można użyć operatora do rzutowania kwalifikatorów. Wszystkie kwalifikatory typów muszą być zgodne.

Możesz użyć operatora, **`const_cast`** Aby usunąć atrybuty, takie jak **`const`** , **`volatile`** , lub **`__unaligned`** .

Poniższy przykład generuje C2682:

```cpp
// C2682.cpp
class A { virtual void f(); };
class B: public A {};

void g(A* pa) {
    B& rb = dynamic_cast<B&>(pa); // C2682
}
```

Poniższy przykład generuje C2682:

```cpp
// C2682b.cpp
// compile with: /clr
ref struct R{};
ref struct RR : public R{};
ref struct H {
   RR^ r ;
   short s;
   int i;
};

int main() {
   H^ h = gcnew H();
   interior_ptr<int>lr = &(h->i);
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK
}
```

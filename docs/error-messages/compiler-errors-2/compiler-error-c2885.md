---
description: 'Dowiedz się więcej o: błąd kompilatora C2885'
title: Błąd kompilatora C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: 040f7a151c34fe7b5e30b6aad1e5bc956b3e5cf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337488"
---
# <a name="compiler-error-c2885"></a>Błąd kompilatora C2885

"Class:: identifier": nie jest prawidłową deklaracją Using w zakresie nieklasowym

Użyto nieprawidłowej deklaracji [using](../../cpp/using-declaration.md) .

Ten błąd może zostać wygenerowany w wyniku pracy zgodnej z kompilatorem, który został wykonany dla programu Visual Studio 2005: nie jest już prawidłowa **`using`** Deklaracja do typu zagnieżdżonego; należy jawnie zakwalifikować każde odwołanie do typu zagnieżdżonego, umieścić typ w przestrzeni nazw lub utworzyć element typedef.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2885.

```cpp
// C2885.cpp
namespace MyNamespace {
   class X1 {};
}

struct MyStruct {
   struct X1 {
      int i;
   };
};

int main () {
   using MyStruct::X1;   // C2885

   // OK
   using MyNamespace::X1;
   X1 myX1;

   MyStruct::X1 X12;

   typedef MyStruct::X1 abc;
   abc X13;
   X13.i = 9;
}
```

Jeśli używasz **`using`** słowa kluczowego z składową klasy, C++ wymaga zdefiniowania tego elementu członkowskiego wewnątrz innej klasy (klasy pochodnej).

Poniższy przykład generuje C2885.

```cpp
// C2885_b.cpp
// compile with: /c
class A {
public:
   int i;
};

void z() {
   using A::i;   // C2885 not in a class
}

class B : public A {
public:
   using A::i;
};
```

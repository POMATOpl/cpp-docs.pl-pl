---
description: 'Dowiedz się więcej o: błąd kompilatora C2027'
title: Błąd kompilatora C2027
ms.date: 11/04/2016
f1_keywords:
- C2027
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
ms.openlocfilehash: 131362f2caa8da80865a9601d87cfe3a5e7ab3b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175550"
---
# <a name="compiler-error-c2027"></a>Błąd kompilatora C2027

Użycie niezdefiniowanego typu "Type"

Nie można użyć typu, dopóki nie zostanie on zdefiniowany. Aby rozwiązać ten problem, upewnij się, że typ jest w pełni zdefiniowany przed odwołaniem do niego.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2027.

```cpp
// C2027.cpp
class C;
class D {
public:
   void func() {
   }
};

int main() {
   C *pC;
   pC->func();   // C2027

   D *pD;
   pD->func();
}
```

Można zadeklarować wskaźnik do zadeklarowanego, ale niezdefiniowanego typu. Ale C++ nie zezwala na odwołanie do niezdefiniowanego typu.

Poniższy przykład generuje C2027.

```cpp
// C2027_b.cpp
class A;
A& CreateA();

class B;
B* CreateB();

int main() {
   CreateA();   // C2027
   CreateB();   // OK
}
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C2079'
title: Błąd kompilatora C2079
ms.date: 11/04/2016
f1_keywords:
- C2079
helpviewer_keywords:
- C2079
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
ms.openlocfilehash: 73ca5d334ac3bf3157b61a1b2a9489282ae1fe00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151219"
---
# <a name="compiler-error-c2079"></a>Błąd kompilatora C2079

element "identifier" używa niezdefiniowanej klasy/struktury/Unii "name"

Określony identyfikator jest niezdefiniowaną klasą, strukturą lub Unią.

Ten błąd może być spowodowany inicjalizacją anonimowej Unii.

Poniższy przykład generuje C2079:

```cpp
// C2079.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   std::ifstream g;   // C2079
}
```

Możliwe rozwiązanie:

```cpp
// C2079b.cpp
// compile with: /EHsc
#include <fstream>
int main( ) {
   std::ifstream g;
}
```

C2079 może również wystąpić, jeśli próbujesz zadeklarować obiekt na stosie typu, którego deklaracja do przodu jest tylko w zakresie.

```cpp
// C2079c.cpp
class A;

class B {
   A a;   // C2079
};

class A {};
```

Możliwe rozwiązanie:

```cpp
// C2079d.cpp
// compile with: /c
class A;
class C {};

class B {
   A * a;
   C c;
};

class A {};
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C2514'
title: Błąd kompilatora C2514
ms.date: 11/04/2016
f1_keywords:
- C2514
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
ms.openlocfilehash: 3999a5a65df08142b68e7257b257d39d1b5245e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212821"
---
# <a name="compiler-error-c2514"></a>Błąd kompilatora C2514

"Class": Klasa nie ma konstruktorów

Klasa, struktura lub Unia nie ma konstruktora z listą parametrów, który odpowiada parametrom używanym do tworzenia wystąpienia.

Aby można było utworzyć wystąpienie, Klasa musi być w pełni zadeklarowana.

Poniższy przykład generuje C2514:

```cpp
// C2514.cpp
// compile with: /c
class f;

class g {
public:
    g (int x);
};

class fmaker {
   f *func1() {
      return new f(2);   // C2514
   }

   g *func2() {
      return new g(2);   // OK
   }
};
```

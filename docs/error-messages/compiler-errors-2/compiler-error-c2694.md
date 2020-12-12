---
description: 'Dowiedz się więcej o: błąd kompilatora C2694'
title: Błąd kompilatora C2694
ms.date: 11/04/2016
f1_keywords:
- C2694
helpviewer_keywords:
- C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
ms.openlocfilehash: 4da5362a9c20a2bae10d2a201650f4312d455164
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326660"
---
# <a name="compiler-error-c2694"></a>Błąd kompilatora C2694

"override": przesłanianie wirtualnej funkcji ma mniej restrykcyjną specyfikację wyjątku niż Klasa bazowa wirtualnej funkcji składowej "Base"

Funkcja wirtualna została przesłonięta, ale w obszarze [/za](../../build/reference/za-ze-disable-language-extensions.md)funkcja zastępująca miała mniej restrykcyjną [specyfikację wyjątku](../../cpp/exception-specifications-throw-cpp.md).

Poniższy przykład generuje C2694:

```cpp
// C2694.cpp
// compile with: /Za /c
class MyBase {
public:
   virtual void f(void) throw(int) {
   }
};

class Derived : public MyBase {
public:
   void f(void) throw(...) {}   // C2694
   void f2(void) throw(int) {}   // OK
};
```

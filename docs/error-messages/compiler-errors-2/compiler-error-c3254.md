---
description: 'Dowiedz się więcej o: błąd kompilatora C3254'
title: Błąd kompilatora C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 7d0084f52060803cd99b973c9f6105fc8915c2aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194218"
---
# <a name="compiler-error-c3254"></a>Błąd kompilatora C3254

"jawne przesłonięcie": Klasa zawiera jawne przesłonięcie "override", ale nie pochodzi z interfejsu, który zawiera deklarację funkcji

W przypadku [jawnego przesłaniania](../../cpp/explicit-overrides-cpp.md) metody Klasa, która zawiera przesłonięcie, musi pochodzić, bezpośrednio lub pośrednio, z typu, który zawiera zastępujący funkcję.

Poniższy przykład generuje C3254:

```cpp
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```

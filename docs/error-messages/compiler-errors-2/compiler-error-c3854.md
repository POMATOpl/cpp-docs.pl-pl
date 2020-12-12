---
description: 'Dowiedz się więcej o: błąd kompilatora C3854'
title: Błąd kompilatora C3854
ms.date: 11/04/2016
f1_keywords:
- C3854
helpviewer_keywords:
- C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
ms.openlocfilehash: f6c2399ff4c38cfbb306bd90e5bb5e96b34220eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328160"
---
# <a name="compiler-error-c3854"></a>Błąd kompilatora C3854

wyrażenie po lewej stronie "=" daje w wyniku funkcję. Nie można przypisać do funkcji (funkcja nie jest l-wartością)

Nie można ponownie zainicjować odwołania. Odwołanie do odwołania do funkcji daje funkcję, która jest rvalue, do której nie można przypisać. W związku z tym nie można przypisać przez odwołanie do funkcji.

Poniższy przykład generuje C3854:

```cpp
// C3854.cpp
int afunc(int i)
{
   return i;
}

typedef int (& rFunc_t)(int);
typedef int (* pFunc_t)(int);

int main()
{
   rFunc_t rf = afunc;   // OK binding a reference to function
   pFunc_t pf = &afunc;   // OK initializing a pointer to function

   *pf = &afunc;   // C3854
   // try the following line instead
   // pf = &afunc;
   *rf = &afunc;   // C3854
}
```

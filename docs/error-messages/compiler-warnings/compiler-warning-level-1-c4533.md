---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4533'
title: Ostrzeżenie kompilatora (poziom 1) C4533
ms.date: 11/04/2016
f1_keywords:
- C4533
helpviewer_keywords:
- C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
ms.openlocfilehash: 76358a19beb5fc6d177c21d39fe9a375eb60af02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212288"
---
# <a name="compiler-warning-level-1-c4533"></a>Ostrzeżenie kompilatora (poziom 1) C4533

Inicjalizacja elementu "variable" jest pomijana przez instrukcję "Instruction"

Instrukcja w programie zmieniła przepływ sterowania, na przykład, nie wykonano instrukcji, która zainicjowała zmienną. Poniższy przykład generuje C4533:

```cpp
// C4533.cpp
// compile with: /W1
#include <stdio.h>

struct A
{
   int m_data;
};

int main()
{
   if (1)
   {
      goto Label;
   }

   A a = { 100 };

   Label:   // C4533
      printf("\n%d", a.m_data);   // prints an uninitialized value
}
```

---
title: Błąd kompilatora C2764
ms.date: 11/04/2016
f1_keywords:
- C2764
helpviewer_keywords:
- C2764
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
ms.openlocfilehash: ba16431fc71a0e594b77dcc6dab62ed6c49c9137
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257494"
---
# <a name="compiler-error-c2764"></a>Błąd kompilatora C2764

"param": parametr szablonu nieużywany lub dający się wywieźć w składowej specjalizacji "specjalizacja"

Parametr szablonu nie jest używany w częściowej specjalizacji. Częściowa specjalizacja temu bezużyteczny, ponieważ nie można wywnioskować parametru szablonu.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C2764:

```
// C2764.cpp
#include <stdio.h>
template <class T1, class T2>
struct S  {
   int m_i;
};

template <class T1, class T2>
struct S<int, T2*> {   // C2764
// try the following line instead
// struct S<T1(*)(T2), T2*> {
   char m_c;
};

int main() {
   S<int, char> s1;
   S<void (*)(short), short *> s2;
   s2.m_c = 10;
   s1.m_i = s2.m_c;
   printf_s("%d\n", s1.m_i);
}
```
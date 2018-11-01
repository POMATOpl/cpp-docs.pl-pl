---
title: Błąd kompilatora C2770
ms.date: 11/04/2016
f1_keywords:
- C2770
helpviewer_keywords:
- C2770
ms.assetid: 100001b5-80b0-4971-8ff6-9023f443c926
ms.openlocfilehash: 9397b52838f61449f0475a31d5bb4077dad7f587
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601578"
---
# <a name="compiler-error-c2770"></a>Błąd kompilatora C2770

Nieprawidłowe jawne template_or_generic następującej liczby argumentów: "szablon"

W wyniku kandydatów szablonów funkcji za pomocą jawnego szablonu lub argumenty ogólne typy funkcji niedozwolonych.

Poniższy przykład spowoduje wygenerowanie C2770:

```
// C2770.cpp
#include <stdio.h>
template <class T>
int f(typename T::B*);   // expects type with member B

struct Err {};

int main() {
   f<int>(0);   // C2770 int has no B
   // try the following line instead
   f<OK>(0);
}
```
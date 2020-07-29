---
title: Błąd kompilatora C2786
ms.date: 11/04/2016
f1_keywords:
- C2786
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
ms.openlocfilehash: 60e921c17cd2b3f9462df77094162bb3f1eff379
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206682"
---
# <a name="compiler-error-c2786"></a>Błąd kompilatora C2786

"Type": nieprawidłowy operand dla __uuidof

Operator [__uuidof](../../cpp/uuidof-operator.md) przyjmuje zdefiniowany przez użytkownika typ z DOŁĄCZONYm identyfikatorem GUID lub obiektem takiego typu zdefiniowanego przez użytkownika.  Możliwe przyczyny:

1. Argument nie jest typem zdefiniowanym przez użytkownika.

1. **`__uuidof`** nie można wyodrębnić identyfikatora GUID z argumentu.

Poniższy przykład generuje C2786:

```cpp
// C2786.cpp
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};

int main() {
   __uuidof(int);   // C2786
   __uuidof(int *);   // C2786
   __uuidof(A **);   // C2786

   // no error
   __uuidof(A);
   __uuidof(A *);
   __uuidof(A &);
   __uuidof(A[]);

   int i;
   int *pi;
   A **ppa;

   __uuidof(i);      // C2786
   __uuidof(pi);     // C2786
   __uuidof(ppa);    // C2786
}
```

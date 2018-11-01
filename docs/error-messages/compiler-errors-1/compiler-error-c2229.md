---
title: Błąd kompilatora C2229
ms.date: 11/04/2016
f1_keywords:
- C2229
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
ms.openlocfilehash: 998067e9af178c1898c3443c4e84da965c22fa81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576907"
---
# <a name="compiler-error-c2229"></a>Błąd kompilatora C2229

Typ 'Identyfikator' ma niedozwolony zerowy rozmiar tablicy

Element członkowski pola struktury lub bitowego zawiera zerowy rozmiar tablicy, który nie jest ostatni element członkowski.

Ponieważ może mieć zero wielkości tablicy ostatni element członkowski struktury, należy określić jego rozmiar podczas alokowania struktury.

Jeśli tablicy o rozmiarze zero nie jest ostatniego członka struktury, kompilator nie może obliczyć przesunięcie dla pozostałych pól.

Poniższy przykład spowoduje wygenerowanie C2229:

```
// C2229.cpp
struct S {
   int a[0];  // C2229  zero-sized array
   int b[1];
};

struct S2 {
   int a;
   int b[0];
};

int main() {
   // allocate 7 elements for b field
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];
   s2->b[6] = 100;
}
```
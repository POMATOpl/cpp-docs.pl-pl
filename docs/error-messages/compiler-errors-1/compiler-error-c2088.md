---
title: Błąd kompilatora C2088
ms.date: 11/04/2016
f1_keywords:
- C2088
helpviewer_keywords:
- C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
ms.openlocfilehash: 6d53f2896fc3b964a4d2652b3bfd0dcebb4a7226
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175176"
---
# <a name="compiler-error-c2088"></a>Błąd kompilatora C2088

'operator': niedozwolony dla "klucz klasy"

Operator nie został zdefiniowany dla struktury lub Unii. Ten błąd jest prawidłowy tylko dla kodu C.

Poniższy przykład spowoduje wygenerowanie C2088 trzy razy:

```
// C2088.c
struct S {
   int m_i;
} s;

int main() {
   int i = s * 1;   // C2088
   struct S s2 = +s;   // C2088
   s++;   // C2088
}
```
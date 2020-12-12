---
description: 'Dowiedz się więcej o: błąd kompilatora C2088'
title: Błąd kompilatora C2088
ms.date: 11/04/2016
f1_keywords:
- C2088
helpviewer_keywords:
- C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
ms.openlocfilehash: 246c130c0918310b59924f3940950d443c0b9217
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251924"
---
# <a name="compiler-error-c2088"></a>Błąd kompilatora C2088

"operator": niedozwolone dla "klasy-Key"

Nie zdefiniowano operatora dla struktury lub związku. Ten błąd jest prawidłowy tylko dla kodu C.

Poniższy przykład generuje C2088 trzykrotnie:

```c
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

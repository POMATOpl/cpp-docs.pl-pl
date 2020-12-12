---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4717'
title: Ostrzeżenie kompilatora (poziom 1) C4717
ms.date: 11/04/2016
f1_keywords:
- C4717
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
ms.openlocfilehash: 7a23469539dd809ea4905701bd1f8064f26a8036
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328127"
---
# <a name="compiler-warning-level-1-c4717"></a>Ostrzeżenie kompilatora (poziom 1) C4717

"Function": rekursywnie we wszystkich ścieżkach kontroli, funkcja spowoduje przepełnienie stosu środowiska uruchomieniowego

Każda ścieżka przez funkcję zawiera wywołanie funkcji. Ponieważ nie istnieje sposób, aby wyjść z funkcji bez uprzedniego wywołania się cyklicznie, funkcja nigdy nie zostanie zakończona.

Poniższy przykład generuje C4717:

```cpp
// C4717.cpp
// compile with: /W1 /c
// C4717 expected
int func(int x) {
   if (x > 1)
      return func(x - 1); // recursive call
   else {
      int y = func(0) + 1; // recursive call
      return y;
   }
}

int main(){
   func(1);
}
```

---
title: Błąd kompilatora C2750
ms.date: 11/04/2016
f1_keywords:
- C2750
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
ms.openlocfilehash: 943220fae035da8d6fc861d2abae435051381e1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453745"
---
# <a name="compiler-error-c2750"></a>Błąd kompilatora C2750

"type": nie można użyć "new" dla typu odwołania; Zamiast tego użyj "gcnew"

Aby utworzyć wystąpienia typu CLR, co powoduje, że wystąpienie, które mają być umieszczane w stercie zebranych elementów bezużytecznych, należy użyć [gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md).

Poniższy przykład spowoduje wygenerowanie C2750:

```
// C2750.cpp
// compile with: /clr
ref struct Y1 {};

int main() {
   Y1 ^ x = new Y1;   // C2750

   // try the following line instead
   Y1 ^ x2 = gcnew Y1;
}
```
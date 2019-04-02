---
title: Błąd kompilatora C2750
ms.date: 11/04/2016
f1_keywords:
- C2750
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
ms.openlocfilehash: 34d19e8e9f51c90c48ec0d429f98bb82e3d829d4
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778913"
---
# <a name="compiler-error-c2750"></a>Błąd kompilatora C2750

"type": nie można użyć "new" dla typu odwołania; Zamiast tego użyj "gcnew"

Aby utworzyć wystąpienia typu CLR, co powoduje, że wystąpienie, które mają być umieszczane w stercie zebranych elementów bezużytecznych, należy użyć [gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md).

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
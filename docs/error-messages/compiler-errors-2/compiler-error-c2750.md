---
description: 'Dowiedz się więcej o: błąd kompilatora C2750'
title: Błąd kompilatora C2750
ms.date: 11/04/2016
f1_keywords:
- C2750
helpviewer_keywords:
- C2750
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
ms.openlocfilehash: 727bf085e1377de8725f6537a33917283d51d839
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174497"
---
# <a name="compiler-error-c2750"></a>Błąd kompilatora C2750

"Type": nie można użyć "New" dla typu referencyjnego; Zamiast tego użyj "gcnew"

Aby utworzyć wystąpienie typu CLR, które powoduje umieszczenie wystąpienia na stosie zebranych elementów bezużytecznych, należy użyć [gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md).

Poniższy przykład generuje C2750:

```cpp
// C2750.cpp
// compile with: /clr
ref struct Y1 {};

int main() {
   Y1 ^ x = new Y1;   // C2750

   // try the following line instead
   Y1 ^ x2 = gcnew Y1;
}
```

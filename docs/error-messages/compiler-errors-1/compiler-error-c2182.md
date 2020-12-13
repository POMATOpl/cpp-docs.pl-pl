---
description: 'Dowiedz się więcej o: błąd kompilatora C2182'
title: Błąd kompilatora C2182
ms.date: 11/04/2016
f1_keywords:
- C2182
helpviewer_keywords:
- C2182
ms.assetid: dfd8d47d-9606-496e-bd96-4bf41ba1f857
ms.openlocfilehash: c8ad265810d287a32b4bffe3aa133c1437420ec7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335171"
---
# <a name="compiler-error-c2182"></a>Błąd kompilatora C2182

"Identyfikator": niedozwolone użycie typu "void"

Zmienna jest zadeklarowana jako typ **`void`** .

Poniższy przykład generuje C2182:

```cpp
// C2182.cpp
// compile with: /c
int main() {
   int i = 10;
   void &ir = i;   // C2182 cannot have a reference to type void
   int &ir = i;   // OK
}
```

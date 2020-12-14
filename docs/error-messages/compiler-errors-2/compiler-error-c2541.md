---
description: 'Dowiedz się więcej o: błąd kompilatora C2541'
title: Błąd kompilatora C2541
ms.date: 11/04/2016
f1_keywords:
- C2541
helpviewer_keywords:
- C2541
ms.assetid: ed95180f-00df-4e62-a8e9-1b6dab8281bf
ms.openlocfilehash: 79d4cab33a7c92455b5a4eacdf75f26f80b16a33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302013"
---
# <a name="compiler-error-c2541"></a>Błąd kompilatora C2541

"Delete": delete: nie można usunąć obiektów, które nie są wskaźnikami

Operator [delete](../../cpp/delete-operator-cpp.md) został użyty w obiekcie, który nie jest wskaźnikiem.

Poniższy przykład generuje C2541:

```cpp
// C2541.cpp
int main() {
   int i;
   delete i;   // C2541 i not a pointer

   // OK
   int *ip = new int;
   delete ip;
}
```

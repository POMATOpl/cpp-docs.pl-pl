---
title: Błąd kompilatora C2256
ms.date: 11/04/2016
f1_keywords:
- C2256
helpviewer_keywords:
- C2256
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
ms.openlocfilehash: 56c4df338feb2c0f406835c1ef2ffeeb7caf8bca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387063"
---
# <a name="compiler-error-c2256"></a>Błąd kompilatora C2256

niedozwolone użycie zaprzyjaźnionego specyfikatora na "function"

Destruktor lub konstruktora, nie można określić jako [friend](../../cpp/friend-cpp.md).

Poniższy przykład spowoduje wygenerowanie C2256:

```
// C2256.cpp
// compile with: /c
class C {
public:
   friend ~C();   // C2256
   ~C();   // OK
};
```
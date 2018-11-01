---
title: Błąd kompilatora C2120
ms.date: 11/04/2016
f1_keywords:
- C2120
helpviewer_keywords:
- C2120
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
ms.openlocfilehash: 699a80b2cdb1de175c78efb918ba9389ec3695f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486297"
---
# <a name="compiler-error-c2120"></a>Błąd kompilatora C2120

"void" niedozwolone ze wszystkimi typami

`void` Typ jest używany w deklaracji z innego typu.

Poniższy przykład spowoduje wygenerowanie C2120:

```
// C2120.cpp
int main() {
   void int i;   // C2120
   int j;   // OK
}
```
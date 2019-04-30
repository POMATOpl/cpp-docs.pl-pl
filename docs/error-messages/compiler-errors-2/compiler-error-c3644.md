---
title: Błąd kompilatora C3644
ms.date: 11/04/2016
f1_keywords:
- C3644
helpviewer_keywords:
- C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
ms.openlocfilehash: 6d147d6a5955208bbca1ccf9a2f2bcfe3f485b4f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385631"
---
# <a name="compiler-error-c3644"></a>Błąd kompilatora C3644

'Funkcja': nie można skompilować funkcji do generowania kodu zarządzanego

Obecność niektórych słów kluczowych w funkcji spowoduje, że funkcja jest kompilowana do natywnego.

Poniższy przykład spowoduje wygenerowanie C3644:

```
// C3644.cpp
// compile with: /clr
// processor: x86

void __clrcall Func2(int i) {
   __asm {}   // C3644
}
```
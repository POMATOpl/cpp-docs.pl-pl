---
title: Błąd kompilatora C2488
ms.date: 11/04/2016
f1_keywords:
- C2488
helpviewer_keywords:
- C2488
ms.assetid: cd435909-43e4-43c6-a57c-5d02468ef75f
ms.openlocfilehash: 9b49d49c8a261bb3d636446f820a45699361830f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452120"
---
# <a name="compiler-error-c2488"></a>Błąd kompilatora C2488

'Identyfikator': "naked" można stosować tylko do definicji funkcji składowej

["Naked"](../../cpp/naked-cpp.md) atrybut została zastosowana do deklaracji funkcji.

Poniższy przykład spowoduje wygenerowanie C2488:

```
// C2488.cpp
// compile with: /c
// processor: x86
__declspec( naked ) void func();   // C2488  declaration, not definition
__declspec( naked ) void i;   // C2488  i is not a function

__declspec( naked ) void func() {}   // OK
```
---
description: 'Dowiedz się więcej o: błąd kompilatora C2490'
title: Błąd kompilatora C2490
ms.date: 11/04/2016
f1_keywords:
- C2490
helpviewer_keywords:
- C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
ms.openlocfilehash: 9638b65eb453fcc957ac2e9a947138ba1f7ac745
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339348"
---
# <a name="compiler-error-c2490"></a>Błąd kompilatora C2490

słowo kluczowe "unkeyword" jest niedozwolone w funkcji z atrybutem "owies"

Funkcja zdefiniowana jako " [owies](../../cpp/naked-cpp.md) " nie może korzystać z obsługi wyjątków strukturalnych.

Poniższy przykład generuje C2490:

```cpp
// C2490.cpp
// processor: x86
__declspec( naked ) int func() {
   __try{}   // C2490, structured exception handling
}
```

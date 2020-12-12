---
description: 'Dowiedz się więcej o: błąd kompilatora C2489'
title: Błąd kompilatora C2489
ms.date: 11/04/2016
f1_keywords:
- C2489
helpviewer_keywords:
- C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
ms.openlocfilehash: 21e7a935ee3cf9c0dc1aa886b94ada931fbb64ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305406"
---
# <a name="compiler-error-c2489"></a>Błąd kompilatora C2489

"Identyfikator": zainicjowana zmienna autolub Register nie jest dozwolona w zakresie funkcji w funkcji "owies"

Aby uzyskać więcej informacji, [Zobacz.](../../cpp/naked-cpp.md)

Poniższy przykład generuje C2489:

```cpp
// C2489.cpp
// processor: x86
__declspec( naked ) int func() {
   int i = 1;   // C2489
   register int j = 1;   // C2489
}
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C2486'
title: Błąd kompilatora C2486
ms.date: 11/04/2016
f1_keywords:
- C2486
helpviewer_keywords:
- C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
ms.openlocfilehash: c45e0bdb0f515743694fe372bea3afdb24e00177
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339361"
---
# <a name="compiler-error-c2486"></a>Błąd kompilatora C2486

Element "__LOCAL_SIZE" jest dozwolony tylko w funkcji z atrybutem "owies"

W wbudowanych funkcjach zestawu nazwa `__LOCAL_SIZE` jest zarezerwowana dla funkcji zadeklarowanych za pomocą atrybutu [owies](../../cpp/naked-cpp.md) .

Poniższy przykład generuje C2486:

```cpp
// C2486.cpp
// processor: x86
void __declspec(naked) f1() {
   __asm {
      mov   eax,   __LOCAL_SIZE
   }
}
void f2() {
   __asm {
      mov   eax,   __LOCAL_SIZE   // C2486
   }
}
```

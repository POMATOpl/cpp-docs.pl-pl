---
title: Błąd kompilatora C3886
ms.date: 11/04/2016
f1_keywords:
- C3886
helpviewer_keywords:
- C3886
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
ms.openlocfilehash: e9e9d4b478d5b53e50203d1f009295e1da444f2d
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770723"
---
# <a name="compiler-error-c3886"></a>Błąd kompilatora C3886

"var": literał składowej danych musi zostać zainicjowany

A [literału](../../extensions/literal-cpp-component-extensions.md) zmiennej musi być inicjowana, gdy jest declaraed.

Poniższy przykład spowoduje wygenerowanie C3886:

```
// C3886.cpp
// compile with: /clr /c
ref struct Y1 {
   literal int staticConst;   // C3886
   literal int staticConst2 = 0;   // OK
};
```
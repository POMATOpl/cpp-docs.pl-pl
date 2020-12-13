---
description: 'Dowiedz się więcej o: błąd kompilatora C3644'
title: Błąd kompilatora C3644
ms.date: 11/04/2016
f1_keywords:
- C3644
helpviewer_keywords:
- C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
ms.openlocfilehash: e08471583dea096481115f3d710a1854ef00baf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340284"
---
# <a name="compiler-error-c3644"></a>Błąd kompilatora C3644

"Function": nie można skompilować funkcji w celu wygenerowania kodu zarządzanego

Obecność niektórych słów kluczowych w funkcji spowoduje skompilowanie funkcji w trybie macierzystym.

Poniższy przykład generuje C3644:

```cpp
// C3644.cpp
// compile with: /clr
// processor: x86

void __clrcall Func2(int i) {
   __asm {}   // C3644
}
```

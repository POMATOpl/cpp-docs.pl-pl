---
description: 'Dowiedz się więcej o: błąd kompilatora C2734'
title: Błąd kompilatora C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: c867ef8456be35d0e566056aedc4de43d16c8f14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123178"
---
# <a name="compiler-error-c2734"></a>Błąd kompilatora C2734

"Identyfikator": obiekt const musi zostać zainicjowany, jeśli nie jest zewnętrzny

Identyfikator jest zadeklarowany, **`const`** ale nie został zainicjowany lub **`extern`** .

Poniższy przykład generuje C2734:

```cpp
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```

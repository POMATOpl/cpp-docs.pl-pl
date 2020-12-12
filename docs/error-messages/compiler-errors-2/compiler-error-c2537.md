---
description: 'Dowiedz się więcej o: błąd kompilatora C2537'
title: Błąd kompilatora C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 46603ded270b4702d4b7d4de97352547c5f503f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302039"
---
# <a name="compiler-error-c2537"></a>Błąd kompilatora C2537

"specyfikator": niedozwolona Specyfikacja powiązania

Możliwe przyczyny:

1. Specyfikator powiązania nie jest obsługiwany. Obsługiwany jest tylko specyfikator łączenia "C".

1. Połączenie "C" jest określone dla więcej niż jednej funkcji w zestawie przeciążonych funkcji. Jest to niedozwolone.

Poniższy przykład generuje C2537:

```cpp
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```

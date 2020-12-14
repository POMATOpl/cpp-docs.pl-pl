---
description: 'Dowiedz się więcej o: błąd kompilatora C2293'
title: Błąd kompilatora C2293
ms.date: 11/04/2016
f1_keywords:
- C2293
helpviewer_keywords:
- C2293
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
ms.openlocfilehash: 667ca42295092711f5812d2d7d0b10afb82e9959
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235258"
---
# <a name="compiler-error-c2293"></a>Błąd kompilatora C2293

"Identyfikator": niedozwolone jest posiadanie zmiennej składowej jako specyfikatora __based

Specyfikatory dla **`__based`** modyfikatora muszą być wskaźnikami nienależącymi do elementów członkowskich.

Poniższy przykład generuje C2293:

```cpp
// C2293.cpp
// compile with: /c
class A {
   static int *i;
   void __based(i) *bp;   // C2293
   void *bp2;   // OK
};
```

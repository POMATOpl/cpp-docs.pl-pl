---
description: 'Dowiedz się więcej o: błąd kompilatora C2652'
title: Błąd kompilatora C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: 6d0f85a089c527ce299e007ce04d96ac68daaf56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286179"
---
# <a name="compiler-error-c2652"></a>Błąd kompilatora C2652

"Identyfikator": niedozwolony Konstruktor kopiujący: pierwszy parametr nie może być identyfikatorem

Pierwszy parametr w konstruktorze kopiującym ma ten sam typ, który jest klasą, strukturą lub Unią, dla której jest zdefiniowany. Pierwszy parametr może być odwołaniem do typu, ale nie do samego typu.

Poniższy przykład generuje C2651:

```cpp
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```

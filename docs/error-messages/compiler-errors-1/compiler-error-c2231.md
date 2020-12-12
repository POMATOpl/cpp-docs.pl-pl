---
description: 'Dowiedz się więcej o: błąd kompilatora C2231'
title: Błąd kompilatora C2231
ms.date: 11/04/2016
f1_keywords:
- C2231
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
ms.openlocfilehash: 159f29529fdcf7253fa1af51951c402df1b21823
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194959"
---
# <a name="compiler-error-c2231"></a>Błąd kompilatora C2231

".": Lewy argument operacji wskazuje na "Class-Key", użyj "->"

Operand po lewej stronie operacji wyboru elementu członkowskiego (.) jest wskaźnikiem, a nie klasą, strukturą lub Unią.

Poniższy przykład generuje C2231:

```c
// C2231.c
struct S {
   int member;
} s, *ps = &s;
int main() {
   ps.member = 0;   // C2231

   // OK
   ps->member = 0;   // crash
   s.member = 0;
}
```

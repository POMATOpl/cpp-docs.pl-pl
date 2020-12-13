---
description: 'Dowiedz się więcej o: błąd kompilatora C2562'
title: Błąd kompilatora C2562
ms.date: 11/04/2016
f1_keywords:
- C2562
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
ms.openlocfilehash: 9e9da8a7463b450073f4b537ec36512242995760
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338704"
---
# <a name="compiler-error-c2562"></a>Błąd kompilatora C2562

"Identyfikator": funkcja "void" zwraca wartość

Funkcja jest zadeklarowana jako, **`void`** ale zwraca wartość.

Ten błąd może być spowodowany przez nieprawidłowy prototyp funkcji.

Ten błąd może zostać naprawiony w przypadku określenia typu zwracanego w deklaracji funkcji.

Poniższy przykład generuje C2562:

```cpp
// C2562.cpp
// compile with: /c
void testfunc() {
   int i;
   return i;   // C2562 delete the return to resolve
}
```

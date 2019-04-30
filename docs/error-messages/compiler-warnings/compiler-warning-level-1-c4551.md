---
title: Kompilator ostrzeżenie (poziom 1) C4551
ms.date: 11/04/2016
f1_keywords:
- C4551
helpviewer_keywords:
- C4551
ms.assetid: 458b59bd-e2d7-425f-9ba6-268ff200424f
ms.openlocfilehash: 8a30ad5622d8e889a7f3ec64b73ead7c63f65b48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397357"
---
# <a name="compiler-warning-level-1-c4551"></a>Kompilator ostrzeżenie (poziom 1) C4551

wywołaniu funkcji brakuje listy argumentów

Wywołanie funkcji musi zawierać otwierających i zamykających nawiasów po nazwie funkcji, nawet jeśli funkcja nie przyjmuje żadnych parametrów.

Poniższy przykład spowoduje wygenerowanie C4551:

```
// C4551.cpp
// compile with: /W1
void function1() {
}

int main() {
   function1;   // C4551
   function1();   // OK
}
```
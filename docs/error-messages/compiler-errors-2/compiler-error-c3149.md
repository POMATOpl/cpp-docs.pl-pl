---
description: 'Dowiedz się więcej o: błąd kompilatora C3149'
title: Błąd kompilatora C3149
ms.date: 11/04/2016
f1_keywords:
- C3149
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
ms.openlocfilehash: 596a8d2728e7598a737da4aa5a1650df669db969
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322093"
---
# <a name="compiler-error-c3149"></a>Błąd kompilatora C3149

"Type": nie można użyć tego typu w tym miejscu bez znaku "char" najwyższego poziomu

Deklaracja nie została określona prawidłowo.

Na przykład można zdefiniować typ CLR w zakresie globalnym i próbować utworzyć zmienną typu w ramach definicji. Ponieważ zmienne globalne typów CLR są niedozwolone, kompilator generuje C3149.

Aby rozwiązać ten problem, należy zadeklarować zmienne typów CLR wewnątrz funkcji lub definicji typu.

Poniższy przykład generuje C3149:

```cpp
// C3149.cpp
// compile with: /clr
using namespace System;
int main() {
   // declare an array of value types
   array< Int32 ^> IntArray;   // C3149
   array< Int32>^ IntArray2;   // OK
}
```

Poniższy przykład generuje C3149:

```cpp
// C3149b.cpp
// compile with: /clr /c
delegate int MyDelegate(const int, int);
void Test1(MyDelegate m) {}   // C3149
void Test2(MyDelegate ^ m) {}   // OK
```

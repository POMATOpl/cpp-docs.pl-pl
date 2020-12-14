---
description: 'Dowiedz się więcej o: błąd kompilatora C2362'
title: Błąd kompilatora C2362
ms.date: 06/03/2019
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: 9043b6e82fd45923e7108d6a6f8934416eaaa328
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210923"
---
# <a name="compiler-error-c2362"></a>Błąd kompilatora C2362

> Inicjalizacja elementu "*Identifier*" jest pomijana przez element "goto *Label*"

Po skompilowaniu przy użyciu [/za](../../build/reference/za-ze-disable-language-extensions.md), skok do etykiety uniemożliwia zainicjowanie identyfikatora.

Można tylko przeskoczyć do wcześniejszej deklaracji z inicjatorem, jeśli deklaracja jest ujęta w bloku, który nie został wprowadzony, lub jeśli zmienna została już zainicjowana.

Poniższy przykład generuje C2362:

```cpp
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

Możliwe rozwiązanie:

```cpp
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```

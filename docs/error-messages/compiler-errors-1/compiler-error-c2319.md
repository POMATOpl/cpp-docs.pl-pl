---
title: Błąd kompilatora C2319
ms.date: 11/04/2016
f1_keywords:
- C2319
helpviewer_keywords:
- C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
ms.openlocfilehash: f0ec35cfb74fd08180969344180ff42d485d58c0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587606"
---
# <a name="compiler-error-c2319"></a>Błąd kompilatora C2319

"try/catch" musi następować instrukcja złożona. Brak "{"

A `try` lub `catch` bloku nie można odnaleźć następującego `try` lub `catch` instrukcji. Blok muszą być ujęte w nawiasy klamrowe.

Poniższy przykład spowoduje wygenerowanie C2319:

```
// C2319.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
   try {
      throw "ooops!";
   }
   catch( C ) ;    // C2319
   // try the following line instead
   // catch( C ) {}
}
```
---
title: Błąd kompilatora C2319
ms.date: 11/04/2016
f1_keywords:
- C2319
helpviewer_keywords:
- C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
ms.openlocfilehash: af9c0f0395e29c384ddc06f9a029f29c921e71c8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221240"
---
# <a name="compiler-error-c2319"></a>Błąd kompilatora C2319

po instrukcji "try/catch" musi występować złożona instrukcja. Brak znaku "{"

**`try`** **`catch`** Nie znaleziono bloku lub w **`try`** **`catch`** instrukcji or. Blok musi być ujęty w nawiasy klamrowe.

Poniższy przykład generuje C2319:

```cpp
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

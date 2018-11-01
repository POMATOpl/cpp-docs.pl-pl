---
title: Kompilator ostrzeżenie (poziom 1) C4401
ms.date: 11/04/2016
f1_keywords:
- C4401
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
ms.openlocfilehash: c7e6cf8a52288d895b74481678dc91fee387a6a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455422"
---
# <a name="compiler-warning-level-1-c4401"></a>Kompilator ostrzeżenie (poziom 1) C4401

"bitfield": składowa jest polem bitowym

Wbudowany kod asemblera próbuje uzyskać dostępu do członka pole bitowe. Wbudowany zestaw nie ma dostępu członków pola bitowego, więc ostatniego granicy pakowania przed składowej pola bitowego jest używany.

Aby uniknąć tego ostrzeżenia, należy zrzutować pola bitowego do odpowiedniego typu przed wprowadzeniem odwołania w kodzie zestawu wbudowanego. Poniższy przykład spowoduje wygenerowanie C4401:

```
// C4401.cpp
// compile with: /W1
// processor: x86
typedef struct bitfield {
   signed bit : 1;
} mybitfield;

int main() {
   mybitfield bf;
   bf.bit = 0;
   __asm {
      mov bf.bit,0;   // C4401
   }

   /* use the following __asm block to resolve the warning
   int i = (int)bf.bit;
   __asm {
      mov i,0;
   }
   */
}
```
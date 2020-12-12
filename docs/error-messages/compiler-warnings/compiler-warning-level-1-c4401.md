---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4401'
title: Ostrzeżenie kompilatora (poziom 1) C4401
ms.date: 11/04/2016
f1_keywords:
- C4401
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
ms.openlocfilehash: c6314b64ef9a675f8838cc7c3f4c89c2d6063231
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212743"
---
# <a name="compiler-warning-level-1-c4401"></a>Ostrzeżenie kompilatora (poziom 1) C4401

"pole bitowe": składowa jest polem bitowym

Wbudowany kod asemblera próbuje uzyskać dostęp do elementu członkowskiego pola bitowego. Wbudowany zestaw nie może uzyskać dostępu do elementów członkowskich w polu bitowym, więc należy użyć ostatniej granicy pakowania przed użyciem elementu członkowskiego pola bitowego.

Aby uniknąć tego ostrzeżenia, należy rzutować pole bitowe na odpowiedni typ przed wprowadzeniem odwołania w kodzie zestawu wbudowanego. Poniższy przykład generuje C4401:

```cpp
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

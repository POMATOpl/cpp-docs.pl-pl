---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4731'
title: Ostrzeżenie kompilatora (poziom 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: d2041936d7d3c4b7189f57d57ffb1c9f226ea933
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228654"
---
# <a name="compiler-warning-level-1-c4731"></a>Ostrzeżenie kompilatora (poziom 1) C4731

"wskaźnik": Rejestr wskaźnika ramki "Register" został zmodyfikowany przez wbudowany kod asemblera

Zmodyfikowano rejestr wskaźników klatki. Musisz zapisać i przywrócić rejestr w bloku zestawu wbudowanego lub zmiennej ramki (Local lub Parameter, w zależności od zmodyfikowanego rejestru) lub kod może nie funkcjonować prawidłowo.

Poniższy przykład generuje C4731:

```cpp
// C4731.cpp
// compile with: /W1 /LD
// processor: x86
// C4731 expected
void bad(int p) {
   __asm
   {
      mov ebp, 1
   }

   if (p == 1)
   {
      // ...
   }
}
```

EBP jest wskaźnikiem ramki (FPO jest niedozwolony) i jest modyfikowany. Gdy jest przywoływany w `p` późniejszym czasie, odwołanie odwołuje się do `EBP` . Ale został `EBP` nadpisany przez kod, więc program nie będzie działał prawidłowo i może nawet ulec awarii.

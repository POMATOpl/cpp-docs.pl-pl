---
description: 'Dowiedz się więcej o: błąd kompilatora C2422'
title: Błąd kompilatora C2422
ms.date: 11/04/2016
f1_keywords:
- C2422
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
ms.openlocfilehash: 4fb35b7613e523c750d6c3f15a8071117edba46a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120246"
---
# <a name="compiler-error-c2422"></a>Błąd kompilatora C2422

niedozwolone przesłonięcie segmentu w "operandzie"

Wbudowany kod asemblera niepoprawnie używa operatora przesłaniania segmentu (dwukropek) dla operandu.  Ta sytuacja może mieć następujące przyczyny:

- Rejestr poprzedzający operator nie jest rejestrem segmentów.

- Rejestr poprzedzający operator nie jest jedynym rejestrem segmentów w argumencie operacji.

- Operator przesłonięcia segmentu pojawia się w operatorze pośrednim (nawiasy).

- Wyrażenie następujące po przesłonięciu segmentu nie jest bezpośrednim operandem lub operandem pamięci.

Poniższy przykład generuje C2422:

```cpp
// C2422.cpp
// processor: x86
int main() {
   _asm {
      mov AX, [BX:ES]   // C2422
      mov AX, ES   // OK
   }
}
```

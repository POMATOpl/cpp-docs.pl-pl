---
title: Błąd kompilatora C2630
ms.date: 11/04/2016
f1_keywords:
- C2630
helpviewer_keywords:
- C2630
ms.assetid: 7a655a9c-bab4-495b-97a3-a3f34cf5369a
ms.openlocfilehash: db4108961c940afe3333dc726a97a8ce6ae639a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657161"
---
# <a name="compiler-error-c2630"></a>Błąd kompilatora C2630

"symbol" w czymś co powinno być rozdzielaną przecinkami listę

Symbol pojawia się w kontekście, który wymaga wartości przecinkami.

Poniższy przykład spowoduje wygenerowanie C2630:

```
// C2630.cpp
// compile with: /c
struct D {
   D(int);
};

struct E {
   E(int);
};

class C : public D, public E {
   C();
};

C::C() : D(0) ; E(0) { }   // C2630
C::C() : D(0), E(0) {}   // OK
```
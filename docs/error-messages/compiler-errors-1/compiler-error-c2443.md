---
title: Błąd kompilatora C2443
ms.date: 11/04/2016
f1_keywords:
- C2443
helpviewer_keywords:
- C2443
ms.assetid: 315330d5-24bc-4193-a531-0642095be58f
ms.openlocfilehash: 41ae2c430362f96f5863819e2bf49124bdfb0a4d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598475"
---
# <a name="compiler-error-c2443"></a>Błąd kompilatora C2443

konflikt rozmiaru operandu

Instrukcja wymaga argumentów operacji, aby mieć taki sam rozmiar.

Poniższy przykład spowoduje wygenerowanie C2443:

```
// C2443.cpp
// processor: x86
short var;
int main() {
   __asm xchg ax,bl   // C2443
   __asm mov al,red   // C2443
   __asm mov al,BYTE PTR var   // OK
}
```
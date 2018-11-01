---
title: Błąd kompilatora C3697
ms.date: 11/04/2016
f1_keywords:
- C3697
helpviewer_keywords:
- C3697
ms.assetid: 2d3f63c4-b7f8-421d-a7a5-2bf17fd054f9
ms.openlocfilehash: 55eadd55af8d4e6f088a0d0eb732d820242cae66
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540455"
---
# <a name="compiler-error-c3697"></a>Błąd kompilatora C3697

"kwalifikator": nie można użyć tego kwalifikatora na "^"

Śledzenie dojścia (^) została zastosowana do kwalifikator, dla którego zostało ono zaprojektowane.

Poniższy przykład spowoduje wygenerowanie C3697:

```
// C3697.cpp
// compile with: /clr
using namespace System;
int main() {
   String ^__restrict s;   // C3697
   String ^ s2;   // OK
}
```
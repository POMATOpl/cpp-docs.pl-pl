---
title: Kompilator ostrzeżenie (poziom 3) C4554
ms.date: 11/04/2016
f1_keywords:
- C4554
helpviewer_keywords:
- C4554
ms.assetid: 55bb68f0-2e80-4330-8921-51083c4f8d53
ms.openlocfilehash: 26251e4acac862e0505ea52e40a7aff2527fd472
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401829"
---
# <a name="compiler-warning-level-3-c4554"></a>Kompilator ostrzeżenie (poziom 3) C4554

'operator': Sprawdź pierwszeństwo operatorów w poszukiwaniu możliwego błędu; Użyj nawiasów, aby ujednoznacznić pierwszeństwo

Poniższy przykład spowoduje wygenerowanie C4554:

```
// C4554.cpp
// compile with: /W3 /WX
int main() {
   int a = 0, b = 0, c = 0;
   a = a << b + c;   // C4554
   // probably intended (a << b) + c,
   // but will get a << (b + c)
}
```
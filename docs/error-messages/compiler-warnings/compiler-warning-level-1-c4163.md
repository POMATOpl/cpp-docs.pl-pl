---
title: Kompilator ostrzeżenie (poziom 1) C4163
ms.date: 11/04/2016
f1_keywords:
- C4163
helpviewer_keywords:
- C4163
ms.assetid: b08413fd-03fc-4f41-9167-a98976ac12f2
ms.openlocfilehash: 737cf7ad00bfefd429792eed3f730844789e0c02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597172"
---
# <a name="compiler-warning-level-1-c4163"></a>Kompilator ostrzeżenie (poziom 1) C4163

'Identyfikator': nie jest dostępna jako funkcja wewnętrzna

Określona funkcja nie może służyć jako [wewnętrzne](../../preprocessor/intrinsic.md) funkcji. Kompilator ignoruje nieprawidłową nazwę funkcji.

Poniższy przykład spowoduje wygenerowanie C4163:

```
// C4163.cpp
// compile with: /W1 /LD
#include <math.h>
#pragma intrinsic(mysin)   // C4163
// try the following line instead
// #pragma intrinsic(sin)
```
---
title: Błąd kompilatora C2124
ms.date: 11/04/2016
f1_keywords:
- C2124
helpviewer_keywords:
- C2124
ms.assetid: 93392aaa-5582-4d68-8cc5-bd9c62a0ae7e
ms.openlocfilehash: 82bc4447aaf27190c013edf48a20a56c57a646c9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611669"
---
# <a name="compiler-error-c2124"></a>Błąd kompilatora C2124

Dzielenie lub dzielenie modulo przez zero

Wyrażenie stałej ma zero mianownik. Aby naprawić błąd, nie dzielenie przez zero.

Poniższy przykład spowoduje wygenerowanie C2124:

```
// C2124.cpp
int main() {
  int i = 1 / 0;   // C2124  do not divide by zero
  int i2 = 12 / 2;   // OK
}
```
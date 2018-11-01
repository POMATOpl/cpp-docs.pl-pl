---
title: Błąd kompilatora C2365
ms.date: 11/04/2016
f1_keywords:
- C2365
helpviewer_keywords:
- C2365
ms.assetid: 35839b0b-4055-4b79-8957-b3a0871bdd02
ms.openlocfilehash: 9d862fb06041b01c306560264758d13f8f75b491
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611383"
---
# <a name="compiler-error-c2365"></a>Błąd kompilatora C2365

"składowej klasy": zmiana definicji; Definicja Poprzednia była "składowej klasy"

Próbowano zmienić definicję składowej klasy.

Poniższy przykład spowoduje wygenerowanie C2365.

```
// C2365.cpp
// compile with: /c
class C1 {
   int CFunc();
   char *CFunc;   // C2365, already exists as a member function

   int CMem;
   char *CMem();   // C2365, already exists as a data member
};
```
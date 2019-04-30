---
title: Błąd kompilatora C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: d920629dc0697d0f2fdd05ac5aca6118b89b88cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378859"
---
# <a name="compiler-error-c2884"></a>Błąd kompilatora C2884

"name": wprowadzone za pomocą deklaracji koliduje z lokalnej funkcji "function"

Próbowano zdefiniować funkcję więcej niż jeden raz. Pierwsza definicja jest lokalnej definicji. Druga jest z przestrzeni nazw za pomocą `using` deklaracji.

Poniższy przykład spowoduje wygenerowanie C2884:

```
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```
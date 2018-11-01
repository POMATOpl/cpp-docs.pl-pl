---
title: Błąd kompilatora C3230
ms.date: 11/04/2016
f1_keywords:
- C3230
helpviewer_keywords:
- C3230
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
ms.openlocfilehash: a4d5edeb5898a57b99839b7e044f909cea1ec199
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428252"
---
# <a name="compiler-error-c3230"></a>Błąd kompilatora C3230

'Funkcja': argument typu szablonu dla "template" nie może zawierać parametru typu generycznego: "param"

Szablony są tworzone w czasie kompilacji, ale typy ogólne są tworzone w czasie wykonywania. W związku z tym nie jest możliwe wygenerować kod ogólny, który można wywołać tego szablonu, ponieważ nie można utworzyć wystąpienia szablonu w czasie wykonywania, gdy na koniec jest znany typ ogólny.

Poniższy przykład spowoduje wygenerowanie C3230:

```
// C3230.cpp
// compile with: /clr /LD
template <class S>
void f(S t);

generic <class U>
ref class C {
   void f1(U x) {
      f(x);   // C3230
   }
};
```
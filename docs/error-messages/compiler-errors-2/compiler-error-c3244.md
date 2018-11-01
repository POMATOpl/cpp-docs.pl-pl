---
title: Błąd kompilatora C3244
ms.date: 11/04/2016
f1_keywords:
- C3244
helpviewer_keywords:
- C3244
ms.assetid: dae6c49b-5212-4206-8f61-d4010c0b9969
ms.openlocfilehash: fe17ac0f20c5644fd5bb81094242403b244bd1d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521270"
---
# <a name="compiler-error-c3244"></a>Błąd kompilatora C3244

"method": Ta metoda została wprowadzona przez "interface", nie przez "interface"

Nastąpiła próba [jawnie przesłonić](../../cpp/explicit-overrides-cpp.md) element członkowski, który nie istnieje w określonego interfejsu, ale istnieje w innej klasy bazowej.

Poniższy przykład spowoduje wygenerowanie C3244:

```
// C3244.cpp
#pragma warning(disable:4199)

__interface IX15A {
   void f();
};

__interface IX15B {
   void g();
};

class CX15 : public IX15A, public IX15B {
public:
   void IX15A::f();
   void IX15B::g();
};

void CX15::IX15A::g()   // C3244 occurs here
{
}
```
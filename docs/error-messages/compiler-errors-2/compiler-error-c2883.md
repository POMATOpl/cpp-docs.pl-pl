---
title: Błąd kompilatora C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: 3f32307e519394433927d49aa92333fdff7b70f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587515"
---
# <a name="compiler-error-c2883"></a>Błąd kompilatora C2883

"name": deklaracja funkcji powoduje konflikt z 'Identyfikator' wynikające z deklaracji using

Próbowano zdefiniować funkcję więcej niż jeden raz. Pierwsza definicja została wprowadzona w obszarze nazw o `using` deklaracji. Drugim była lokalnej definicji.

Poniższy przykład spowoduje wygenerowanie C2883:

```
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```
---
title: Błąd kompilatora C2875 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2875
dev_langs:
- C++
helpviewer_keywords:
- C2875
ms.assetid: d589fc0c-08b2-4a79-bc0e-dca5eb80bdd5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c33813cbb6e6c6b0e7a386428414358709e0b0c9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030649"
---
# <a name="compiler-error-c2875"></a>Błąd kompilatora C2875

Deklaracja Using powoduje wielokrotną deklarację "class::identifier"

Deklaracja powoduje, że ten sam element, należy zdefiniować dwa razy.

Poniższy przykład spowoduje wygenerowanie C2875:

```
// C2875.cpp
struct A {
   void f(int*);
};

struct B {
   void f(double*);
};

struct AB : A, B {
   using A::f;
   using A::f;   // C2875
   using B::f;
};
```
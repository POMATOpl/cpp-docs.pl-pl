---
title: Błąd kompilatora C2550 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2550
dev_langs:
- C++
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd132184a993f27ec04a913cfef2aed07f8bd4a8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062517"
---
# <a name="compiler-error-c2550"></a>Błąd kompilatora C2550

'Identyfikator': listy inicjatorów konstruktora są dozwolone tylko dla definicji konstruktora

Listy inicjatorów klasy bazowej jest używany w definicji funkcji, która nie jest konstruktorem.

Poniższy przykład spowoduje wygenerowanie C2550:

```
// C2550.cpp
// compile with: /c
class C {
public:
   C();
};

class D : public C {
public:
   D();
   void func();
};

void D::func() : C() {}  // C2550
D::D() : C() {}   // OK
```
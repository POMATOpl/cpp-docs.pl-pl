---
description: 'Dowiedz się więcej o: błąd kompilatora C2881'
title: Błąd kompilatora C2881
ms.date: 11/04/2016
f1_keywords:
- C2881
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
ms.openlocfilehash: a1bc3922ce315d29f84309849660b2574631b2fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194361"
---
# <a name="compiler-error-c2881"></a>Błąd kompilatora C2881

"Namespace1": jest już używany jako alias dla elementu "namespace2"

Nie można użyć takiej samej nazwy jak alias dla dwóch przestrzeni nazw.

Poniższy przykład generuje C2881:

```cpp
// C2881.cpp
// compile with: /c
namespace A {
   int k;
}

namespace B {
   int i;
}

namespace C = A;
namespace C = B;   // C2881 C is already an alias for A
```

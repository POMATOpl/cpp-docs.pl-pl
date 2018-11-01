---
title: Błąd kompilatora C3626
ms.date: 11/04/2016
f1_keywords:
- C3626
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
ms.openlocfilehash: d0360b16c2e59bd01c3a5dd4be9c49b578b9c45b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667340"
---
# <a name="compiler-error-c3626"></a>Błąd kompilatora C3626

"— słowo kluczowe": słowo kluczowe "__event" można używać tylko na interfejsów COM, funkcji składowych i składowych danych, które są wskaźnikami do delegatów

Słowo kluczowe zostało niepoprawnie użyte.

Poniższy przykład spowoduje wygenerowanie C3626:

```
// C3626.cpp
// compile with: /c
struct A {
   __event int i;   // C3626
// try the following line instead
// __event int i();
};
```
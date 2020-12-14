---
description: 'Dowiedz się więcej o: błąd kompilatora C2317'
title: Błąd kompilatora C2317
ms.date: 11/04/2016
f1_keywords:
- C2317
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
ms.openlocfilehash: e83a69086c22349d12d041e3b6dc2fd97a227272
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282227"
---
# <a name="compiler-error-c2317"></a>Błąd kompilatora C2317

blok "try" rozpoczynający się w wierszu "number" nie ma obsługi catch

**`try`** Blok musi mieć co najmniej jedną procedurę obsługi catch.

Poniższy przykład generuje C2317:

```cpp
// C2317.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   // C2317, no catch handler
}
```

Możliwe rozwiązanie:

```cpp
// C2317b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   catch(char*) {}
}
```

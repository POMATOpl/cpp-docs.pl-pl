---
title: Błąd kompilatora C2317
ms.date: 11/04/2016
f1_keywords:
- C2317
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
ms.openlocfilehash: aef89f850ff0a280255e3ec9c4c28ea422038091
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748115"
---
# <a name="compiler-error-c2317"></a>Błąd kompilatora C2317

blok "try" rozpoczynający się w wierszu "number" nie ma obsługi catch

Blok `try` musi mieć co najmniej jedną procedurę obsługi catch.

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

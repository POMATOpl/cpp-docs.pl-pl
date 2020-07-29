---
title: Błąd kompilatora C2703
ms.date: 11/04/2016
f1_keywords:
- C2703
helpviewer_keywords:
- C2703
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
ms.openlocfilehash: 62e03d1edc5806a9babc44eaf2dc388e3ed81de9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221110"
---
# <a name="compiler-error-c2703"></a>Błąd kompilatora C2703

Niedozwolona instrukcja __leave

Blok * * `__leave** statement must be inside a ` __try ".

Poniższy przykład generuje C2703:

```cpp
// C2703.cpp
int main() {
   __leave;   // C2703
   __try {
      // try the following line instead
      __leave;
   }
   __finally {}
}
```

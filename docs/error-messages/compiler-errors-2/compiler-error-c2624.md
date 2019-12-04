---
title: Błąd kompilatora C2624
ms.date: 11/04/2016
f1_keywords:
- C2624
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
ms.openlocfilehash: 5c8e33e3760a29e8bff4280cdb4452c15cd32f94
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754761"
---
# <a name="compiler-error-c2624"></a>Błąd kompilatora C2624

klas lokalnych nie można używać do deklarowania zmiennych "extern"

Nie można użyć lokalnej klasy lub struktury do deklarowania zmiennych `extern`.

Poniższy przykład generuje C2624:

```cpp
// C2624.cpp
int main() {
   struct C {};
   extern C ac;   // C2624
}
```

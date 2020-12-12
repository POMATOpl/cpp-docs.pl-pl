---
description: 'Dowiedz się więcej o: błąd kompilatora C2050'
title: Błąd kompilatora C2050
ms.date: 11/04/2016
f1_keywords:
- C2050
helpviewer_keywords:
- C2050
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
ms.openlocfilehash: a6e6221b0985ee509953b517ae04de9f0962fe3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175043"
---
# <a name="compiler-error-c2050"></a>Błąd kompilatora C2050

wyrażenie Switch nie jest integralne

Wynikiem wyrażenia jest wartość niebędąca **`switch`** liczbą całkowitą. Aby rozwiązać ten problem, użyj tylko wartości całkowitych w instrukcjach Switch.

Poniższy przykład generuje C2050:

```cpp
// C2050.cpp
int main() {
   int a = 1;
   switch ("a") {   // C2050
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```

Możliwe rozwiązanie:

```cpp
// C2050b.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```

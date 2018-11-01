---
title: Błąd kompilatora C2751
ms.date: 11/04/2016
f1_keywords:
- C2751
helpviewer_keywords:
- C2751
ms.assetid: 44a3abdf-8a87-4a09-b34b-532c220c310a
ms.openlocfilehash: 14f458725564d39851ae16b5fd2cd5a79f00420d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470801"
---
# <a name="compiler-error-c2751"></a>Błąd kompilatora C2751

"parametru": nie może być kwalifikowana nazwa parametru funkcji

Nie można użyć kwalifikowanej nazwy, jako parametru funkcji.

Poniższy przykład spowoduje wygenerowanie C2751:

```
// C2751.cpp
namespace std {
   template<typename T>
   class list {};
}

#define list std::list
void f(int &list){}   // C2751
```
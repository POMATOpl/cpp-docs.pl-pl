---
description: 'Dowiedz się więcej o: błąd kompilatora C2106'
title: Błąd kompilatora C2106
ms.date: 11/04/2016
f1_keywords:
- C2106
helpviewer_keywords:
- C2106
ms.assetid: d5c91a2e-04e4-4770-8478-788b98c52a53
ms.openlocfilehash: edcd926763fc76fba0329ccc22b4d263b5042f4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170155"
---
# <a name="compiler-error-c2106"></a>Błąd kompilatora C2106

"operator": lewy operand musi być l-wartością

Operator musi mieć wartość l-wartości jako jej lewy argument operacji.

Poniższy przykład generuje C2106:

```cpp
// C2106.cpp
int main() {
   int a;
   1 = a;   // C2106
   a = 1;   // OK
}
```

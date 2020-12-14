---
description: 'Dowiedz się więcej o: błąd kompilatora C2333'
title: Błąd kompilatora C2333
ms.date: 11/04/2016
f1_keywords:
- C2333
helpviewer_keywords:
- C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
ms.openlocfilehash: 6db3e68dd9a709abbb8153ad8b4acdaf7d4d6f9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234894"
---
# <a name="compiler-error-c2333"></a>Błąd kompilatora C2333

"Function": błąd w deklaracji funkcji; Pomijanie treści funkcji

Ten błąd występuje po wystąpieniu innego błędu dla funkcji Członkowskich zdefiniowanych wewnątrz ich klasy.

Poniższy przykład generuje C2333:

```cpp
// C2333.cpp
struct s1 {
   s1(s1) {}   // C2333
};
```

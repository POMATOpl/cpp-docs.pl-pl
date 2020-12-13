---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4280'
title: Ostrzeżenie kompilatora (poziom 3) C4280
ms.date: 11/04/2016
f1_keywords:
- C4280
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
ms.openlocfilehash: e2ef8d4961bf4046d2501d5724ff487bb1526ce2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344136"
---
# <a name="compiler-warning-level-3-c4280"></a>Ostrzeżenie kompilatora (poziom 3) C4280

element "operator->" był samocykliczny przy użyciu typu "Type"

Kod niepoprawnie umożliwia **operatorowi >** wywoływanie siebie.

Poniższy przykład generuje C4280:

```cpp
// C4280.cpp
// compile with: /W3 /WX
struct A
{
   int z;
   A& operator ->();
};

void f(A y)
{
   int i = y->z; // C4280
}
```

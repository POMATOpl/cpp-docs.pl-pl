---
description: 'Dowiedz się więcej o: błąd kompilatora C2100'
title: Błąd kompilatora C2100
ms.date: 11/04/2016
f1_keywords:
- C2100
helpviewer_keywords:
- C2100
ms.assetid: 9ed5ea11-9d55-4ddf-8b1a-162c74f3c390
ms.openlocfilehash: 6e63f17ed7d7cf7e77b421e4706869313a078e62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341311"
---
# <a name="compiler-error-c2100"></a>Błąd kompilatora C2100

niedozwolony operator pośredni

Operator pośredni ( `*` ) jest stosowany do wartości niebędącej punktem.

Poniższy przykład generuje C2100:

```cpp
// C2100.cpp
int main() {
   int r = 0, *s = 0;
   s = &r;
   *r = 200;   // C2100
   *s = 200;   // OK
}
```

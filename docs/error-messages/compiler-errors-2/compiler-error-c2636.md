---
description: 'Dowiedz się więcej o: błąd kompilatora C2636'
title: Błąd kompilatora C2636
ms.date: 11/04/2016
f1_keywords:
- C2636
helpviewer_keywords:
- C2636
ms.assetid: 379873ec-8d05-49f8-adf1-b067bc07bdb8
ms.openlocfilehash: 789da819b85435bfb54d0f88c6e6c1414f04b6f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208739"
---
# <a name="compiler-error-c2636"></a>Błąd kompilatora C2636

"Identyfikator": wskaźnik do odwołania składowej jest niedozwolony

Zadeklarowano wskaźnik do składowej odwołania.

Poniższy przykład generuje C2636:

```cpp
// C2636.cpp
struct S {};
int main() {
   int &S::*prs;   // C2636
   int S::*prs1;   // OK
   int *S::*prs2;   // OK
}
```

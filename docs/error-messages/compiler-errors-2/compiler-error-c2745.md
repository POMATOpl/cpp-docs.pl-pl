---
description: 'Dowiedz się więcej o: błąd kompilatora C2745'
title: Błąd kompilatora C2745
ms.date: 11/04/2016
f1_keywords:
- C2745
helpviewer_keywords:
- C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
ms.openlocfilehash: 3f80ce1c13e8f1beeaa241e0638dfc9de784c3fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123035"
---
# <a name="compiler-error-c2745"></a>Błąd kompilatora C2745

"token": ten token nie może zostać przekonwertowany na identyfikator

Identyfikatory muszą składać się z znaków prawnych.

Poniższy przykład generuje C2745:

```cpp
// C2745.cpp
// compile with: /clr
int main() {
   int __identifier([));   // C2745
}
```

---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4090'
title: Ostrzeżenie kompilatora (poziom 1) C4090
ms.date: 11/04/2016
f1_keywords:
- C4090
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
ms.openlocfilehash: c096a32e5aa0d632d43d9990f3256c3f865bf796
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278106"
---
# <a name="compiler-warning-level-1-c4090"></a>Ostrzeżenie kompilatora (poziom 1) C4090

"Operation": różne kwalifikatory "modyfikator"

Zmienna użyta w operacji jest zdefiniowana z określonym modyfikatorem, który uniemożliwia jego modyfikację bez wykrywania przez kompilator. Wyrażenie jest kompilowane bez modyfikacji.

To ostrzeżenie może być spowodowane tym, że wskaźnik do **`const`** **`volatile`** elementu lub jest przypisany do wskaźnika, który nie został zadeklarowany jako wskazanie **`const`** lub **`volatile`** .

To ostrzeżenie jest wydawane dla programów C. W programie w języku C++ kompilator wystawia błąd: [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).

Poniższy przykład generuje C4090:

```c
// C4090.c
// compile with: /W1
int *volatile *p;
int *const *q;
int **r;

int main() {
   p = q;   // C4090
   p = r;
   q = p;   // C4090
   q = r;
   r = p;   // C4090
   r = q;   // C4090
}
```

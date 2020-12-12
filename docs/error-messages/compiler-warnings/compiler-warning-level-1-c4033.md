---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4033'
title: Ostrzeżenie kompilatora (poziom 1) C4033
ms.date: 11/04/2016
f1_keywords:
- C4033
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
ms.openlocfilehash: 1d2455d62b3c375b0f1a863e6cfc3064f44e840a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325962"
---
# <a name="compiler-warning-level-1-c4033"></a>Ostrzeżenie kompilatora (poziom 1) C4033

Funkcja "Function" musi zwracać wartość

Ta funkcja nie zwraca wartości. Zwrócona wartość jest niezdefiniowana.

Funkcje, które używają **`return`** bez wartości zwracanej, muszą być zadeklarowane jako typ **`void`** .

Ten błąd jest przeznaczony dla kodu języka C.

Poniższy przykład generuje C4033:

```c
// C4033.c
// compile with: /W1 /LD
int test_1(int x)   // C4033 expected
{
   if (x)
   {
      return;   // C4033
   }
}
```

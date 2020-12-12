---
description: 'Dowiedz się więcej o: błąd kompilatora C2657'
title: Błąd kompilatora C2657
ms.date: 11/04/2016
f1_keywords:
- C2657
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
ms.openlocfilehash: dfec399c4b65615310263aa58db145b87c42594d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286075"
---
# <a name="compiler-error-c2657"></a>Błąd kompilatora C2657

"Class::*" znaleziono na początku instrukcji (Czy pamiętasz o określeniu typu?)

Linia została rozpoczęta z identyfikatorem wskaźnika do elementu członkowskiego.

Ten błąd może być spowodowany brakiem specyfikatora typu w deklaracji wskaźnika do składowej.

Poniższy przykład generuje C2657:

```cpp
// C2657.cpp
class C {};
int main() {
   C::* pmc1;        // C2657
   int C::* pmc2;   // OK
}
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C2400'
title: Błąd kompilatora C2400
ms.date: 11/04/2016
f1_keywords:
- C2400
helpviewer_keywords:
- C2400
ms.assetid: 1ba441ee-73f9-42a5-bfe9-fbeab93808eb
ms.openlocfilehash: 64582d04e232c574dd132741dd1663e4055fe05f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145369"
---
# <a name="compiler-error-c2400"></a>Błąd kompilatora C2400

błąd składni wbudowanego asemblera w "context"; znaleziono "token"

Token spowodował błąd składniowy w określonym kontekście.

Poniższy przykład generuje C2400:

```cpp
// C2400.cpp
// processor: x86
int main() {
   __asm {
      heh ax,bx;   // C2400, heh is not a valid x86 instruction
      mov ax,bx;   // OK
   }
}
```

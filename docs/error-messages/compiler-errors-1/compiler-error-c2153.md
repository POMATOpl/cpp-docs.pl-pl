---
description: 'Dowiedz się więcej o: błąd kompilatora C2153'
title: Błąd kompilatora C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: 0b5ded0908f3c12033f1c2b3b034b41b52e847cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181296"
---
# <a name="compiler-error-c2153"></a>Błąd kompilatora C2153

stałe szesnastkowe muszą mieć co najmniej jedną cyfrę szesnastkową

Stałe szesnastkowe 0x, 0X i \x są nieprawidłowe. Co najmniej jedna cyfra szesnastkowa musi następować po x lub X.

Poniższy przykład generuje C2153:

```cpp
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```

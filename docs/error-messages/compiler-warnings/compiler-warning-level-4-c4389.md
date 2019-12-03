---
title: Ostrzeżenie kompilatora (poziom 4) C4389
ms.date: 11/04/2016
f1_keywords:
- c4389
helpviewer_keywords:
- C4389
ms.assetid: fc0e3a8e-f766-437c-b7f1-e61abb2a8765
ms.openlocfilehash: 2cfb33e8a79259d0ff02dfd832a1b5943cbc0da9
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2019
ms.locfileid: "74682949"
---
# <a name="compiler-warning-level-4-c4389"></a>Ostrzeżenie kompilatora (poziom 4) C4389

"operator": niezgodność ze znakiem/bez znaku

Operacja dotyczyła podpisane i niepodpisane zmienne. Może to spowodować utratę danych.

Poniższy przykład generuje C4389:

```cpp
// C4389.cpp
// compile with: /W4
#pragma warning(default: 4389)

int main()
{
   int a = 9;
   unsigned int b = 10;
   if (a == b)   // C4389
      return 0;
   else
      return 0;
};
```
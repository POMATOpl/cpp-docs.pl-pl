---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4197'
title: Ostrzeżenie kompilatora (poziom 3) C4197
ms.date: 11/04/2016
f1_keywords:
- C4197
helpviewer_keywords:
- C4197
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
ms.openlocfilehash: f52c37e28ce681b96158b7e1f10fef3e9f121522
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344214"
---
# <a name="compiler-warning-level-3-c4197"></a>Ostrzeżenie kompilatora (poziom 3) C4197

"Type": nietrwały element Top-Level w rzutowaniu jest ignorowany

Kompilator wykrył rzutowanie na typ wartości r, który jest kwalifikowany za pomocą [volatile](../../cpp/volatile-cpp.md), lub rzutowanie typu r-Value na typ, który jest kwalifikowany z nietrwałym. Zgodnie ze standardem C (6.5.3), właściwości skojarzone z kwalifikowanymi typami są zrozumiałe tylko dla wyrażeń l-wartości.

Poniższy przykład generuje C4197:

```cpp
// C4197.cpp
// compile with: /W3
#include <stdio.h>
#include <signal.h>
#include <stdlib.h>

void sigproc(int);
struct S
{
   int i;
} s;

int main()
{
   signal(SIGINT, sigproc);
   s.i = 1;
   S *pS = &s;
   for ( ; (volatile int)pS->i ; )   // C4197
      break;
   // for ( ; *(volatile int *)&pS->i ; )   // OK
   //    break;
}

void sigproc(int) // ctrl-C
{
   signal(SIGINT, sigproc);
   s.i = 0;
}
```

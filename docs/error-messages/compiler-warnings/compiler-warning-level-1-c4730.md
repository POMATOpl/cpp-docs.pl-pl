---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4730'
title: Ostrzeżenie C4730 kompilatora (poziom 1)
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: e026d44bc76d58c934eeccc363f4385f43d15597
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150660"
---
# <a name="compiler-warning-level-1-c4730"></a>Ostrzeżenie C4730 kompilatora (poziom 1)

"Main": mieszanie _m64 i wyrażeń zmiennoprzecinkowych może spowodować niewłaściwy kod

Funkcja używa [__m64](../../cpp/m64.md) i **`float`** / **`double`** typów. Ze względu na to, że rejestry MMX i zmiennoprzecinkowe współdzielą ten sam obszar rejestru fizycznego (nie mogą być używane jednocześnie), użycie **`__m64`** i **`float`** / **`double`** typy w tej samej funkcji mogą spowodować uszkodzenie danych, co może powodować wyjątek.

Aby bezpiecznie używać **`__m64`** typów i typów zmiennoprzecinkowych w tej samej funkcji, każda instrukcja, która używa jednego z typów, powinna być oddzielona **_m_empty ()** (dla systemu MMX) lub **_m_femms ()** (dla 3DNow!).

Poniższy przykład generuje C4730:

```cpp
// C4730.cpp
// compile with: /W1
// processor: x86
#include "mmintrin.h"

void func(double)
{
}

int main(__m64 a, __m64 b)
{
   __m64 m;
   double f;
   f = 1.0;
   m = _m_paddb(a, b);
   // uncomment the next line to resolve C4730
   // _m_empty();
   func(f * 3.0);   // C4730
}
```

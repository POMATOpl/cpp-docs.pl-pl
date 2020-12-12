---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4566'
title: Ostrzeżenie kompilatora (poziom 1) C4566
ms.date: 11/04/2016
f1_keywords:
- C4566
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
ms.openlocfilehash: 2e0d1f5b80a42d58f2866109957e466d3ab36cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332243"
---
# <a name="compiler-warning-level-1-c4566"></a>Ostrzeżenie kompilatora (poziom 1) C4566

znak reprezentowany przez nazwę typu uniwersalnego "char" nie może być przedstawiony w bieżącej stronie kodowej (strona)

Nie każdy znak Unicode może być przedstawiony w bieżącej stronie kodowej ANSI.

Wąskie ciągi (znaki jednobajtowe) są konwertowane na znaki wielobajtowe, natomiast szerokie ciągi (znaki dwubajtowe) nie są.

Poniższy przykład generuje C4566:

```cpp
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```

---
title: Kompilator ostrzeżenie (poziom 3) C4267
ms.date: 11/04/2016
f1_keywords:
- C4267
helpviewer_keywords:
- C4267
ms.assetid: 2fa2f13f-fa4f-47bb-ad8f-6cb19cfc91e6
ms.openlocfilehash: 31e5b9a9b8e7b25a0d54648ce808ff6266a27321
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608042"
---
# <a name="compiler-warning-level-3-c4267"></a>Kompilator ostrzeżenie (poziom 3) C4267

"var": konwersja z "size_t" do "type", możliwa utrata danych

Kompilator wykrył konwersja `size_t` typowi mniejsze.

Aby usunąć to ostrzeżenie, użyj `size_t` zamiast `type`. Można również użyć integralny typ, który jest przynajmniej tak duże jak `size_t`.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4267.

```
// C4267.cpp
// compile by using: cl /W4 C4267.cpp
void Func1(short) {}
void Func2(int) {}
void Func3(long) {}
void Func4(size_t) {}

int main() {
   size_t bufferSize = 10;
   Func1(bufferSize);   // C4267 for all platforms
   Func2(bufferSize);   // C4267 only for 64-bit platforms
   Func3(bufferSize);   // C4267 only for 64-bit platforms
   Func4(bufferSize);   // OK for all platforms
}
```
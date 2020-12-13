---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4267'
title: Ostrzeżenie kompilatora (poziom 3) C4267
ms.date: 11/04/2016
f1_keywords:
- C4267
helpviewer_keywords:
- C4267
ms.assetid: 2fa2f13f-fa4f-47bb-ad8f-6cb19cfc91e6
ms.openlocfilehash: 25d0eb776482bb50bdc4dbfec1d1ae46978afb0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344162"
---
# <a name="compiler-warning-level-3-c4267"></a>Ostrzeżenie kompilatora (poziom 3) C4267

"var": konwersja z "size_t" na "Type", możliwa utrata danych

Kompilator wykrył konwersję z `size_t` do mniejszego typu.

Aby usunąć to ostrzeżenie, użyj `size_t` zamiast `type` . Alternatywnie użyj typu całkowitego, który jest co najmniej tak duży `size_t` .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4267.

```cpp
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

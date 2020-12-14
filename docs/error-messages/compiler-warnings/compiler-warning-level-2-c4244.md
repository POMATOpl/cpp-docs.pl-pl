---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 2) C4244'
title: Ostrzeżenie kompilatora (poziom 2) C4244
ms.date: 11/04/2016
f1_keywords:
- C4244
helpviewer_keywords:
- C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
ms.openlocfilehash: b51af5179c9afbf01529f545bbc602ac9c9fac6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238131"
---
# <a name="compiler-warning-level-2-c4244"></a>Ostrzeżenie kompilatora (poziom 2) C4244

"argument": konwersja z "type1" na "type2", możliwa utrata danych

Typ zmiennoprzecinkowy został przekonwertowany na typ Integer.  Mogła wystąpić utrata danych.

W przypadku uzyskania C4244 należy zmienić program tak, aby korzystał z zgodnych typów, lub dodać do kodu logikę, aby upewnić się, że zakres możliwych wartości będzie zawsze zgodny z typami, z których korzystasz.

C4244 może również być wyzwalane na poziomie 3 i 4; Aby uzyskać więcej informacji, zobacz [Ostrzeżenie kompilatora (poziomy 3 i 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4244:

```cpp
// C4244_level2.cpp
// compile with: /W2

int f(int x){ return 0; }
int main() {
   double x = 10.1;
   int i = 10;
   return (f(x));   // C4244
   // try the following line instead
   // return (f(i));
}
```

---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4162'
title: Ostrzeżenie kompilatora (poziom 1) C4162
ms.date: 11/04/2016
f1_keywords:
- C4162
helpviewer_keywords:
- C4162
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
ms.openlocfilehash: 471d424329e2954ca96c860cabdc9774395b612b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267173"
---
# <a name="compiler-warning-level-1-c4162"></a>Ostrzeżenie kompilatora (poziom 1) C4162

"Identyfikator": nie znaleziono funkcji z powiązaniem C

Funkcja z powiązaniem C jest zadeklarowana, ale nie można jej odnaleźć.

Aby rozwiązać ten problem, skompiluj w pliku c (Wywołaj kompilator C).  Jeśli musisz wywołać kompilator języka C++, umieść extern "C" przed deklaracją funkcji.

Poniższy przykład generuje C4162

```cpp
// C4162.cpp
// compile with: /c /W1
unsigned char _bittest(long* a, long b);
#pragma intrinsic (_bittest)   // C4162

int main() {
   bool bit;
   long num = 78002;
   bit = _bittest(&num, 5);
}
```

Możliwe rozwiązanie:

```cpp
// C4162b.cpp
// compile with: /c
extern "C"
unsigned char _bittest(long* a, long b);
#pragma intrinsic (_bittest)

int main() {
   bool bit;
   long num = 78002;
   bit = _bittest(&num, 5);
}
```

---
title: Błąd kompilatora C2864 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2864
dev_langs:
- C++
helpviewer_keywords:
- C2864
ms.assetid: d0ca2ad9-90a6-4aef-8511-98a3b414c102
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 428f97904f88198efb0dbbf67e9c5e360f7fb62e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097929"
---
# <a name="compiler-error-c2864"></a>Błąd kompilatora C2864

'zmienna': statyczna składowa danych z inicjatorem w klasie musi być typu nieulotnego stałego całkowitoliczbowego

Aby zainicjować `static` składowej danych, która jest zdefiniowana jako `volatile`, nie —`const`, lub nie typu całkowitoliczbowego, należy użyć instrukcji definicji elementu członkowskiego. Nie mogą one być inicjowane w deklaracji.

Ten przykład generuje C2864:

```
// C2864.cpp
// compile with: /c
class B  {
private:
   int a = 3;   // OK
   static int b = 3;   // C2864
   volatile static int c = 3;   // C2864
   volatile static const int d = 3;   // C2864
   const static long long e = 3;   // OK
   static const double f = 3.33;   // C2864
};
```

Ten przykład pokazuje, jak naprawić C2864:

```
// C2864b.cpp
// compile with: /c
class C  {
private:
   int a = 3;
   static int b; // = 3; C2864
   volatile static int c; // = 3; C2864
   volatile static const int d; // = 3; C2864
   static const long long e = 3;
   static const double f; // = 3.33; C2864
};

// Initialize static volatile, non-const, or non-integral
// data members when defined, not when declared:
int C::b = 3;
volatile int C::c = 3;
volatile const int C::d = 3;
const double C::f = 3.33;
```
---
title: Błąd kompilatora C2864
ms.date: 11/04/2016
f1_keywords:
- C2864
helpviewer_keywords:
- C2864
ms.assetid: d0ca2ad9-90a6-4aef-8511-98a3b414c102
ms.openlocfilehash: 9bfc18137df1a54530011a8ec3f7ea50b1d6c86a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227503"
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
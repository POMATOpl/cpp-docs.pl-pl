---
title: Błąd krytyczny C1202
ms.date: 11/04/2016
f1_keywords:
- C1202
helpviewer_keywords:
- C1202
ms.assetid: c859adb8-17a7-4fa1-a1f3-5820b7bf3849
ms.openlocfilehash: c9aeccd0a7bf29edd5ecab91ee1de6c76fa2512e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585240"
---
# <a name="fatal-error-c1202"></a>Błąd krytyczny C1202

cyklicznego typu lub funkcji zależności kontekstu zbyt złożony

Definicja szablonu jest cykliczne lub przekroczenia limitów złożoności.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C1202.

```
// C1202.cpp
// processor: x86 IPF
template<int n>
class Factorial : public Factorial<n-1>  {   // C1202
public:
   operator int () {
      return Factorial <n-1>::operator int () * n;
   }
};
Factorial<7> facSeven;
```

## <a name="example"></a>Przykład

Możliwe rozwiązanie.

```
// C1202b.cpp
// compile with: /c
template<int n>
class Factorial : public Factorial<n-1> {
public:
   operator int () {
      return Factorial <n-1>::operator int () * n;
   }
};

template <>
class Factorial<0> {
public:
   operator int () {
      return 1;
   }
};

Factorial<7> facSeven;
```
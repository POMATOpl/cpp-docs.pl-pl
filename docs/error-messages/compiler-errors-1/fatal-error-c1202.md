---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1202'
title: Błąd krytyczny C1202
ms.date: 11/04/2016
f1_keywords:
- C1202
helpviewer_keywords:
- C1202
ms.assetid: c859adb8-17a7-4fa1-a1f3-5820b7bf3849
ms.openlocfilehash: 72c7556a390c00b8e83b05c8a78535836b316318
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268109"
---
# <a name="fatal-error-c1202"></a>Błąd krytyczny C1202

kontekst cyklicznego typu lub funkcji zależności zbyt złożony

Definicja szablonu była cykliczna lub przekroczyła limity złożoności.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C1202.

```cpp
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

Możliwe rozwiązanie.

```cpp
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

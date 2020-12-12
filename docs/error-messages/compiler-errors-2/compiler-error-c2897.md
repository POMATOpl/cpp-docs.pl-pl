---
description: 'Dowiedz się więcej o: błąd kompilatora C2897'
title: Błąd kompilatora C2897
ms.date: 11/04/2016
f1_keywords:
- C2897
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
ms.openlocfilehash: b1a1f66987aa4bbd01fdf12f88f8933e3436938a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270878"
---
# <a name="compiler-error-c2897"></a>Błąd kompilatora C2897

destruktor/finalizator nie może być szablonem funkcji

Destruktory i finalizatory nie mogą być przeciążone, dlatego deklarując destruktor jako szablon (który definiuje zestaw destruktorów) jest niedozwolony.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2897.

```cpp
// C2897.cpp
// compile with: /c
class X {
public:
   template<typename T> ~X() {}   // C2897
};
```

Poniższy przykład generuje C2897.

```cpp
// C2897_b.cpp
// compile with: /c /clr
ref struct R2 {
protected:
   template<typename T> !R2(){}   // C2897 error
};
```

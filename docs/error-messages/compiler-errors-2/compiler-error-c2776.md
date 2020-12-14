---
description: 'Dowiedz się więcej o: błąd kompilatora C2776'
title: Błąd kompilatora C2776
ms.date: 11/04/2016
f1_keywords:
- C2776
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
ms.openlocfilehash: 75e0121c61fd55aa89e6ffcc6e1ed00137fcaaca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298139"
---
# <a name="compiler-error-c2776"></a>Błąd kompilatora C2776

tylko jedna metoda "Get" może być określona dla właściwości

Można określić tylko jedną `get` funkcję w rozszerzonym atrybucie [Właściwości](../../cpp/property-cpp.md) . Ten błąd występuje, gdy `get` określono wiele funkcji.

Poniższy przykład generuje C2776:

```cpp
// C2776.cpp
struct A {
   __declspec(property(get=GetProp,get=GetPropToo))
   // try the following line instead
   // __declspec(property(get=GetProp))
      int prop;   // C2776
   int GetProp(void);
   int GetPropToo(void);
};
```

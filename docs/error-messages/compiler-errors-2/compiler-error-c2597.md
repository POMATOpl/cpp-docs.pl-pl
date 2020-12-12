---
description: 'Dowiedz się więcej o: błąd kompilatora C2597'
title: Błąd kompilatora C2597
ms.date: 11/04/2016
f1_keywords:
- C2597
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
ms.openlocfilehash: b3430da85cef961b7c26b55e8dee9f1911533faf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120142"
---
# <a name="compiler-error-c2597"></a>Błąd kompilatora C2597

niedozwolone odwołanie do niestatycznego elementu członkowskiego "identifier"

Możliwe przyczyny:

1. Niestatyczny element członkowski jest określony w statycznej funkcji członkowskiej. Aby uzyskać dostęp do niestatycznej składowej, należy przekazać lub utworzyć lokalne wystąpienie klasy i użyć operatora dostępu do składowych ( `.` lub `->` ).

1. Określony identyfikator nie jest elementem członkowskim klasy, struktury lub Unii. Sprawdź pisownię identyfikatorów.

1. Operator dostępu do składowej odwołuje się do funkcji nienależącej do elementu członkowskiego.

1. Poniższy przykład generuje C2597 i pokazuje, jak to naprawić:

```cpp
// C2597.cpp
// compile with: /c
struct s1 {
   static void func();
   static void func2(s1&);
   int i;
};

void s1::func() {
   i = 1;    // C2597 - static function can't access non-static data member
}

// OK - fix by passing an instance of s1
void s1::func2(s1& a) {
   a.i = 1;
}
```

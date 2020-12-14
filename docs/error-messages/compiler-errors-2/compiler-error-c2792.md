---
description: 'Dowiedz się więcej o: błąd kompilatora C2792'
title: Błąd kompilatora C2792
ms.date: 11/04/2016
f1_keywords:
- C2792
helpviewer_keywords:
- C2792
ms.assetid: 392cf748-4f5e-4e62-a364-3118d5658408
ms.openlocfilehash: 5699f734574aaadd01aa6ddabac09facc249fb1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297762"
---
# <a name="compiler-error-c2792"></a>Błąd kompilatora C2792

"Super": to słowo kluczowe musi następować "::"

Jedyny token, który może następować po słowie kluczowym **`__super`** `::` .

Poniższy przykład generuje C2792:

```cpp
// C2792.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super.();   // C2792

      // try the following line instead
      // __super::mf();
   }
};
```

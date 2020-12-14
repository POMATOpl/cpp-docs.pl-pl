---
description: 'Dowiedz się więcej o: błąd kompilatora C2798'
title: Błąd kompilatora C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: d3a78eaf09797d658c64b5659dcd0e05191fab1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297593"
---
# <a name="compiler-error-c2798"></a>Błąd kompilatora C2798

element "Super:: member" jest niejednoznaczny

Wiele dziedziczonych struktur zawiera element członkowski, do którego odwołuje się [Super](../../cpp/super.md). Błąd można naprawić, wykonując jedną z:

- Usuwanie B1 lub B2 z listy dziedziczenia D.

- Zmiana nazwy elementu członkowskiego danych w B1 lub B2.

Poniższy przykład generuje C2798:

```cpp
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```

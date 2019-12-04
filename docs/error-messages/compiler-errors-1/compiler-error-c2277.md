---
title: Błąd kompilatora C2277
ms.date: 11/04/2016
f1_keywords:
- C2277
helpviewer_keywords:
- C2277
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
ms.openlocfilehash: d1c39203d8733b3992ed73172bb58fd7431e110a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759194"
---
# <a name="compiler-error-c2277"></a>Błąd kompilatora C2277

"Identyfikator": nie może przyjmować adresu tej funkcji składowej

Nie można przyjąć adresu funkcji składowej.

Poniższy przykład generuje C2277:

```cpp
// C2277.cpp
class A {
public:
   A();
};
(*pctor)() = &A::A;   // C2277
```

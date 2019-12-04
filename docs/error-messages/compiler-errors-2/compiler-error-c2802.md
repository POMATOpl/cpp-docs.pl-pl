---
title: Błąd kompilatora C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: 12ce65def043a05f5f154130b64326797a974137
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758297"
---
# <a name="compiler-error-c2802"></a>Błąd kompilatora C2802

Statyczny element członkowski "operator operatora" nie ma formalnych parametrów

Operator zadeklarowany przez `static`ą funkcję członkowską musi mieć co najmniej jeden parametr.

Poniższy przykład generuje C2802:

```cpp
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```

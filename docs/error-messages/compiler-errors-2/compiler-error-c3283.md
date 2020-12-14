---
description: 'Dowiedz się więcej o: błąd kompilatora C3283'
title: Błąd kompilatora C3283
ms.date: 11/04/2016
f1_keywords:
- C3283
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
ms.openlocfilehash: 577f3fa6c3316c58bf6e9dca94b22a168a451b17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311880"
---
# <a name="compiler-error-c3283"></a>Błąd kompilatora C3283

"Type": interfejs nie może mieć konstruktora wystąpień

[Interfejs](../../extensions/interface-class-cpp-component-extensions.md) CLR nie może mieć konstruktora wystąpienia.  Dozwolony jest Konstruktor statyczny.

Poniższy przykład generuje C3283:

```cpp
// C3283.cpp
// compile with: /clr
interface class I {
   I();   // C3283
};
```

Możliwe rozwiązanie:

```cpp
// C3283b.cpp
// compile with: /clr /c
interface class I {
   static I(){}
};
```

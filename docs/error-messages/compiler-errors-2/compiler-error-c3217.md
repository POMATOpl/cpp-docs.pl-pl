---
description: 'Dowiedz się więcej o: błąd kompilatora C3217'
title: Błąd kompilatora C3217
ms.date: 11/04/2016
f1_keywords:
- C3217
helpviewer_keywords:
- C3217
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
ms.openlocfilehash: 3e38c188f5e6d061312cc9994e86143a6661a287
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173717"
---
# <a name="compiler-error-c3217"></a>Błąd kompilatora C3217

"param": parametr generyczny nie może być ograniczony w tej deklaracji

Ograniczenie zostało źle sformułowane; parametr generyczny ograniczenia musi zgadzać się z parametrem szablonu klasy ogólnej.

Poniższy przykład generuje C3217:

```cpp
// C3217.cpp
// compile with: /clr
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T : A   // C3217
   void f();
};
```

Poniższy przykład demonstruje możliwe rozwiązanie:

```cpp
// C3217b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T1 : A
   void f();
};
```

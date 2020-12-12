---
description: 'Dowiedz się więcej o: błąd kompilatora C2902'
title: Błąd kompilatora C2902
ms.date: 11/04/2016
f1_keywords:
- C2902
helpviewer_keywords:
- C2902
ms.assetid: 89d78d0e-78e5-4c2c-a0f9-a60110e9395e
ms.openlocfilehash: 45e58615e6bd2465489da7059a350ef476b705a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270761"
---
# <a name="compiler-error-c2902"></a>Błąd kompilatora C2902

"token": Nieoczekiwany token następujący po "template", Oczekiwano identyfikatora

Token następujący po słowie kluczowym **`template`** nie jest identyfikatorem.

Poniższy przykład generuje C2902:

```cpp
// C2902.cpp
// compile with: /c
namespace N {
   template<class T> class X {};
   class Y {};
}
void g() {
   N::template + 1;   // C2902
}

void f() {
   N::template X<int> x1;   // OK
}
```

C2902 może również wystąpić przy użyciu typów ogólnych:

```cpp
// C2902b.cpp
// compile with: /clr /c
namespace N {
   generic<class T> ref class GC {};
}

void f() {
   N::generic + 1;   // C2902
   N::generic GC<int>^ x;
}
```

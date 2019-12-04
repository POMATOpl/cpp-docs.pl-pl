---
title: Błąd kompilatora C3207
ms.date: 11/04/2016
f1_keywords:
- C3207
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
ms.openlocfilehash: 718c731985e6578787d190c70cb8041bd85ab8e7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751081"
---
# <a name="compiler-error-c3207"></a>Błąd kompilatora C3207

"Function": nieprawidłowy argument szablonu dla elementu "ARG", oczekiwano szablonu klasy

Funkcja szablonu jest definiowana jako przyjmujący argument szablonu. Jednak argument typu szablonu został przekazano.

Poniższy przykład generuje C3207:

```cpp
// C3207.cpp
template <template <class T> class TT>
void f(){}

template <class T>
struct S
{
};

void f1()
{
   f<S<int> >();   // C3207
   // try the following line instead
   // f<S>();
}
```

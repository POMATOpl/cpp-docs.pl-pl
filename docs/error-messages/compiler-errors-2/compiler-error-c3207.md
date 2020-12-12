---
description: 'Dowiedz się więcej o: błąd kompilatora C3207'
title: Błąd kompilatora C3207
ms.date: 11/04/2016
f1_keywords:
- C3207
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
ms.openlocfilehash: 744dbee62e6247b07ca07354c44d4ebb7a438766
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173990"
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

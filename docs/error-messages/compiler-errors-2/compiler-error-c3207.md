---
title: Błąd kompilatora C3207
ms.date: 11/04/2016
f1_keywords:
- C3207
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
ms.openlocfilehash: 51873e089499e42f4ddeb97c95e3f18416df447c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402713"
---
# <a name="compiler-error-c3207"></a>Błąd kompilatora C3207

'Funkcja': nieprawidłowy argument szablonu dla "arg", Oczekiwano klasy szablonu

Funkcja szablonu jest zdefiniowany jako biorąc argument szablonu szablonu. Jednak został przekazany argument typu szablonu.

Poniższy przykład spowoduje wygenerowanie C3207:

```
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
---
description: 'Dowiedz się więcej o: błąd kompilatora C2784'
title: Błąd kompilatora C2784
ms.date: 11/04/2016
f1_keywords:
- C2784
helpviewer_keywords:
- C2784
ms.assetid: 3d761fe2-881c-48bd-afae-e2e714e20473
ms.openlocfilehash: dcee0cc2c6c8154bafe4a37fe83c66b1c8d477d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297918"
---
# <a name="compiler-error-c2784"></a>Błąd kompilatora C2784

"Deklaracja": nie można wywnioskować argumentu szablonu dla elementu "Type" z typu "Type"

Kompilator nie może określić argumentu szablonu na podstawie podanych argumentów funkcji.

Poniższy przykład generuje C2784 i pokazuje, jak to naprawić:

```cpp
// C2784.cpp
template<class T> class X {};
template<class T> void f(X<T>) {}

int main() {
   X<int> x;
   f(1);   // C2784

   // To fix it, try the following line instead
   f(x);
}
```

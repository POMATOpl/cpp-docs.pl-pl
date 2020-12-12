---
description: 'Dowiedz się więcej o: błąd kompilatora C3255'
title: Błąd kompilatora C3255
ms.date: 11/04/2016
f1_keywords:
- C3255
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
ms.openlocfilehash: 576b2c9126173f72470a6e741dd64d8a356c9224
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194205"
---
# <a name="compiler-error-c3255"></a>Błąd kompilatora C3255

"typ wartości": nie można dynamicznie przydzielić tego obiektu typu wartościowego na stercie natywnym

Wystąpienia typu wartości (zobacz [klasy i struktury](../../extensions/classes-and-structs-cpp-component-extensions.md)) zawierające zarządzane elementy członkowskie można utworzyć na stosie, ale nie na stercie.

Poniższy przykład generuje C3255:

```cpp
// C3255.cpp
// compile with: /clr
using namespace System;
value struct V {
   Object^ o;
};

value struct V2 {
   int i;
};

int main() {
   V* pv = new V;   // C3255
   V2* pv2 = new V2;
   V v2;
}
```

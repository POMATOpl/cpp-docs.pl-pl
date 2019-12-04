---
title: Błąd kompilatora C3255
ms.date: 11/04/2016
f1_keywords:
- C3255
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
ms.openlocfilehash: 43538ce87e1d832fcfc4fca882a9f129b917aad5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754215"
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

---
description: 'Dowiedz się więcej o: błąd kompilatora C3352'
title: Błąd kompilatora C3352
ms.date: 11/04/2016
f1_keywords:
- C3352
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
ms.openlocfilehash: 66d6921c86c6b7a30026880f01ab2a5dada11a65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150946"
---
# <a name="compiler-error-c3352"></a>Błąd kompilatora C3352

"Function": określona funkcja jest niezgodna z typem delegata "Type"

Listy parametrów dla `function` i delegata nie pasują do siebie.

Aby uzyskać więcej informacji, zobacz [Delegat (C++ Component Extensions)](../../extensions/delegate-cpp-component-extensions.md).

Poniższy przykład generuje C3352:

```cpp
// C3352.cpp
// compile with: /clr
delegate int D( int, int );
ref class C {
public:
   int mf( int ) {
      return 1;
   }

   // Uncomment the following line to resolve.
   // int mf(int, int) { return 1; }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352
}
```

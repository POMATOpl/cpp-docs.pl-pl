---
description: 'Dowiedz się więcej o: błąd kompilatora C3699'
title: Błąd kompilatora C3699
ms.date: 11/04/2016
f1_keywords:
- C3699
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
ms.openlocfilehash: 670b5c41aad9afcece8d8cd292727ad64925a4ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228719"
---
# <a name="compiler-error-c3699"></a>Błąd kompilatora C3699

"operator": nie można użyć tego operatora pośredniego dla typu "Type"

Podjęto próbę użycia operatora pośredniego, który jest niedozwolony w `type` .

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3699.

```cpp
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

Właściwość prosta nie może mieć typu referencyjnego. Aby uzyskać więcej informacji, zobacz [Właściwość](../../extensions/property-cpp-component-extensions.md) . Poniższy przykład generuje C3699.

```cpp
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

Odpowiednikiem składni "wskaźnik do wskaźnika" jest dojście do odwołania śledzenia. Poniższy przykład generuje C3699.

```cpp
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```

---
description: 'Dowiedz się więcej o: błąd kompilatora C3181'
title: Błąd kompilatora C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: b9b9c6e8c6271abbea2d97adf92f33c35eb2028b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174133"
---
# <a name="compiler-error-c3181"></a>Błąd kompilatora C3181

"Type": nieprawidłowy operand dla operatora

Do operatora [typeid](../../extensions/typeid-cpp-component-extensions.md) przekazano nieprawidłowy parametr. Parametr musi być typem zarządzanym.

Należy zauważyć, że kompilator używa aliasów dla typów natywnych, które są mapowane na typy w środowisku uruchomieniowym języka wspólnego.

Poniższy przykład generuje C3181:

```cpp
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```

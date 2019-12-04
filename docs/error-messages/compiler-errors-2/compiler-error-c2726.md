---
title: Błąd kompilatora C2726
ms.date: 11/04/2016
f1_keywords:
- C2726
helpviewer_keywords:
- C2726
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
ms.openlocfilehash: 36ddf54b3924ae48969fa810ba2883c51b2264b5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757426"
---
# <a name="compiler-error-c2726"></a>Błąd kompilatora C2726

"gcnew" może być użyty tylko do utworzenia obiektu z typem zarządzanym lub WinRT

Nie można utworzyć wystąpienia typu natywnego na stosie zebranych elementów bezużytecznych.

Poniższy przykład generuje C2726 i pokazuje, jak to naprawić:

```cpp
// C2726.cpp
// compile with: /clr
using namespace System;
class U {};
ref class V {};
value class W {};

int main() {
   U* pU = gcnew U;    // C2726
   U* pU2 = new U;   // OK
   V^ p2 = gcnew V;   // OK
   W p3;   // OK

}
```

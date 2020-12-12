---
description: 'Dowiedz się więcej o: błąd kompilatora C2108'
title: Błąd kompilatora C2108
ms.date: 11/04/2016
f1_keywords:
- C2108
helpviewer_keywords:
- C2108
ms.assetid: c84f0b47-5e2c-47d2-8edb-427a40e17c36
ms.openlocfilehash: 36b10fec25ef508685676464367761225241e5b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170116"
---
# <a name="compiler-error-c2108"></a>Błąd kompilatora C2108

Indeks dolny nie jest typem całkowitym

Indeks dolny tablicy jest wyrażeniem niebędącym liczbą całkowitą.

## <a name="example"></a>Przykład

C2108 może wystąpić w przypadku nieprawidłowego użycia **`this`** wskaźnika typu wartości w celu uzyskania dostępu do domyślnego indeksatora typu. Aby uzyskać więcej informacji, zobacz [semantyka tego wskaźnika](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).

Poniższy przykład generuje C2108.

```cpp
// C2108.cpp
// compile with: /clr
using namespace System;

value struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
   void Test() {
      Console::WriteLine("{0}", this[3.3]);   // C2108
      Console::WriteLine("{0}", this->default[3.3]);   // OK
   }
};

int main() {
   B ^ myb = gcnew B();
   myb->Test();
}
```

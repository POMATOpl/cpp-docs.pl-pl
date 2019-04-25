---
title: Błąd kompilatora C3287
ms.date: 11/04/2016
f1_keywords:
- C3287
helpviewer_keywords:
- C3287
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
ms.openlocfilehash: ab0b93aa1a74ea79515e24ef2b1e289cf0227dac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222680"
---
# <a name="compiler-error-c3287"></a>Błąd kompilatora C3287

Typ "type" (typ zwrotny z GetEnumerator) musi mieć odpowiednie odpowiednią funkcję składową MoveNext i właściwość publiczną Current

Klasy kolekcji zdefiniowanych przez użytkownika musi zawierać definicje `MoveNext` i `Current`.

Zobacz [jak: Iterate Over a User-Defined kolekcji za pomocą każdego](../../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md) Aby uzyskać więcej informacji.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3287.

```
// C3287.cpp
// compile with: /clr
using namespace System;

ref struct R {
   bool MoveNext() {
      return true;
   }
   property Object^ Current {
      Object^ get() {
         Object ^ o = gcnew Object;
         return o;
      }
   }
};

ref struct R2 {
   R ^GetEnumerator() {
      R^ r = gcnew R;
      return r;
   }
};

ref struct T {};

ref struct T2 {
   T ^GetEnumerator() {
      T^ t = gcnew T;
      return t;
   }
};

int main() {
   for each (int i in gcnew T2) {}   // C3287
   for each (int i in gcnew R2) {}   // OK
}
```
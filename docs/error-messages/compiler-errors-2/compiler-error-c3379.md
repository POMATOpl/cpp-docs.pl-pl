---
description: 'Dowiedz się więcej o: błąd kompilatora C3379'
title: Błąd kompilatora C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 622a1327eb84d83fa24d8a084e3266183c669120
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220737"
---
# <a name="compiler-error-c3379"></a>Błąd kompilatora C3379

"Class": zagnieżdżona Klasa nie może mieć specyfikatora dostępu do zestawu jako części swojej deklaracji

W przypadku zastosowania do typu zarządzanego, takiego jak Klasa lub struktura, słowa kluczowe [Public](../../cpp/public-cpp.md) i [Private](../../cpp/private-cpp.md) wskazują, czy Klasa zostanie udostępniona za pomocą metadanych zestawu. `public` lub `private` nie można jej zastosować do klasy zagnieżdżonej, która odziedziczy dostęp do zestawu klasy otaczającej.

Gdy jest używany z [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), `ref` `value` słowa kluczowe i wskazują, że Klasa jest zarządzana (zobacz [klasy i struktury](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Poniższy przykład generuje C3379:

```cpp
// C3379a.cpp
// compile with: /clr
using namespace System;

public ref class A {
public:
   static int i = 9;

   public ref class BA {   // C3379
   // try the following line instead
   // ref class BA {
   public:
      static int ii = 8;
   };
};

int main() {

   A^ myA = gcnew A;
   Console::WriteLine(myA->i);

   A::BA^ myBA = gcnew A::BA;
   Console::WriteLine(myBA->ii);
}
```

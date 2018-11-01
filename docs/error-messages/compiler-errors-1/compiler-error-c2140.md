---
title: Błąd kompilatora C2140
ms.date: 11/04/2016
f1_keywords:
- C2140
helpviewer_keywords:
- C2140
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
ms.openlocfilehash: e04a44007161fcfae5bab948584809590edbc095
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668705"
---
# <a name="compiler-error-c2140"></a>Błąd kompilatora C2140

"type": typ, który jest zależny od parametru typu generycznego nie jest dozwolona jako argument typu wewnętrznej cechy kompilatora "cechy"

Nieprawidłowy specyfikator typu został przekazany do cechy typu.

Aby uzyskać więcej informacji, zobacz [Obsługa cech typu w kompilatorze](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C2140.

```
// C2140.cpp
// compile with: /clr /c
template <class T>

struct is_polymorphic {
   static const bool value = __is_polymorphic(T);
};

class x {};

generic <class T>
ref class C {
   void f() {
      System::Console::WriteLine(__is_polymorphic(T));   // C2140
      System::Console::WriteLine(is_polymorphic<T>::value);   // C2140

      System::Console::WriteLine(__is_polymorphic(x));   // OK
      System::Console::WriteLine(is_polymorphic<x>::value);   // OK
   }
};
```
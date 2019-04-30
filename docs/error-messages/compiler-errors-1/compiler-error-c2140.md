---
title: Błąd kompilatora C2140
ms.date: 11/04/2016
f1_keywords:
- C2140
helpviewer_keywords:
- C2140
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
ms.openlocfilehash: 35b6e38290acddb41bdf53d9663a058259300ee8
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345679"
---
# <a name="compiler-error-c2140"></a>Błąd kompilatora C2140

"type": typ, który jest zależny od parametru typu generycznego nie jest dozwolona jako argument typu wewnętrznej cechy kompilatora "cechy"

Nieprawidłowy specyfikator typu został przekazany do cechy typu.

Aby uzyskać więcej informacji, zobacz [Obsługa cech typu w kompilatorze](../../extensions/compiler-support-for-type-traits-cpp-component-extensions.md).

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
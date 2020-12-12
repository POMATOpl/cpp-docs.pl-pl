---
description: 'Dowiedz się więcej o: błąd kompilatora C2140'
title: Błąd kompilatora C2140
ms.date: 11/04/2016
f1_keywords:
- C2140
helpviewer_keywords:
- C2140
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
ms.openlocfilehash: b9292019ce9a17c8f1dabca87f61f27b21494a82
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124153"
---
# <a name="compiler-error-c2140"></a>Błąd kompilatora C2140

"Type": typ, który jest zależny od parametru typu ogólnego jest niedozwolony jako argument dla cechy wewnętrznego typu "cecha" kompilatora

Nieprawidłowy specyfikator typu został przekazano do cechy typu.

Aby uzyskać więcej informacji, zobacz [Obsługa kompilatora dla cech typu](../../extensions/compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C2140.

```cpp
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

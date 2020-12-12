---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4484'
title: Ostrzeżenie kompilatora C4484
ms.date: 11/04/2016
f1_keywords:
- C4484
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
ms.openlocfilehash: 43228cabc8dfd728ea104f6c3b57d863ec9e5e5a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180737"
---
# <a name="compiler-warning-c4484"></a>Ostrzeżenie kompilatora C4484

"override_function": pasuje do metody bazowej klasy referencyjnej "base_class_function", ale nie jest oznaczona modyfikatorem "Virtual", "New" ani "override"; Założono modyfikator "New" (ale nie "Virtual")

Podczas kompilowania z **/CLR** kompilator nie będzie niejawnie przesłaniał funkcji klasy bazowej, co oznacza, że funkcja uzyska nowe miejsce w tabeli metod wirtualnych. Aby rozwiązać ten problem, należy jawnie określić, czy funkcja jest przesłonięciem.

Aby uzyskać więcej informacji, zobacz:

- [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md)

- [override](../../extensions/override-cpp-component-extensions.md)

- [new (nowe gniazdo w vtable)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

C4484 jest zawsze wystawiony jako błąd. Użyj [ostrzeżenia](../../preprocessor/warning.md) pragma, aby pominąć C4484.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4484.

```cpp
// C4484.cpp
// compile with: /clr
ref struct A {
   virtual void Test() {}
};

ref struct B : A {
   void Test() {}   // C4484
};

// OK
ref struct C {
   virtual void Test() {}
   virtual void Test2() {}
};

ref struct D : C {
   virtual void Test() new {}
   virtual void Test2() override {}
};
```
